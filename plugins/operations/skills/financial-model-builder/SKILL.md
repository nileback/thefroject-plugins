---
name: financial-model-builder
description: Build structured financial models including DCF valuation, scenario analysis, and sensitivity tables. Walks through assumptions, builds the model layer by layer, and stress-tests the output. Use for investment decisions, fundraising prep, or strategic planning.
triggers:
  - financial model
  - DCF
  - valuation
  - scenario analysis
  - sensitivity analysis
  - cap table
  - build a model
allowed-tools: []
---

# Financial Model Builder

## Writes
- `outputs/financial-model-[name].md`

## Context Scan

Check `context/` and `reference/` for:
- Historical financial statements (P&L, balance sheet, cash flow)
- Revenue breakdown by product/segment
- Headcount and compensation data
- Growth rates and KPIs
- Comparable company data or prior valuations

Ask for what is missing. At minimum you need: 12+ months of historical revenue and costs, and the purpose of the model (fundraising, acquisition, internal planning, etc.).

## Step 1 — Purpose and Structure

Define before building:

- **What decision does this model support?** (raise capital, evaluate acquisition, plan headcount, etc.)
- **Time horizon:** 3-year or 5-year projection
- **Granularity:** Monthly for year 1, quarterly or annual for years 2-5
- **Output needed:** Valuation, break-even analysis, scenario comparison, or all three

## Step 2 — Assumptions

Every model is only as good as its assumptions. Document each one explicitly.

### Revenue Assumptions
| Driver | Historical | Assumed | Basis |
|--------|-----------|---------|-------|
| Revenue growth rate | [Last 12m actual] | [Projected] | [Why this number] |
| Customer count / deal size | | | |
| Pricing changes | | | |
| Churn / retention | | | |
| New product / segment revenue | | | |

### Cost Assumptions
| Driver | Historical | Assumed | Basis |
|--------|-----------|---------|-------|
| Headcount growth | | | |
| Avg. cost per employee | | | |
| Infrastructure / hosting | | | |
| Sales & marketing as % of revenue | | | |
| G&A as % of revenue | | | |

### Capital Assumptions
| Item | Amount | Timing |
|------|--------|--------|
| CapEx | | |
| Working capital changes | | |
| Debt / financing | | |

Flag every assumption that is a guess vs. backed by data. Honest assumption labeling prevents false confidence in the output.

## Step 3 — Income Statement Projection

Build the projected P&L:

| Line Item | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
|-----------|--------|--------|--------|--------|--------|
| Revenue | | | | | |
| COGS | | | | | |
| Gross Profit | | | | | |
| Gross Margin % | | | | | |
| Operating Expenses | | | | | |
| EBITDA | | | | | |
| EBITDA Margin % | | | | | |
| D&A | | | | | |
| EBIT | | | | | |
| Net Income | | | | | |

## Step 4 — Cash Flow Projection

| Line Item | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
|-----------|--------|--------|--------|--------|--------|
| Net Income | | | | | |
| Add back D&A | | | | | |
| Changes in working capital | | | | | |
| Operating cash flow | | | | | |
| CapEx | | | | | |
| Free cash flow | | | | | |
| Cumulative FCF | | | | | |

## Step 5 — DCF Valuation (if applicable)

| Component | Value | Basis |
|-----------|-------|-------|
| Discount rate (WACC) | | [Calculation or comparable] |
| Terminal growth rate | | |
| Terminal value | | |
| PV of projected FCFs | | |
| PV of terminal value | | |
| Enterprise value | | |
| Less: net debt | | |
| Equity value | | |

## Step 6 — Sensitivity Analysis

Test the two assumptions that matter most (usually revenue growth and margin):

| | Growth -20% | Growth -10% | Base | Growth +10% | Growth +20% |
|---|-----------|-----------|------|-----------|-----------|
| Margin -5% | | | | | |
| Margin -2% | | | | | |
| Base margin | | | | | |
| Margin +2% | | | | | |
| Margin +5% | | | | | |

Highlight the cells where the model breaks (negative cash, unrealistic multiples, etc.).

## Step 7 — Scenario Summary

| Metric | Bear Case | Base Case | Bull Case |
|--------|----------|----------|----------|
| Year 5 Revenue | | | |
| Year 5 EBITDA | | | |
| Enterprise Value | | | |
| IRR (if investment) | | | |

For each scenario: state the 2-3 assumptions that differ from base case.

## Do NOT
- Present a model without listing assumptions. The assumptions ARE the model. The math is just arithmetic.
- Use a single discount rate without justifying it. WACC components should be visible.
- Project hockey-stick growth without explaining the mechanism. "Revenue grows 50% because we want it to" is not a model.
- Hide the terminal value. In most DCFs, terminal value is 60-80% of total value. Make it visible and test its sensitivity.
- Build precision you do not have. Projecting revenue to the dollar in year 5 implies accuracy that does not exist. Round appropriately.
