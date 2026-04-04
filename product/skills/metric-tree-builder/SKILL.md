---
name: metric-tree-builder
description: Break down a top-line metric into its component parts to identify which levers have the highest impact. Use when setting goals, diagnosing metric movement, or deciding where to focus.
triggers:
  - metric tree
  - break down metrics
  - metric decomposition
  - growth model
---

# Metric Tree Builder

A metric tree decomposes a top-line number into its component parts so you can see which inputs drive the output. Instead of staring at "revenue is flat," you can see that signups are up but activation is down, so the problem is onboarding, not acquisition.

## Phase 1 — Define the Top-Line Metric

Start with one metric that matters most right now:

| Field | Value |
|-------|-------|
| Metric | [e.g., Monthly Recurring Revenue] |
| Current value | [$X] |
| Target value | [$Y] |
| Time horizon | [by when] |

## Phase 2 — Decompose

Break the metric into a multiplication tree. Each level should be a direct mathematical relationship.

**Revenue example:**
```
Revenue
├── New Revenue
│   ├── New Customers = Visitors x Signup Rate x Activation Rate x Conversion Rate
│   └── ARPU (new) = Average Plan Price
├── Expansion Revenue
│   ├── Upgrades = Active Customers x Upgrade Rate x Upgrade Amount
│   └── Add-ons = Active Customers x Add-on Attach Rate x Add-on Price
└── Churned Revenue (negative)
    └── Churned MRR = Active Customers x Churn Rate x Average MRR
```

**User growth example:**
```
Active Users
├── New Users = Reach x Click Rate x Signup Rate x Activation Rate
├── Retained Users = Prior Active x Retention Rate
├── Resurrected Users = Dormant Users x Reactivation Rate
└── Churned Users (negative) = Prior Active x Churn Rate
```

## Phase 3 — Quantify Each Node

Fill in current values at every level of the tree:

| Node | Current Value | Unit |
|------|--------------|------|
| [metric] | [value] | [%, $, count] |

## Phase 4 — Sensitivity Analysis

For each leaf node, calculate: if this input improves by 10%, how much does the top-line metric move?

| Input | Current | +10% Value | Top-Line Impact | Rank |
|-------|---------|-----------|-----------------|------|
| [input metric] | [current] | [improved] | [$ or % change at top] | [#] |

Sort by top-line impact. The highest-impact inputs are where effort should concentrate.

## Phase 5 — Identify Leverage Points

A leverage point has:
1. **High sensitivity** — small changes produce large top-line impact
2. **Room to improve** — current performance is below benchmark or historical best
3. **Actionable** — the team can influence this metric directly

| Leverage Point | Impact | Headroom | Actionability | Priority |
|---------------|--------|----------|---------------|----------|
| [metric] | H/M/L | H/M/L | H/M/L | [rank] |

## Output

Write to `outputs/metric-tree-[metric-name].md`:

1. **Top-line metric** — definition, current value, target
2. **Tree diagram** — full decomposition with current values
3. **Sensitivity analysis** — ranked inputs by impact
4. **Leverage points** — where to focus with reasoning
5. **Next steps** — specific initiatives tied to the highest-leverage inputs

## Do NOT
- Build trees deeper than 4 levels — the precision becomes false
- Include metrics you cannot measure or influence
- Treat the tree as static — update it monthly as inputs change
- Confuse correlation with causation — the tree shows mathematical relationships, not causal ones
