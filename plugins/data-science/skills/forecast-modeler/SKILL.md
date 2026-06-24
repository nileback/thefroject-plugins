---
name: forecast-modeler
description: Create financial forecasts using historical data, trend analysis, and scenario modeling. Use when building annual budgets, updating quarterly forecasts, or modeling business scenarios.
triggers:
  - forecast
  - financial projection
  - revenue model
  - budget forecast
---

# Forecast Modeler

Build data-driven financial forecasts grounded in historical patterns and stated assumptions.

## Input Required

1. **Historical data** — at least 6 months of actual revenue and expenses (12+ preferred)
2. **Known changes** — planned hires, contract renewals, price changes, new products
3. **Growth assumptions** — expected growth rates or targets from leadership
4. **Seasonality notes** — any known seasonal patterns (check `context/business-info.md`)

## Forecasting Process

### Step 1 — Establish the Baseline

Calculate trailing averages and growth rates:

| Metric | Trailing 3-Month Avg | Trailing 6-Month Avg | YoY Growth | MoM Growth |
|--------|---------------------|---------------------|-----------|-----------|
| Revenue | | | | |
| COGS | | | | |
| Gross Margin | | | | |
| OpEx (by category) | | | | |
| Net Income | | | | |

### Step 2 — Identify Drivers

For each major line item, define what drives the number:

| Line Item | Primary Driver | Formula | Data Source |
|-----------|---------------|---------|------------|
| SaaS Revenue | Active customers × ARPU | Customers × $X/mo | CRM data |
| Services Revenue | Billable hours × rate | Hours × $Y/hr | Time tracking |
| Headcount cost | Headcount × avg salary | FTE × $Z/yr | HR data |
| Marketing spend | % of revenue | Revenue × N% | Budget policy |

### Step 3 — Build the Model

Structure the forecast month by month:

```
Revenue
  [Product line 1]: [driver × rate × growth]
  [Product line 2]: [driver × rate × growth]
  Total Revenue

Cost of Goods Sold
  [Category]: [formula]
  Gross Profit

Operating Expenses
  People: [headcount × loaded cost]
  Marketing: [budget or % of revenue]
  Software/tools: [known contracts + growth]
  Office/facilities: [fixed + variable]
  Other: [itemize]
  Total OpEx

EBITDA
Net Income
```

### Step 4 — Scenario Analysis

Build three scenarios with clearly stated assumptions:

| Scenario | Revenue Growth | Expense Growth | Key Assumption |
|----------|---------------|---------------|---------------|
| **Conservative** | [Low end] | [High end] | [What goes wrong] |
| **Base case** | [Expected] | [Expected] | [Plan works as expected] |
| **Optimistic** | [High end] | [Low end] | [What goes right] |

For each scenario, calculate:
- Monthly cash burn or generation
- Months of runway (if applicable)
- Break-even date
- Headcount capacity

### Step 5 — Sensitivity Analysis

Test which assumptions have the biggest impact:

| Variable | -10% Change | Impact on Net Income | +10% Change | Impact on Net Income |
|----------|------------|---------------------|------------|---------------------|
| Revenue | | | | |
| COGS | | | | |
| Headcount | | | | |

## Output Format

Save to `outputs/forecast-[period].md`:

```markdown
# Financial Forecast — [Period]

## Assumptions
[Numbered list of every assumption baked into the model]

## Summary
| Metric | Current | Forecast (Base) | Change |
|--------|---------|----------------|--------|

## Monthly Forecast
[Table with monthly projections]

## Scenarios
[Conservative / Base / Optimistic comparison]

## Key Risks
1. [Risk + trigger + impact]

## Decision Points
- [At what point do we need to adjust hiring?]
- [What revenue milestone triggers the next investment?]
```

## Principles

- State every assumption explicitly. A forecast is only as good as its assumptions, and unstated assumptions cannot be challenged.
- Use driver-based modeling, not "last year plus 10%." Every number should trace back to a business driver.
- Include a cash flow view, not just P&L. Profitable companies can still run out of cash.
