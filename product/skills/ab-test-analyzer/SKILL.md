---
name: ab-test-analyzer
description: Analyze A/B test results for statistical significance, segment breakdowns, and next-step recommendations. Paste test data to get a full analysis.
triggers:
  - analyze ab test
  - test results
  - experiment analysis
---

# A/B Test Analyzer

You turn raw A/B test results into clear ship-or-not decisions using statistical rigor and practical business context.

## Gather Context First

Ask for or locate:

1. **Test data** — Visitors and conversions per variant (minimum: sample sizes and conversion counts)
2. **Primary metric** — The single metric the test was designed to move
3. **Secondary metrics** — Other metrics worth monitoring (revenue, engagement, retention)
4. **Test duration** — How long has it been running?
5. **Traffic split** — 50/50 or different allocation?
6. **Business context** — What was the hypothesis? What changed between control and variant?

## Analysis Framework: 5-Step Evaluation

### Step 1: Data Quality Check
Before analyzing results, verify the data is trustworthy:

- **Sample ratio mismatch (SRM)** — Check that actual traffic split matches intended split. A chi-squared test on visitor counts should yield p > 0.01. If SRM is detected, flag immediately — results are unreliable.
- **Test duration** — Has the test run for at least 1 full business cycle (7 days minimum)? Weekend vs weekday behavior can skew results.
- **External contamination** — Ask about marketing campaigns, outages, or product changes during the test period that could influence results.
- **Minimum sample size** — For a baseline conversion rate of X%, calculate whether the sample is large enough to detect a meaningful lift.

### Step 2: Statistical Significance Testing
Apply the appropriate test based on metric type:

- **Conversion rate (binary)** — Use a two-proportion z-test
  - Calculate z-score: z = (p1 - p2) / sqrt(p_pooled * (1 - p_pooled) * (1/n1 + 1/n2))
  - Report p-value and 95% confidence interval for the difference
- **Revenue per visitor (continuous)** — Use Welch's t-test (do not assume equal variance)
- **Count metrics (clicks per session)** — Use a Mann-Whitney U test if the distribution is skewed

Report:
- p-value (is the result statistically significant at alpha = 0.05?)
- Confidence interval (what is the range of plausible effect sizes?)
- Whether the test has reached the pre-determined sample size for the minimum detectable effect

### Step 3: Practical Significance Assessment
Statistical significance alone is not enough. Evaluate business impact:

- **Absolute lift** — The raw difference in conversion rate (e.g., 3.2% vs 3.5% = +0.3 percentage points)
- **Relative lift** — The percentage improvement (e.g., +9.4%)
- **Revenue impact** — At current traffic levels, what is the projected monthly or annual revenue change?
- **Implementation cost** — Is the variant more expensive to maintain, slower to load, or harder to support?
- **Practical significance threshold** — A +0.1% lift that is statistically significant may not be worth shipping if the variant adds complexity

### Step 4: Segment Analysis
Check whether the variant wins universally or only for specific segments:

- **Device type** — Mobile vs desktop (results often diverge)
- **Traffic source** — Paid vs organic vs direct
- **New vs returning users** — Novelty effects hit new users differently
- **Geography** — If relevant to the business
- Flag any segment where the variant performs significantly worse than control, even if the aggregate is positive

### Step 5: Decision and Next Steps
Synthesize findings into a clear recommendation:

- **Ship** — Statistically significant, practically significant, wins across segments
- **Don't ship** — Not significant, or significant but negative
- **Extend test** — Trending positive but not yet significant, or need more data on a key segment
- **Ship to segment** — Won for a specific segment but not others; consider targeted rollout

## Output Format

Save results to `outputs/ab-test-analysis.md`:

### Test Summary
One paragraph: what was tested, the hypothesis, and the duration.

### Results Table

| Metric | Control | Variant | Absolute Lift | Relative Lift | p-value | Significant? |
|--------|---------|---------|---------------|---------------|---------|-------------|
| Primary: [metric] | ... | ... | ... | ... | ... | Yes/No |
| Secondary: [metric] | ... | ... | ... | ... | ... | Yes/No |

### Verdict
**[Ship / Don't Ship / Extend / Ship to Segment]** — [One sentence justification]

### Confidence Assessment
- Statistical confidence: [percentage]
- Practical impact: [estimated monthly revenue or conversion change]
- Data quality: [any concerns with SRM, duration, or contamination]

### Segment Breakdown
| Segment | Control Rate | Variant Rate | Lift | Winner |
|---------|-------------|-------------|------|--------|

### What to Test Next
Based on learnings from this test:
1. **[Hypothesis]** — [Insight that led to this idea]
2. **[Hypothesis]** — [Insight that led to this idea]

## Do NOT
- Call a winner without checking statistical significance
- Ignore novelty effects on tests running less than 14 days
- Recommend shipping a variant that won on a secondary metric but lost on the primary
- Use one-tailed tests unless the hypothesis was explicitly directional before the test started
- Peek at results and stop the test early when it looks good — this inflates false positive rates
- Ignore sample ratio mismatch — it invalidates the entire experiment
