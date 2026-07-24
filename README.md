# Kaasu — Financial Wellness, Visualized

Kaasu is a browser-based retirement planning tool that connects the life you want in retirement with the financial decisions you are making today.

The app offers two ways to begin:

- **Build your retirement plan** — estimate retirement spending, Social Security income, your target portfolio, and the annual or monthly investing needed to reach it.
- **See where you're headed** — enter your current income, taxes, budget, invested assets, and contributions to project your retirement trajectory.

## Live site

`https://gvgfr.github.io/Finance-Retirement-/`

## What the app does

### 1. Retirement spending plan

Build an annual retirement budget using essential and lifestyle categories such as:

- Housing and property expenses
- Healthcare and prescriptions
- Food and transportation
- Travel and leisure
- Dining and entertainment
- Family support, fitness, and hobbies

Categories can be edited, added, or removed.

### 2. Retirement target

Kaasu estimates the portfolio needed to support retirement spending while accounting for:

- Your planned retirement age
- Your Social Security benefit
- Your Social Security claiming age
- A spouse's Social Security benefit and claiming age
- Pension, rental, part-time, or other retirement income
- The years before Social Security begins

The model combines a pre-Social-Security bridge amount with a long-term portfolio estimate rather than applying a simple 25× multiplier to all spending.

### 3. Contribution calculator

Enter:

- Current age
- Retirement age
- Current invested assets
- Expected annual real return
- Retirement target

The app calculates the annual and monthly contribution needed to reach the target.

Current invested assets can include:

- 401(k) or 403(b)
- Traditional IRA
- Roth IRA
- Brokerage accounts
- Invested HSA
- Pension cash value

Checking accounts, emergency savings, and money intended for near-term spending should not be included.

### 4. Income and tax estimate

Enter salary, filing status, state, other income, and annual pre-tax 401(k) contributions.

The app estimates:

- Gross income
- Taxable income
- Federal income tax
- FICA
- State income tax
- Take-home cash

These figures are planning estimates and are not tax advice.

### 5. Current budget

The current-budget section includes:

- Housing and utilities
- Insurance and healthcare
- Groceries and transportation
- Student, personal, auto, and other loan payments
- Childcare and family expenses
- Short-term savings goals
- Education savings
- Emergency-fund planning
- Additional monthly retirement investing

Credit-card payments are intentionally excluded as a separate category. Purchases should be entered in their actual spending categories.

### 6. Plan versus current trajectory

The final results compare:

- Growth of current invested assets
- Ongoing 401(k) contributions
- Additional retirement investing
- Projected portfolio at retirement
- Retirement target
- Potential shortfall or surplus
- Portfolio growth and retirement drawdown over time

The results distinguish existing assets, 401(k) contributions, and additional investing so the recommended extra monthly amount is not confused with the amount already going into a workplace plan.

## Data source

The site can load configurable data from a connected Google Sheet through Google Apps Script.

Set the Apps Script deployment URL in `index.html`:

```js
const SHEET_API_URL = "https://script.google.com/macros/s/.../exec";
```

When live data is unavailable, the app uses its built-in default categories and assumptions.

## Files

- `index.html` — the complete browser application
- `Code.gs` — optional Google Apps Script backend for connected Sheet data
- `README.md` — project documentation

There is no build step and no package installation required.

## Running locally

Open `index.html` directly in a browser, or serve the folder with a simple local web server.

For example:

```bash
python3 -m http.server 8000
```

Then visit:

`http://localhost:8000`

## GitHub Pages

1. Push the repository to GitHub.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose the main branch and the repository root.
5. Save.
6. Replace the placeholder live-site URL in this README with the published Pages URL.

## Important limitations

- Retirement projections are estimates, not guarantees.
- The 4% framework is a planning rule of thumb and may not fit every retirement horizon, asset allocation, or market environment.
- Investment returns are uncertain.
- Inflation, taxes, healthcare costs, Social Security rules, and personal circumstances can change.
- Tax calculations are simplified estimates.
- This tool does not provide individualized financial, investment, legal, or tax advice.
