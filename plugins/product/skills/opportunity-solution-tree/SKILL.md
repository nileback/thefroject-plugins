---
name: opportunity-solution-tree
description: Build an Opportunity Solution Tree (OST) — a visual map connecting a desired outcome to user opportunities, candidate solutions, and the experiments that test them. Use when a team has a clear outcome but a fuzzy roadmap, or when too many feature ideas are competing without traceable user evidence.
triggers:
  - opportunity solution tree
  - OST
  - map opportunities
  - discovery tree
---

# Opportunity Solution Tree

Map a desired outcome down to opportunities, solutions, and experiments. The tree forces every solution to trace back to a real user need and every assumption to a planned test. It replaces feature lists with a discovery structure.

## Before You Start

Gather these inputs before drafting the tree:

1. **The outcome** — One business outcome the team owns. Should be a metric or behavior change, not a feature ("increase weekly active teams" beats "ship dashboards").
2. **Recent user research** — Interviews, support tickets, sales calls, or analytics that surface user struggles. The richer this corpus, the more honest the tree.
3. **Existing solution ideas** — The list of features already on the table. They land at the bottom of the tree, not the top.
4. **Team context** — Who owns the outcome, what cadence they review the tree, and what counts as "validated" vs "still risky."

## The Four Layers

```
                        ┌────────────┐
                        │  OUTCOME   │  (single business metric)
                        └─────┬──────┘
              ┌───────────────┼───────────────┐
        ┌─────▼─────┐   ┌─────▼─────┐   ┌─────▼─────┐
        │OPPORTUNITY│   │OPPORTUNITY│   │OPPORTUNITY│  (user struggles, in their words)
        └─────┬─────┘   └─────┬─────┘   └─────┬─────┘
         ┌────┴────┐       ┌──┴──┐         ┌──┴──┐
       ┌─▼─┐  ┌─▼─┐      ┌─▼─┐  ┌─▼─┐    ┌─▼─┐
       │SOL│  │SOL│      │SOL│  │SOL│    │SOL│        (candidate solutions)
       └─┬─┘  └─┬─┘      └─┬─┘  └─┬─┘    └─┬─┘
         ▼      ▼          ▼     ▼         ▼
       [exp] [exp]      [exp] [exp]     [exp]         (experiments to test riskiest assumption)
```

### 1. Outcome (top)
A measurable, time-bound result the team commits to moving. Examples:
- "Lift activation from 38% to 55% by Q3"
- "Cut support tickets per onboarded customer by half"

Bad outcomes: "Ship the new dashboard" (output), "Be the best in the market" (vague).

### 2. Opportunities (middle)
User struggles, needs, or unmet desires — in the user's own words wherever possible. Source them from research; never invent them. Each opportunity must:
- Be tied to a real user moment ("when I'm onboarding a new teammate, I lose the thread because…")
- Be distinct from siblings (no overlap)
- Be sized roughly equally so prioritization is meaningful

Group related raw quotes into clusters. Each cluster becomes one opportunity node.

### 3. Solutions (lower)
Candidate ways to address the parent opportunity. Multiple solutions per opportunity is the norm — that's the whole point. Solutions live below their opportunity, never floating free.

### 4. Experiments (leaves)
For each solution worth pursuing, name the riskiest assumption and the cheapest test. Examples:
- Desirability: "Will users pick this option?" → unmoderated test on a clickable prototype
- Viability: "Will it move the metric?" → A/B test with 10% traffic for two weeks
- Feasibility: "Can we build it under 200ms?" → engineering spike

## Working Process

### Step 1 — Frame the outcome
Pressure-test it. Is it a business outcome (metric the team owns) vs. a product output (feature shipped) vs. a traffic metric (page views)? Reject anything that doesn't pass.

### Step 2 — Inventory user evidence
List the research sources you'll mine. If the cupboard is bare, send the team to do interviews before drawing the tree — don't paper over the gap with assumptions.

### Step 3 — Generate opportunities from evidence
Cluster raw quotes by theme. Aim for 5-8 opportunities at the top level. If you have 20, you're too granular — collapse. If you have 2, you're too abstract — split.

### Step 4 — Brainstorm solutions per opportunity
For each opportunity, generate 3-5 solution candidates. Quantity over polish at this stage. Existing feature ideas land here, under their parent opportunity, not free-floating.

### Step 5 — Prioritize one branch
Pick the opportunity with the strongest signal × weakest current product response. Inside it, pick 1-2 solutions to test. Resist the urge to "go wide" — depth beats breadth in discovery.

### Step 6 — Design experiments
For each chosen solution, write the riskiest assumption as a falsifiable statement. Match it to the cheapest test that can disprove it. A solution worth pursuing is worth a real test, not a stakeholder review.

### Step 7 — Review on a cadence
Weekly or biweekly. Move nodes as evidence comes in. Solutions get killed, opportunities get re-clustered, the tree breathes.

## Output Format

Save the tree to `outputs/discovery/<outcome-slug>-ost.md`:

```
# OST: <Outcome>

**Outcome:** <metric, target, deadline>
**Owner:** <PM>  **Reviewed:** <cadence>  **Last update:** <date>

## Opportunities

### O1 — <user struggle in their words>
**Evidence:** <quotes / tickets / data refs>
**Why it matters:** <theory of impact>

#### Solutions
- S1.1 — <candidate solution>
  - **Riskiest assumption:** <…>
  - **Experiment:** <method, success criterion>
  - **Status:** [exploring | testing | shipping | killed]
- S1.2 — <…>

### O2 — <…>
…

## Killed branches (with reason)
- <node> — <reason>

## Open questions / research debts
- <…>
```

## Do NOT

- Add solutions that don't trace to an opportunity. If you can't connect it, the team is solution-shopping, not problem-solving.
- Frame opportunities in product language ("user needs a settings page"). Restate as a struggle ("user can't find where to invite teammates").
- Treat the tree as a one-time artifact. If it's not edited weekly, the team has stopped doing discovery.
- Let the tree balloon past one screen. Aim for ≤8 opportunities and ≤3 active solutions per branch. Archive the rest.
- Confuse outputs (features) with outcomes (behavior change). Outputs are the means; outcomes are the goal.
