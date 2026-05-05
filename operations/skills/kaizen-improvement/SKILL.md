---
name: kaizen-improvement
description: Run a continuous improvement program inspired by lean / kaizen — small, structured improvements driven from the team level, repeated. Distinct from process-optimizer (one-time process redesign). Use when user mentions kaizen, continuous improvement, lean methodology, or building an ongoing improvement culture.
triggers:
  - kaizen
  - continuous improvement
  - lean
  - improvement culture
  - small improvements
  - improvement program
---

# Kaizen Improvement

Build an ongoing improvement program where small fixes accumulate into compounding gains. Distinct from one-time process redesign (`process-optimizer`); the value here is the cadence and the compounding.

## Gather context

Ask if not provided:

1. **What process or domain?** — customer support, engineering deploys, finance close, content production?
2. **Current state** — already running improvement cycles? First time? Failed attempt before?
3. **Team size** — under 10, 10-50, 50+. Different approaches.
4. **Pain signal** — what triggered this? (Ticket backlog growing, deploys getting slower, something measurable.)
5. **Time available** — how much weekly time can the team commit (typically 1-2 hours).

## The core loop (PDCA / Plan-Do-Check-Act)

Every kaizen cycle is the same loop:

1. **Plan** — pick a small problem (one team can solve in 1-2 weeks). Hypothesize a fix.
2. **Do** — try the fix. Small scope, real conditions.
3. **Check** — measure. Did it work? Better than before, no change, worse?
4. **Act** — if better, standardize the fix. If not, learn and move to the next.

Repeat. Forever.

## Workflow design

### Step 1: Pick the right problems
Good kaizen problems are:
- **Visible** to the team daily (not theoretical).
- **Small enough** to fix in 1-2 weeks (not "rebuild our CI/CD pipeline").
- **Measurable** (you can tell if it improved).
- **Within team control** (not requiring leadership decision or other-team dependency).

Bad kaizen problems:
- "We need to be more strategic." (Vague, not measurable.)
- "Customer success isn't doing its job." (Cross-team blame, not a fix.)
- "Replace the entire CRM." (Too large.)

### Step 2: Build the cadence
A typical weekly kaizen cadence for a 10-person team:

- **Monday standup** — 5 min review of last week's improvement, this week's focus.
- **Wednesday check** — 15 min mid-cycle: is the fix tracking? Block? Tweak?
- **Friday retro** — 30 min: did it work? What's next?

Bigger teams: split into pods of 5-10 with their own kaizen cycles. Each pod owns its area.

### Step 3: Track and visualize
A kaizen board (physical or digital) shows:
- **This week's improvement** — name + owner + target metric.
- **Last week's outcome** — verdict (kept / dropped / iterating).
- **Pipeline of candidate problems** — surfaced from team.
- **Cumulative wins** — running list of standardized improvements (10 wins in 6 months feels like real progress).

### Step 4: Standardize wins
A working kaizen win becomes the new baseline. Document:
- What changed (process, tool, doc, role).
- Why (measurable improvement).
- Who owns ongoing.

Without standardization, gains erode. The team forgets why X was changed; the process drifts back.

## Common improvement domains

Kaizen works for any repetitive process:

- **Engineering deploys** — reduce build time, deploy frequency, rollback frequency.
- **Customer support** — first-response time, resolution time, escalation rate.
- **Content production** — brief-to-publish cycle time, edit rounds, publishing reliability.
- **Sales process** — handoff cleanliness, deal cycle length, MQL response time.
- **Finance close** — days to close, restatements, audit findings.
- **Recruiting** — time-to-hire, candidate experience score, offer acceptance rate.

## Output format

For each cycle, save to `outputs/kaizen/<team>/<week>.md`:

```
## Kaizen cycle: <team> | week <date>

### This week's focus
- Problem: <description>
- Hypothesis: <if we do X, then Y will happen because Z>
- Owner: <name>
- Metric: <how we'll know>

### Mid-cycle check
- Status: on track / off track / blocked
- Tweak: <if any>

### Outcome
- Result: <number>
- Verdict: <kept / dropped / iterating>
- Standardized as: <link to updated process / runbook>
```

Maintain a running scoreboard at `outputs/kaizen/<team>/scoreboard.md` — list of all wins with their measurable improvement. This is the single most motivating artifact in kaizen culture.

## Common mistakes

- Going too big. Kaizen is small + frequent, not occasional + large.
- No measurement. "It feels better now" doesn't accumulate trust.
- No standardization. Wins erode within a quarter.
- Top-down kaizen. The fixes have to come from the team doing the work, not leadership picking them.
- Stopping. Kaizen is forever. The moment you stop, drift starts.
- Tracking effort not outcome. Doing 10 improvements is meaningless if none stuck.

## Cross-references

For one-time process redesign (when the current process is fundamentally broken, not just suboptimal), use `process-optimizer`. For documenting standardized processes that come out of kaizen, use `sop-writer`. For team-level retrospective reviews, use `session-debrief`. For broader operations strategy, use `strategic-alignment`.
