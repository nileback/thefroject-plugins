---
name: pre-mortem
description: Conduct a pre-mortem analysis to identify risks and failure modes before launch. Use when starting a major initiative, planning a release, or evaluating a strategic bet.
triggers:
  - pre-mortem
  - risk analysis
  - what could go wrong
  - failure mode analysis
---

# Pre-Mortem Analyst

A pre-mortem starts with the assumption that the project has already failed. Your job is to work backwards from that failure to identify what went wrong, then build mitigations before it actually happens.

## Phase 1 — Set the Scene

Define the project clearly:

| Field | Value |
|-------|-------|
| Project/initiative | [name] |
| Target outcome | [what success looks like] |
| Timeline | [expected delivery date] |
| Key stakeholders | [who cares about this] |

Now imagine it is [delivery date + 2 weeks]. The project has failed. Not "didn't go perfectly" — genuinely failed. Adoption is flat, the feature shipped broken, the launch was ignored, the team burned out. Something went seriously wrong.

## Phase 2 — Generate Failure Modes

List every plausible way the project could fail. Be specific. Group by category:

### Technical Failures
- What breaks in the implementation?
- What integration or dependency causes problems?
- What scales poorly or performs badly?
- What security or data issue surfaces?

### Market/User Failures
- What if users don't care about this?
- What if the problem is real but the solution misses the mark?
- What if a competitor ships something better first?
- What if the target audience is smaller than assumed?

### Execution Failures
- What if the scope creeps beyond the timeline?
- What if key people are unavailable?
- What if cross-team dependencies stall?
- What if the team burns out mid-project?

### Communication Failures
- What if stakeholders have different expectations?
- What if the launch message confuses people?
- What if documentation or onboarding is insufficient?
- What if feedback loops are too slow to course-correct?

## Phase 3 — Score and Prioritize

For each failure mode:

| Failure Mode | Likelihood (1-5) | Impact (1-5) | Risk Score | Category |
|-------------|-------------------|--------------|------------|----------|
| [specific failure] | [how likely] | [how bad] | [L x I] | [category] |

Sort by risk score descending. The top 5 are your priority mitigations.

## Phase 4 — Build Mitigations

For each high-risk failure mode, define:

| Failure Mode | Mitigation | Owner | Trigger |
|-------------|------------|-------|---------|
| [what could go wrong] | [specific action to reduce risk] | [who owns it] | [when to activate] |

**Mitigation types:**
- **Prevent:** Remove the condition that causes the failure
- **Detect:** Add monitoring or checkpoints that surface the problem early
- **Contain:** Limit the blast radius if the failure occurs
- **Recover:** Plan how to fix or roll back

## Phase 5 — Write the Brief

Output to `outputs/pre-mortem-[project].md`:

1. **Project summary** — what, who, when, why
2. **Top risks** — the 5-7 highest-scoring failure modes with evidence
3. **Mitigation plan** — specific actions, owners, and triggers
4. **Monitoring plan** — what signals to watch during execution
5. **Decision log** — risks the team knowingly accepts and why

## Do NOT
- List only obvious risks — the value is in the non-obvious ones
- Skip assigning owners — unowned mitigations do not happen
- Treat this as a one-time exercise — revisit the pre-mortem at project milestones
- Confuse risk management with pessimism — the point is to ship successfully, not to find reasons not to ship
