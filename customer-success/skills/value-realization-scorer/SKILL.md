---
name: value-realization-scorer
description: Score customer accounts on likelihood to renew based on value realization. Replaces static health scores with a model that compares each customer's intended outcomes (captured at deal close) to actual outcomes today. The value gap drives renewal probability. Use when user mentions value realization, likelihood to renew, value gap, or modernizing health scores.
triggers:
  - value realization
  - likelihood to renew
  - value gap
  - intended outcomes
  - renewal scoring
  - replace health score
---

# Value Realization Scorer

Score customer accounts on likelihood to renew based on value realization, not static health metrics.

## The 2026 model

Traditional health scores (red/yellow/green) bucket customers by usage and engagement signals. They predict churn, not renewal value. The newer model:

```
Likelihood to Renew = f(Intended Outcomes, Actual Outcomes, Time-to-Value)
```

Where:
- **Intended Outcomes** are captured as structured data at deal close. What did the customer say they'd achieve with this product?
- **Actual Outcomes** are measured against those goals on a quarterly cadence.
- **Value Gap** = Intended − Actual. Smaller gap = higher renewal probability.

This is what mature CS teams in 2026 are moving toward. The shift requires changing how deals close (capturing intended outcomes) and how QBRs run (reporting against them).

## Workflow

### Step 1: Audit deal-close capture
Look at the last 10 closed deals. For each, ask:
- Were intended outcomes captured? In what format?
- Are they measurable (specific metric + target + timeframe)?
- Is the data anywhere CS can access?

If no, the program starts with sales process change. Templates below.

### Step 2: Define the outcome categories
Most products fit into 4-6 outcome categories. Examples for a typical SaaS:
- Time saved (hours per week, per role).
- Revenue impact (deals closed, leads generated, conversion lift).
- Cost saved (tools replaced, headcount avoided).
- Quality lift (defect rate, NPS, accuracy).
- Compliance / risk reduction.
- Capability unlocked (could not do X before).

For each category, define how to measure post-implementation.

### Step 3: Build the scoring rubric

Per account, score against each captured outcome:

| Status | Score | Definition |
|---|---|---|
| Achieved | 100 | Customer hit or exceeded their stated target. |
| On track | 75 | Trending toward target, will hit by renewal. |
| Behind | 50 | Off target but recoverable in 1-2 quarters. |
| Stalled | 25 | No progress; needs intervention. |
| Abandoned | 0 | Customer no longer pursuing this outcome. |

Average across the account's outcomes. Weight by stated priority if the customer ranked them.

### Step 4: Translate to renewal probability
- 80-100: high likelihood (>85% renewal probability historically).
- 60-79: moderate (60-80%).
- 40-59: at risk; CS intervention required.
- Under 40: unlikely; either pivot the engagement or prepare for churn.

Calibrate the brackets against your own historical data once you have 4 quarters of scores.

## Capturing intended outcomes (sales process change)

Add a required field at deal close:

```
Intended Outcomes (mandatory, 2-4 items):
1. [Outcome category] — [Specific target] — [Timeframe] — [Priority: high/med/low]
   Example: "Cost saved — replace [tool X] saving $40k/yr — within 6 months — high"
```

Capture in the CRM as structured fields (not free-text notes). Make it required for the deal to move to closed-won.

## Output format

Save to `outputs/value-realization/<account>-Q<n>.md` per account, per quarter:

```
## Account: <name>
- Plan tier: <tier>
- Renewal date: <date>

## Intended outcomes (captured <date>)
1. <outcome 1> — target — timeframe — priority
2. ...

## Actual outcomes (measured <date>)
1. <outcome 1>: <status> — <measurement>
2. ...

## Value gap analysis
- Score: <N/100>
- Renewal probability: <high/moderate/at-risk/unlikely>
- Drivers: [main reasons]

## Action plan
- Owner: <CSM>
- Next step: <specific action>
- Review: <date>
```

Roll up to a portfolio dashboard at `outputs/value-realization/portfolio-Q<n>.md` with every account's score and the renewal forecast.

## Common mistakes

- Trying to retrofit intended outcomes for accounts that closed without capturing them. Skip these and start from new closes — building backwards is too noisy.
- Letting "intended outcomes" become aspirational marketing copy ("transform our business"). Force specificity.
- Measuring outcomes only at QBR time. Continuous tracking is more useful.
- Ignoring the priority weighting. A "high" outcome behind hurts more than a "low" outcome behind.

## Cross-references

For the QBR that delivers this report to the customer, use `qbr-builder`. For the broader feedback program, use `customer-feedback-orchestration`. For the renewal program built on top of this scoring, use (when added) `renewal-orchestration`. For converting healthy accounts into expansion, use `expansion-opportunity-analyzer`.
