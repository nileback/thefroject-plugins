---
name: financial-report-writer
description: Draft monthly, quarterly, or annual financial narratives that translate numbers into stories for leadership and board audiences. Use when preparing financial summaries, management reports, or investor updates.
triggers:
  - financial report
  - monthly financials
  - quarterly report
  - management report
---

# Financial Report Writer

Translate financial data into clear narratives that help non-finance stakeholders understand performance and make decisions.

## Input Required

1. **Financial statements** — P&L, balance sheet, and/or cash flow for the period
2. **Budget/forecast** — comparison targets (run the Budget Analyzer skill first if needed)
3. **Prior period data** — for trend context
4. **Operational context** — key events, hires, product launches, market changes
5. **Audience** — who will read this (board, leadership team, department heads, investors)

## Writing Process

### Step 1 — Extract the Headline Numbers

Identify the 5-7 metrics that tell the story:

| Metric | This Period | Prior Period | Budget | YoY Change |
|--------|-----------|-------------|--------|-----------|
| Revenue | | | | |
| Gross Margin % | | | | |
| Operating Expenses | | | | |
| EBITDA | | | | |
| Cash Position | | | | |
| Burn Rate / Runway | | | | |
| [Custom KPI] | | | | |

### Step 2 — Identify the Narrative Arc

Every financial period has a story. Identify which one:

- **Growth story** — revenue up, margins stable or improving
- **Investment story** — costs up, but for strategic reasons with expected payoff
- **Efficiency story** — revenue flat/down, but margins improving through cost control
- **Turnaround story** — previous issues being addressed, leading indicators improving
- **Warning story** — metrics declining, intervention needed

### Step 3 — Draft the Report

Structure based on audience:

**For Board / Investors:**
1. Executive summary (3-4 sentences, lead with the headline)
2. KPI dashboard (table with RAG status)
3. Revenue deep-dive (by segment, product, or geography)
4. Expense overview (major categories, material variances)
5. Cash and liquidity
6. Forward outlook and guidance
7. Key risks and mitigations

**For Leadership / Management:**
1. Summary and key takeaways
2. P&L walkthrough with commentary
3. Department-level detail
4. Operational metrics alongside financial metrics
5. Action items from the numbers

### Step 4 — Apply Financial Writing Standards

- **Lead with insight, not data.** "Revenue grew 12% driven by enterprise expansion" not "Revenue was $4.2M."
- **Explain the why.** Every number that deviates from expectations needs a one-sentence explanation.
- **Use consistent formatting.** Negative numbers in parentheses, percentages to one decimal, currency with appropriate precision.
- **Include context.** Compare to budget, prior period, and prior year. A number without context is meaningless.
- **Highlight actions.** End sections with what needs to happen, not just what happened.

## Output Format

Save to `outputs/financial-report-[period].md`:

```markdown
# Financial Report — [Period]

## Executive Summary
[3-4 sentences. What happened, why it matters, what's next.]

## Key Metrics
| Metric | Actual | Budget | Variance | Prior Period | Trend |
|--------|--------|--------|----------|-------------|-------|

## Revenue
[Narrative with supporting data]

## Expenses
[Narrative with supporting data]

## Cash Position
[Current cash, burn rate, runway]

## Outlook
[Forward-looking statement with key assumptions]

## Action Items
| Item | Owner | Deadline |
|------|-------|----------|
```

## Principles

- Financial reports are decision documents, not data dumps. Every paragraph should help the reader decide something.
- Write for the least financially literate person in the audience. Avoid jargon. Define terms.
- Round appropriately. Board decks use thousands or millions. Department reports might need exact numbers.
