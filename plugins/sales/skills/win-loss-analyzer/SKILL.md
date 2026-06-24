---
name: win-loss-analyzer
description: Analyze won and lost deals to identify patterns and improve win rates.
triggers:
  - win loss analysis
  - deal analysis
  - pipeline review
  - why do we lose deals
  - competitive win rate
---

# Win-Loss Analyzer

You find the patterns in deal outcomes that others miss. The goal is not just to report what happened, but to identify actionable changes that improve future win rates.

## Gather Context First

Check context/ files for existing sales data and CRM information. Ask for what's missing:

1. **Deal data** — CRM export, spreadsheet, or verbal summary of recent deals?
2. **Time period** — Last quarter, last 6 months, trailing 12 months?
3. **Deal stages** — What is the sales process? (stages from lead to closed)
4. **Competitors** — Who do you compete against most frequently?
5. **Data quality** — Are loss reasons consistently tracked? Are deal values accurate?
6. **Sample size** — How many closed deals in the period? (minimum 30 for reliable patterns)

## Analysis Framework

### Dimension 1: Win Rate by Segment

Break down win rate across every meaningful dimension:

| Segment | Metric |
|---------|--------|
| Deal size | Small (<$10K), Mid ($10-50K), Large ($50K+) |
| Industry | Group by customer industry |
| Persona | Who was the primary buyer? (title/role) |
| Source | How did the deal originate? (inbound, outbound, referral, partner) |
| Competitor | Which competitor appeared in the evaluation? |
| Sales rep | Individual rep performance |
| Product line | If multiple products, which were involved? |

For each segment: win rate, average deal size, average sales cycle length, and sample size.

### Dimension 2: Loss Reason Analysis

Categorize every lost deal into exactly one primary reason:

| Category | Definition | Example |
|----------|-----------|---------|
| **Price** | Lost on cost, not value perception | "Too expensive compared to X" |
| **Feature gap** | Missing a capability the buyer required | "No SSO support" |
| **Timing** | Budget frozen, reorganization, not ready | "Revisiting next quarter" |
| **Competitor** | Chose a specific named alternative | "Went with Competitor Y" |
| **No decision** | Evaluation ended without choosing anyone | "Project deprioritized" |
| **Champion left** | Internal advocate changed roles | "New VP has different priorities" |
| **Trust/fit** | Didn't believe you could deliver | "Felt like too small a vendor" |

**Important:** "No decision" is often the largest category. Analyze it separately. These deals were not lost to a competitor. They were lost to the status quo.

### Dimension 3: Stage Conversion Analysis

For each stage in the pipeline:
- Conversion rate to next stage
- Average time in stage
- Deals that stall (over 2x average time)
- Deals that skip stages (healthy or rushed?)

Identify the "leaky bucket" stage where the most value drops out.

### Dimension 4: Competitive Analysis

For deals involving a named competitor:
- Win rate against each competitor
- Common objections when facing each competitor
- Features or positioning where you win
- Features or positioning where you lose
- Average discount given in competitive deals

### Dimension 5: Time Trend Analysis

Compare metrics across time periods:
- Is win rate improving or declining?
- Are loss reasons shifting? (if "feature gap" is growing, product needs to know)
- Is average deal size changing?
- Is sales cycle lengthening?

## Output Format

Save to outputs/win-loss-analysis.md:

### Executive Summary
3-5 bullet points: biggest findings, biggest risk, and the single most impactful action.

### Win Rate Dashboard
| Segment | Win Rate | Deals | Avg Size | Avg Cycle | Trend |
|---------|----------|-------|----------|-----------|-------|

### Loss Reason Distribution
| Reason | % of Losses | Deals | Trend vs Prior Period |
|--------|-------------|-------|---------------------|

### Top 5 Recommendations (ranked by expected impact)
1. **[Action]** — [Expected impact on win rate] — Owner: [Sales/Product/Marketing]

### Competitive Battle Card Summary
For each top competitor: when we win, when we lose, recommended positioning.

### Data Quality Notes
Flag any caveats: small sample sizes, inconsistent data entry, missing fields.

## Do NOT
- Draw conclusions from fewer than 10 deals in a segment
- Treat "no decision" the same as "lost to competitor" — they need different interventions
- Ignore sales rep variance (some patterns are rep-specific, not market-wide)
- Present findings without specific, actionable recommendations
- Assume self-reported loss reasons are accurate (reps often say "price" when the real reason is different)
- Skip the time trend analysis — point-in-time snapshots miss important shifts

## Succeeds when
- Findings lead to specific, owned changes in sales, product, or marketing
- "No decision" losses are analyzed separately from competitive losses
- Loss reasons are validated against buyer interviews, not only rep self-reports
- Trends across periods are surfaced, not just point-in-time snapshots
- Sample sizes are stated honestly so reviewers know what to trust

## Fails when
- Conclusions are drawn from segments with too few deals to be reliable
- All losses are bucketed together, masking the status quo problem
- Self-reported loss reasons are accepted without scrutiny
- Recommendations are unspecific ("improve win rate") with no owner
