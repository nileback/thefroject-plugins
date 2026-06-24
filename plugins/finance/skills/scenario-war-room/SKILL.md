---
name: scenario-war-room
description: Model cascading what-if scenarios across all business functions simultaneously. Compound adversity, not single-assumption stress tests. Use when user mentions scenario planning, war room, what-if analysis, compound risk, or "what if X AND Y both happen?"
triggers:
  - scenario war room
  - what if analysis
  - compound risk
  - scenario planning
  - cascading effects
  - cross-functional scenario
---

# Scenario War Room

Run a structured cross-functional what-if exercise. Every function has its own stress tests; this skill is for compound scenarios where the question is how multiple bad things interact.

## When to use this skill

- "What if we lose our top customer AND miss the Q3 fundraise?"
- "What if 3 senior engineers quit AND the platform migration is behind schedule?"
- "What if competitor launches at half our price AND a regulatory change forces re-architecture?"
- "What if interest rates spike AND we miss the Q4 quota?"

If the question is single-axis ("what if revenue is down 20%?"), use `scenario-modeling` (finance-specific) or `pre-mortem` (single decision). This skill is for compound, multi-functional scenarios.

## Gather context

Ask if not provided:

1. **What scenario(s)?** — get the user to articulate the compound scenario in concrete terms (specific events, not vague worry).
2. **Time horizon** — 1 quarter, 1 year, multi-year?
3. **Which functions affected** — likely all, but identify which are first-order vs second-order.
4. **Decision the exercise informs** — is this prep for a board conversation? Triggering a contingency plan? Stress-testing a strategic bet?
5. **Participants** — leadership team, function heads, just the founder, full cross-functional group?

## The cascade map

Compound scenarios cascade. Map the chain of events:

```
Trigger event A: <specific event>
Trigger event B: <specific event happening at same time>

First-order effects (immediate):
- Function 1: <effect>
- Function 2: <effect>
- Function 3: <effect>

Second-order effects (within 30-60 days):
- <effect that happens because of the first-order effects>

Third-order effects (within 90+ days):
- <effect that happens because of second-order effects>
```

For each effect, identify:
- Likelihood (high / medium / low) given the trigger.
- Severity (high / medium / low) on the business.
- Function owner (who watches for this and acts).

## The three-track exercise

A war room session typically runs three tracks in parallel:

### Track 1: Identify the breakage points
Where does the business break under this compound scenario? What's the first thing that fails?

Common breakage points:
- Cash runway shortens below safe threshold.
- Critical role or institutional knowledge goes single-point-of-failure.
- Customer concentration becomes a survival risk (top 1-2 customers > X% of revenue).
- Pipeline coverage drops below safe ratio for renewal/expansion target.
- Hiring market tightens just as you need to grow specific functions.

### Track 2: Identify the second-order effects
What does the team itself do under this stress that compounds the problem?

- Reactive cost-cutting that hits growth investments too hard.
- Communication blackouts that erode team trust.
- Talent flight as the highest-performers smell trouble.
- Customer success deprioritized in favor of new sales.

### Track 3: Pre-commit responses
For each breakage point and second-order effect, decide BEFORE the scenario hits what the response is.

Pre-commitment is the key insight. In the moment, decisions are biased by panic, optimism, and politics. Pre-committed responses ("if X happens, we will Y by date Z") are far more rational.

Examples:
- "If runway drops below 12 months, we initiate a 15% cost reduction within 30 days, prioritizing non-revenue functions."
- "If the top 2 customers represent more than 40% of revenue, we pause expansion discussions until concentration is below 30%."
- "If we miss Q3 quota by more than 15%, we run a 30-day sales process audit before any team changes."

## Output format

Save to `outputs/scenario-war-room/<scenario-slug>-<date>.md`:

```
## Scenario: <name>

### Triggers
- A: <event>
- B: <event>

### Cascade map
[Full first / second / third-order cascade]

### Breakage points
1. <breakage> — <function owner> — <pre-committed response>
2. ...

### Second-order risks
1. <risk> — <pre-committed response>
2. ...

### Action plan
- Trigger threshold: when do we activate? (Specific metric / event)
- Owner: who calls it?
- First 30 days: <commitments>
- Communication plan: who hears, what, when

### What we're explicitly NOT doing
[Decisions to avoid in panic mode]
```

## Common mistakes

- Vague scenarios. "Things could get bad" is not a scenario. "Top 3 customers churn AND we lose our Series B lead investor" is.
- Treating it as a one-and-done. Scenarios should be revisited quarterly; conditions change.
- Optimistic cascade mapping. People underweight how badly things compound. Push for darker thinking.
- Pre-commitments that are vague. "We'd consider cost reductions" is not pre-committed. "We cut 15% within 30 days, function-by-function plan attached" is.
- Skipping the communication plan. Half the damage in a crisis is from poor team communication, not the underlying event.

## Cross-references

For single-decision pre-mortems, use `pre-mortem`. For finance-specific scenarios (revenue down N%, runway, fundraise outcomes), use (when added) `scenario-modeling` or existing `forecast-modeler` and `cash-flow-forecaster`. For internal communications during a crisis, use `internal-comms`. For decision documentation around the war room, use `decision-tracker`.
