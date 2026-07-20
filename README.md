# Idaa — financial wellness, visualized

Idaa turns a paycheck into something you can actually see: where every
dollar flows, what your real retirement number is under the 4% rule,
and exactly how much of a $100k salary needs to go toward it.

**Live site:** https://your-username.github.io/idaa/
*(update this link once GitHub Pages is enabled)*

## What's on the page

1. **Money flow** — type in an amount, watch it split into buckets
   (Savings, Essentials, Investing, Fun, Giving) as animated jars.
2. **Retirement number** — build up your estimated annual spending
   category by category (housing, food, healthcare, etc.), and see
   your target nest egg using the 4% withdrawal rule
   (`target = annual spending / 0.04`).
3. **Contribution plan** — enter a salary, timeline, and expected
   growth rate, and see exactly how much needs to go to taxes,
   essentials, and investing each year to hit that number — plus a
   warning if the math doesn't work at your current numbers.

## Data source

The buckets and spending categories are pulled live from a connected
Google Sheet via Apps Script, so you can update the model from your
phone without touching code. If no sheet is connected, the page falls
back to built-in demo data.

### Sheet setup

Two tabs, exact names:

**`Buckets`**

| name | pct | color |
|---|---|---|
| Savings | 30 | #5FA88A |
| Essentials | 35 | #C97B5A |
| Investing | 15 | #4FB6B0 |
| Fun | 12 | #C9A24B |
| Giving | 8 | #B9B29C |

**`RetirementCategories`**

| name | monthly |
|---|---|
| Housing | 1500 |
| Food | 500 |
| Healthcare | 400 |

`pct` and `monthly` are plain numbers — no `%` or `$` symbols.
`color` is optional; leave it blank for a default.

### Connecting the sheet

1. In the Sheet: **Extensions → Apps Script**, paste in `Code.gs`.
2. **Deploy → New deployment → Web app**
   Execute as: *Me* · Who has access: *Anyone*
3. Copy the `/exec` URL it gives you.
4. In `index.html`, set:
   ```js
   const SHEET_API_URL = "https://script.google.com/macros/s/.../exec";
   ```

Editing the sheet data doesn't require redeploying. Editing `Code.gs`
itself does — use *Manage deployments → Edit → New version*.

## Files

- `index.html` — the entire site (no build step, no dependencies)
- `Code.gs` — the Apps Script backend that serves the sheet as JSON

## Notes / limitations

- The 4% rule is a rule of thumb, not a guarantee — it's based on
  historical ~30-year US retirement outcomes and assumes nominal,
  not inflation-adjusted, dollars.
- Tax and growth-rate inputs are rough estimates for planning
  purposes, not financial advice.
