---
name: cash-flow-forecaster
description: Build a rolling cash flow forecast from historical actuals, committed spend, and expected revenue. Focuses on liquidity, runway, and timing of cash needs. Use for monthly planning, board prep, or when evaluating whether you can afford a new hire or investment.
triggers:
  - cash flow forecast
  - runway analysis
  - liquidity planning
  - when do we run out of money
  - cash position
allowed-tools: []
---

# Cash Flow Forecaster

## Writes
- `outputs/cash-flow-forecast.md`

## Context Scan

Check `context/` and `reference/` for:
- P&L or income statements
- Bank balances or treasury reports
- Committed contracts (both revenue and expense)
- Headcount plan
- Capital expenditure plans

Ask for anything missing. At minimum you need: current cash balance, monthly revenue (or revenue schedule), and monthly fixed costs.

## Step 1 — Baseline Cash Position

Document the starting point:

| Item | Amount | Source |
|------|--------|--------|
| Cash on hand | | Bank statement / treasury |
| Committed receivables (next 90 days) | | AR aging or contracts |
| Committed payables (next 90 days) | | AP aging or contracts |
| Net current position | | Calculated |

## Step 2 — Monthly Cash Flow Build

For each of the next 6-12 months, project:

| Month | Revenue In | Operating Costs | Payroll | One-Time Costs | Net Cash Flow | Closing Balance |
|-------|-----------|----------------|---------|---------------|--------------|----------------|
| [Month] | | | | | | |

**Revenue assumptions:** Use contracted/committed revenue where available. For pipeline revenue, discount by probability. State every assumption explicitly.

**Cost assumptions:** Split into fixed (rent, salaries, subscriptions) and variable (commissions, usage-based costs). Flag any costs that step up at specific thresholds.

## Step 3 — Runway Calculation

Based on the monthly projection:

- **Months of runway** at current burn rate (no revenue growth)
- **Months of runway** at projected burn rate (with planned hires or investments)
- **Break-even month** if applicable
- **Minimum cash threshold** the business should maintain (typically 3 months of operating costs)

## Step 4 — Scenario Analysis

Run three scenarios:

**Base case:** Current trajectory with stated assumptions.

**Downside:** Revenue 20% below plan, costs on track. What happens? When does cash get tight?

**Upside:** Revenue 20% above plan, costs on track. How much earlier does break-even arrive? What investments become possible?

For each scenario, flag the month where cash drops below the minimum threshold.

## Step 5 — Cash Timing Risks

Identify timing mismatches:

| Risk | Impact | Likelihood | Mitigation |
|------|--------|-----------|-----------|
| Late customer payments | Cash gap in [month] | High/Med/Low | [Action] |
| Front-loaded annual contracts | Lumpy revenue | | |
| Seasonal cost spikes | [Specific months] | | |
| Planned large purchases | [Item and timing] | | |

## Step 6 — Recommendations

Based on the forecast:

1. **Immediate actions** needed in the next 30 days
2. **Timing decisions** — when to make planned hires or investments based on cash position
3. **Collection priorities** — which receivables to chase first
4. **Cost levers** — what to cut or defer if the downside scenario materializes

## Do NOT
- Confuse profit with cash. A profitable month can be cash-negative if receivables are slow.
- Ignore payment terms. Net-60 receivables and net-30 payables create real cash gaps.
- Project more than 12 months without flagging uncertainty. Longer forecasts are less reliable.
- Present a single scenario. Cash planning without downside analysis is wishful thinking.

## 13-Week Cash Flow Mode

Switch to weekly granularity over the next 13 weeks when the user mentions "13-week cash", "rolling cash forecast", "weekly cash flow", or when runway is under 12 months. 13-week is the standard tight-runway forecast — weekly granularity surfaces timing risks (when receivables arrive vs. when payroll hits) that monthly views miss.

For each week, project:

| Week | Receipts | Disbursements | Payroll Week (Y/N) | Net | Closing Balance |

Notes for the 13-week build:
- Receipts: each named customer with their expected payment week. Don't blend.
- Disbursements: split fixed weekly (subscriptions) from variable (vendor invoices). List vendors over $5k by name.
- Payroll: most companies pay bi-weekly. Mark the actual payroll weeks; payroll spikes break the average.
- One-time items (capex, tax, debt service): list each separately on the week they hit.

Output to `outputs/cash-flow-13-week.md` with a "minimum balance week" flag (the lowest projected closing balance and which week it lands).
