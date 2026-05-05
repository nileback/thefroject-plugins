---
name: scenario-modeling
description: Build best/base/worst financial scenarios with explicit assumptions and sensitivity analysis. Finance-specific — for cross-functional compound scenarios use scenario-war-room. For one-time decision pre-mortems use pre-mortem.
triggers:
  - scenario modeling
  - financial scenarios
  - sensitivity analysis
  - best case worst case
  - runway under stress
  - downside model
---

# Scenario Modeling

Build financial scenarios that drive better decisions. Three named cases (best, base, worst) with explicit assumptions, sensitivity tables, and decision triggers.

## Gather context

Ask if not provided:

1. **What's the decision?** — fundraise sizing, hiring plan, pricing change, geo expansion, runway management?
2. **Time horizon** — 4 quarters, 8 quarters, multi-year?
3. **Granularity** — monthly, quarterly?
4. **Existing model** — is there a base financial model to build on, or starting fresh?
5. **Key drivers** — what 3-5 inputs swing the model the most (top-of-funnel, conversion, ACV, churn, hiring pace, etc.)?

## The three cases

### Base case
The most likely scenario given current trends and committed plans.
- Revenue: forecast based on actual top-of-funnel + historical conversion + committed pipeline.
- Costs: existing run-rate + committed hires + committed contracts.
- One-time items: explicit list.
- Free cash flow / burn: derived.

### Best case
Achievable upside. Not "everything goes perfectly" — that's fantasy and erodes credibility.
- Revenue: top-of-funnel grows N% (cite reason — channel investment, campaign).
- Conversion improves M% (cite reason — better positioning, new segment).
- Costs: same hiring plan, possible operational efficiency gains.
- Best case should be achievable with effort, not luck.

### Worst case
Realistic downside, not catastrophe.
- Revenue: top-of-funnel flat or down N%, conversion deteriorates M%.
- Cost: same plan unless triggered cost-cutting kicks in.
- Don't model "what if every account churns" — that's not a scenario, that's an apocalypse.

For each case, document the assumption changes vs. base. Do NOT change everything — change 3-5 key drivers and let the model show the impact.

## Sensitivity table

Beyond the three cases, build a sensitivity table for the top 2 drivers. Example:

| | Conversion -20% | Conversion -10% | Base | Conversion +10% | Conversion +20% |
|---|---|---|---|---|---|
| Top-of-funnel -20% | <$> | <$> | <$> | <$> | <$> |
| Top-of-funnel -10% | <$> | <$> | <$> | <$> | <$> |
| Base | <$> | <$> | <$> | <$> | <$> |
| Top-of-funnel +10% | <$> | <$> | <$> | <$> | <$> |
| Top-of-funnel +20% | <$> | <$> | <$> | <$> | <$> |

This shows the user the contour of the space, not just three points.

## Decision triggers

For each scenario, document what the team does at it:

- **In the worst case**: at what point do we cut costs? By how much? Which functions?
- **In the best case**: at what point do we accelerate hiring? Marketing investment?
- **At what specific metric / threshold** does each trigger fire?

Pre-committing these decisions in calmer waters is the entire point of the modeling.

## Workflow

1. Confirm or build the base model (single set of assumptions, monthly forecast).
2. Identify the 3-5 highest-leverage assumptions.
3. Create best and worst variants by varying those assumptions.
4. Build the sensitivity table on top 2 drivers.
5. Write the decision triggers.
6. Visualize: 3-line chart (best, base, worst) for revenue, costs, cash position.

## Output format

Save to `outputs/scenario-modeling/<topic>-<date>.xlsx` (the model itself) plus `outputs/scenario-modeling/<topic>-<date>-narrative.md`:

```
## Scenario: <topic>
- Time horizon: <period>
- Granularity: <monthly / quarterly>
- Author: <user>

## Assumptions changed across cases
| Driver | Base | Best | Worst |
|---|---|---|---|
| <driver 1> | ... | ... | ... |

## Key results
- Revenue (period N): base $X / best $Y / worst $Z
- Cash position end-of-horizon: base $X / best $Y / worst $Z
- Months runway in worst case: <N>

## Sensitivity (top 2 drivers)
[table]

## Decision triggers
- If <metric> drops below <threshold> by <date>: <action>
- If <metric> exceeds <threshold> by <date>: <action>

## Recommendation
<one paragraph: what should leadership do given these scenarios?>
```

## Common mistakes

- Three cases that all look basically the same. The point is contrast.
- Best case as wishful thinking. Loses leadership trust.
- Worst case as catastrophe. Models that say "we're dead" without nuance get dismissed.
- No decision triggers. Modeling without action is theater.
- Modeling top-line only. Cash position and runway are usually the decision drivers.

## Cross-references

For cross-functional compound scenarios (not just finance), use `scenario-war-room`. For runway-specific modeling on a 13-week horizon, use `cash-flow-forecaster`. For underlying financial-model construction, use `financial-model-builder`. For board-level presentation of scenarios, use (when added) `board-deck-builder`.
