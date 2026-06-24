---
name: strategic-alignment
description: Design and cascade goals (OKRs or similar) across the org so every team knows how their work ladders up to company strategy. Covers annual planning, quarterly cascades, alignment rituals, and the failure modes that kill goal systems. Use when user mentions OKRs, strategic alignment, cascading goals, annual planning, or "no one knows what we're prioritizing."
triggers:
  - strategic alignment
  - okr design
  - cascade goals
  - annual planning
  - quarterly planning
  - company priorities
---

# Strategic Alignment

Build the goal-cascade system that connects company strategy -> team goals -> individual contribution. Every working version has the same structure; most failures look the same too.

## Gather context

Ask if not provided:

1. **Org size** — under 50, 50-200, 200+. Cascade depth varies.
2. **Current state** — no goal system, OKRs already running, MBOs, KPIs, ad-hoc?
3. **Cadence** — annual + quarterly? Annual only? Bi-annual?
4. **Most recent failure** — if a system was tried and failed, what went wrong?
5. **Tooling** — Notion, Lattice, 15Five, custom, none?

## The cascade structure

Three levels for most orgs (4 if very large):

### Level 1: Company strategy (annual)
The top of the cascade. 3-5 priorities for the year. Each priority is a clear strategic bet, not a metric.

Examples (well-formed):
- "Move upmarket to mid-market customers."
- "Expand product from data ingestion to data activation."
- "Establish the brand as the category leader in [domain]."

Examples (poorly-formed):
- "Grow revenue." (Too vague.)
- "Hit $50M ARR." (That's the result, not the strategy.)
- "Win." (Useless.)

Each priority gets a 1-page narrative: why it matters, what it requires, what success looks like, what we're NOT doing to enable it.

### Level 2: Function or team objectives (quarterly)
Each function defines 2-4 quarterly objectives that ladder up to company priorities.

Format (one variant — adapt to your culture):
- **Objective**: a qualitative outcome ("Reduce mid-market churn by half").
- **Key Results** (2-4): measurable indicators (KR1: monthly logo churn drops from 4% to 2%; KR2: NPS in mid-market segment improves from 35 to 50; etc.).

Each objective should clearly trace to one company priority.

### Level 3: Individual contributions (quarterly)
Each person owns 2-3 commitments that contribute to their team's objectives. These show up in 1:1s and performance reviews.

Format: "Ship X by date Y, expected to move metric Z by amount W."

## Cascade rituals

Goals without rituals decay. Build:

- **Annual offsite** (1-2 days) — leadership sets company priorities for the year.
- **Quarterly planning** (1 week) — each function drafts objectives, leadership reviews for alignment, finalize.
- **Monthly check-in** (per function, 30 min) — progress against KRs.
- **Weekly 1:1** — manager-rep check on individual commitments.
- **Quarterly retro** — what did we ship, what slipped, why.

## The four failure modes

Watch for these. They kill goal systems quietly:

### 1. Goal cascading becomes paperwork
Symptom: people copy-paste their goals from last quarter, leadership doesn't push back.
Fix: leadership reviews must require a real conversation. If a goal is identical to last quarter and KRs missed, that's a flag.

### 2. Misaligned cascades
Symptom: team goals don't tie to company priorities. Each function optimizes locally.
Fix: explicit traceability column on every team objective: "ladders to company priority #X". If a team can't tie its objective to one, the objective is wrong.

### 3. Hitting numbers, missing strategy
Symptom: KRs are green, but the underlying strategic bet isn't progressing.
Fix: leadership reviews ask "did we move the priority?", not just "did we hit the KRs?". Sometimes you hit the KRs by luck or by gaming the metric.

### 4. Too many goals
Symptom: each team has 6 objectives, 30 KRs. Nobody can prioritize.
Fix: hard cap. 3-4 objectives per team. If everything is important, nothing is.

## Output format

Save the strategic alignment artifacts to:
- `outputs/strategic-alignment/<year>-priorities.md` — company priorities with narratives.
- `outputs/strategic-alignment/<year>-Q<n>/<function>.md` — per-function objectives + KRs.
- `outputs/strategic-alignment/<year>-Q<n>-retro.md` — quarterly retrospective.

Visualize the cascade in `outputs/strategic-alignment/cascade-map.md` — a tree showing every team objective traced to its company priority.

## Common mistakes

- Setting goals that aren't strategically meaningful (revenue targets disguised as priorities).
- Designing in isolation. Each function writes goals without seeing peer functions; gaps and conflicts surface mid-quarter.
- No mid-quarter pulse. Goals get reviewed at the end and slipped goals come as a surprise.
- Confusing goals with budgets. They're different artifacts; cascade them separately.
- Treating individual goals as performance contracts. Goals are commitments; performance is judged on broader factors.

## Cross-references

For roadmap planning specifically (product-tagged), use `roadmap-planner`. For decision tracking that comes out of priority debates, use `decision-tracker`. For OKR retrospectives at the team level, use `session-debrief`. For internal communication of priorities, use `internal-comms`. For business intelligence reporting against goals, use (when added) `business-intelligence`.
