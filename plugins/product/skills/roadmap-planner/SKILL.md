---
name: roadmap-planner
description: Build prioritized roadmaps with clear timelines, dependencies, and trade-offs. Use when planning product releases, project milestones, or quarterly OKRs.
triggers:
  - build roadmap
  - quarterly planning
  - prioritize features
---

# Roadmap Planner

Build roadmaps that balance ambition with reality. A roadmap is a communication tool that shows what you plan to do and why. It is not a commitment to specific dates.

## Phase 1 — Input Collection

Before prioritizing, gather all inputs:

### Strategic Inputs
- **Company/product OKRs** — What outcomes are we targeting this period?
- **Vision** — Where are we going in 12-18 months? Check `context/project-vision.md` if available
- **Constraints** — Budget, headcount, technical debt, regulatory deadlines

### Evidence Inputs
| Source | What to Extract | Where to Find |
|--------|----------------|---------------|
| Customer feedback | Top pain points, feature requests with frequency | Support tickets, sales calls, NPS comments |
| Usage data | Underused features (cut or improve?), adoption patterns | Analytics dashboard |
| Competitive intel | Gaps vs. competitors, differentiation opportunities | `context/` competitor analysis files |
| Technical debt | Risks that slow delivery, stability concerns | Engineering retrospectives, incident reports |
| Stakeholder requests | Internal needs from sales, support, marketing | Stakeholder interviews |

## Phase 2 — Prioritization

### The RICE Framework
Score each initiative on four dimensions:

| Factor | Definition | Scale | Formula |
|--------|-----------|-------|---------|
| **Reach** | How many users/customers affected per quarter? | Actual number estimate | |
| **Impact** | How much will it move the target metric per user? | 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal | |
| **Confidence** | How sure are we about reach and impact? | 100% = high, 80% = medium, 50% = low | |
| **Effort** | Person-months to complete | Actual estimate | |

```
RICE Score = (Reach x Impact x Confidence) / Effort
```

### Prioritization Matrix

| Initiative | Reach | Impact | Confidence | Effort | RICE Score | Strategic Fit | Final Priority |
|-----------|-------|--------|-----------|--------|-----------|--------------|---------------|
| [Name] | [N] | [0.25-3] | [50-100%] | [Person-months] | [Score] | [H/M/L] | [P1/P2/P3] |

**Strategic Fit Override:** RICE scores are a starting point. A high-scoring initiative that does not align with the current strategy may be deprioritized. A moderate-scoring initiative that directly supports a key OKR may be elevated. Document the rationale for every override.

**Alternative frameworks when RICE doesn't fit:** ICE (Impact x Confidence x Ease), MoSCoW (Must/Should/Could/Won't), Kano Model (Basic/Performance/Delighter), or Weighted Scoring (custom factors).

## Phase 3 — Dependency Mapping

Before sequencing, map dependencies between initiatives:

```
[Initiative A] ──blocks──> [Initiative B]
[Initiative C] ──depends on──> [External: API v3 release]
[Initiative D] ──shares resource with──> [Initiative E]
```

Identify:
- **Hard dependencies** — B literally cannot start until A is complete
- **Soft dependencies** — B is easier after A but could proceed independently
- **Resource conflicts** — Two initiatives need the same team at the same time
- **External dependencies** — Items blocked by third parties, customers, or events

## Phase 4 — Roadmap Construction

### Time Horizons
Use confidence-appropriate time horizons:

| Horizon | Timeframe | Commitment Level | Detail Level |
|---------|-----------|-----------------|-------------|
| **Now** | This sprint/month | High — committed, work in progress | Specific deliverables, owners, status |
| **Next** | Next 1-2 months | Medium — planned, may shift | Initiative scope and dependencies |
| **Later** | This quarter | Low — directional, will change | Initiative themes and open questions |
| **Future** | Beyond this quarter | Aspirational — no commitment | Strategic bets and exploration areas |

### Roadmap Document Structure

```
## Roadmap: [Period] — [Team/Product Name]

### Theme: [One sentence describing the overarching goal for this period]

### OKR Alignment
| OKR | Key Roadmap Initiatives |
|-----|----------------------|
| [Objective 1] | [Initiative A, Initiative B] |
| [Objective 2] | [Initiative C] |

### Now (In Progress)
| Initiative | Owner | Status | Target Date | Dependency |
|-----------|-------|--------|------------|-----------|
| [Name] | [Name] | On Track / At Risk | [Date] | [None / Blocked by X] |

### Next (Planned)
| Initiative | RICE Score | Dependency | Open Questions |
|-----------|-----------|-----------|---------------|
| [Name] | [Score] | [What blocks it] | [Unresolved decisions] |

### Later (Directional)
| Initiative | Strategic Rationale | Confidence | What Must Be True |
|-----------|-------------------|-----------|-------------------|
| [Name] | [Why this matters] | [H/M/L] | [Conditions for this to happen] |

### Not Doing (Explicit Exclusions)
| Initiative | Why Not Now | Revisit When |
|-----------|-----------|-------------|
| [Name] | [Rationale] | [Trigger condition] |
```

## Phase 5 — Communication

Create audience-specific views: executives see themes and OKR alignment, engineering sees dependencies and sequencing, sales sees customer impact and timelines. A roadmap without context is a promise, so always include the "why" behind priorities and the confidence level of each item.

## Output Format

Save to `plans/roadmap-[period].md` with the full roadmap document structure above, plus:
- Prioritization matrix showing scoring for all considered initiatives
- Dependency map
- "Not doing" list with rationale
- Communication plan for each audience

## Do NOT
- Commit to specific dates beyond the "Now" horizon — use ranges or "Q2" instead of "March 15"
- Present a roadmap as a promise — it is a plan that will change as you learn more
- Skip the "why" behind prioritization decisions — stakeholders need to understand the trade-offs
- Build a roadmap without input from engineering on effort estimates — top-down roadmaps fail on execution
- Forget the "not doing" list — knowing what you said no to is as important as knowing what you said yes to
- Prioritize by loudest stakeholder — use a consistent framework and document overrides
