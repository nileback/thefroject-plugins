---
name: north-star-metric
description: Define a North Star Metric that captures the core value your product delivers and aligns the team around one primary indicator of success. Use when setting strategy, aligning teams, or when multiple metrics compete for attention.
triggers:
  - north star metric
  - primary metric
  - what should we measure
  - success metric
---

# North Star Metric Designer

A North Star Metric (NSM) is the single metric that best captures the value your product delivers to customers. It aligns product, engineering, marketing, and sales around one shared definition of success.

## What Makes a Good NSM

A valid North Star Metric must pass all five tests:

| Test | Question | Pass/Fail |
|------|----------|-----------|
| Value | Does it measure value delivered to the customer, not just value captured by the business? | |
| Leading | Does improvement in this metric predict future revenue growth? | |
| Actionable | Can the team influence it through their daily work? | |
| Understandable | Can every team member explain what it means and how their work connects to it? | |
| Measurable | Can you track it reliably with existing or buildable instrumentation? | |

## Phase 1 — Identify Candidates

List 3-5 candidate metrics. For each, describe what it measures and why it might be the NSM:

| Candidate | What It Measures | Product Type Fit |
|-----------|-----------------|-----------------|
| [metric] | [what value it reflects] | [attention, transaction, productivity] |

### Common NSMs by Product Type
| Type | Example NSM | Why |
|------|------------|-----|
| SaaS / Productivity | Weekly active users completing core action | Measures ongoing value delivery |
| Marketplace | Weekly transactions | Measures both sides getting value |
| Subscription media | Weekly hours consumed | Measures engagement with content |
| E-commerce | Monthly purchases per active customer | Measures repeat value |
| Social / Communication | Daily messages sent | Measures connection value |

## Phase 2 — Evaluate Candidates

Score each candidate:

| Candidate | Value (1-5) | Leading (1-5) | Actionable (1-5) | Understandable (1-5) | Measurable (1-5) | Total |
|-----------|-------------|---------------|-------------------|---------------------|-------------------|-------|
| [metric] | | | | | | |

The highest-scoring candidate is your NSM. If two are close, prefer the one that is more understandable.

## Phase 3 — Build the Input Tree

The NSM should decompose into 3-5 input metrics that different teams own:

```
North Star Metric: [your NSM]
├── Input 1: [metric] → owned by [team]
├── Input 2: [metric] → owned by [team]
├── Input 3: [metric] → owned by [team]
└── Input 4: [metric] → owned by [team]
```

Each input should be:
- Directly measurable
- Owned by one team
- Clearly connected to the NSM through a logical (ideally mathematical) relationship

## Phase 4 — Set Targets

| Metric | Current | 30-Day Target | 90-Day Target | Source |
|--------|---------|---------------|---------------|--------|
| NSM | [value] | [target] | [target] | [where you measure it] |
| Input 1 | [value] | [target] | [target] | [source] |
| Input 2 | [value] | [target] | [target] | [source] |

## Output

Write to `outputs/north-star-metric.md`:

1. **The metric** — name, definition, current value
2. **Why this metric** — how it passed the five tests
3. **Input tree** — component metrics with team ownership
4. **Targets** — 30-day and 90-day goals
5. **What it does NOT measure** — acknowledged blind spots and how you compensate

## Do NOT
- Choose revenue as your NSM — revenue is a lagging indicator of value, not value itself
- Pick a metric that only one team can influence — the NSM must be shared
- Change the NSM frequently — commit for at least two quarters
- Ignore the metrics you did NOT choose — track them as guardrails
