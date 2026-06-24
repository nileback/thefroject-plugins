---
name: budget-analyzer
description: Perform budget vs actual analysis with variance reporting, trend identification, and actionable recommendations. Use when reviewing monthly/quarterly financials, preparing variance reports, or investigating cost overruns.
triggers:
  - budget analysis
  - variance report
  - budget vs actual
  - spending review
---

# Budget Analyzer

Analyze financial performance by comparing budgeted amounts to actual results. Surface the variances that matter and explain why they happened.

## Input Required

Before starting, gather:

1. **Budget data** — the approved budget for the period (check `context/current-data.md` or ask the user to paste it)
2. **Actuals data** — actual revenue and expenses for the same period
3. **Prior period data** — previous month/quarter for trend comparison (if available)
4. **Chart of accounts** — how line items are categorized (check `context/business-info.md`)

## Analysis Process

### Step 1 — Build the Variance Table

For each line item, calculate:

| Line Item | Budget | Actual | Variance ($) | Variance (%) | Favorable? | Notes |
|-----------|--------|--------|-------------|-------------|-----------|-------|
| [Category] | [Amount] | [Amount] | [Actual - Budget] | [Var / Budget × 100] | ✅ / ⚠️ / ❌ | [Context] |

**Favorable vs unfavorable:**
- Revenue: Actual > Budget = Favorable
- Expense: Actual < Budget = Favorable

### Step 2 — Flag Material Variances

Apply materiality thresholds:

| Threshold | Action |
|-----------|--------|
| > 10% AND > $5,000 | Investigate — requires explanation |
| > 5% AND > $2,000 | Note — monitor next period |
| < 5% OR < $2,000 | Acceptable — no action needed |

Adjust thresholds based on the organization's size. A $5,000 variance is material for a startup, not for a $100M company.

### Step 3 — Classify Variance Root Causes

For each material variance, identify the driver:

- **Timing** — expense will hit next period (not a real variance)
- **Volume** — more or fewer units than planned
- **Rate** — different price per unit than planned
- **Scope** — unbudgeted activity or cancelled initiative
- **One-time** — non-recurring event (severance, legal settlement, equipment)
- **Structural** — ongoing change that affects future periods

### Step 4 — Trend Analysis

Compare the current period to the trailing 3-6 periods:

- Which line items are consistently over or under budget?
- Are variances growing or shrinking over time?
- Are there seasonal patterns the budget should account for?

### Step 5 — Cash Flow Impact

Calculate the net impact on cash:

| Metric | Amount |
|--------|--------|
| Budgeted net income | [Amount] |
| Actual net income | [Amount] |
| Net variance | [Amount] |
| Working capital impact | [Amount] |

## Output Format

Save the report to `outputs/budget-analysis-[period].md`:

```markdown
# Budget vs Actual Analysis — [Period]

## Executive Summary
[2-3 sentences: overall performance, biggest variance, key takeaway]

## Variance Summary
| Category | Budget | Actual | Variance | % |
|----------|--------|--------|----------|---|

## Material Variances (Detail)
### [Line Item 1]
- **Variance:** $X (Y%)
- **Root cause:** [Classification + explanation]
- **Action:** [What to do about it]
- **Future impact:** [One-time or ongoing]

## Trends
[Notable patterns across periods]

## Recommendations
1. [Specific action with owner and timeline]
2. [Specific action with owner and timeline]
```

## Principles

- Report variances in both dollars and percentages. A 50% variance on a $200 line item is noise. A 3% variance on a $2M line item is a story.
- Separate timing variances from real variances. Many "misses" are just timing differences that correct next period.
- Always ask "so what?" — a variance without a recommendation is just trivia.
