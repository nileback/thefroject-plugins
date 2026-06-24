---
name: org-health-diagnostic
description: Synthesize multiple data sources (pulse surveys, retention, Glassdoor, exit interviews, comp benchmarks) into a leadership-level organizational health assessment. The CHRO/CEO view distinct from employee-survey-analyst (HR-tactical).
triggers:
  - org health
  - organizational diagnostic
  - leadership health check
  - is the team healthy
  - culture diagnostic
  - org assessment
---

# Org Health Diagnostic

A leadership-level synthesis of organizational health. Distinct from `employee-survey-analyst` (which works one survey at a time) — this skill pulls multiple signals together into a board-ready assessment.

## Gather context

Ask if not provided:

1. **Trigger** — annual review, board prep, post-incident, post-restructuring, founder concern?
2. **Available data sources** — eNPS, pulse surveys, exit interviews, Glassdoor, retention data, comp benchmarks, productivity metrics?
3. **Time horizon** — last quarter, last year, multi-year trend?
4. **Audience** — CEO, board, exec team, full company?
5. **Specific questions** — anything in particular leadership wants answered?

## Sources to pull from

### Quantitative
- **eNPS / pulse survey scores** with trend over 4-8 quarters.
- **Retention / attrition** rates, broken down by tenure cohort, function, role level, geography.
- **Engagement signals**: meeting attendance patterns, message volume, working-hours patterns.
- **Compensation benchmarks**: salary band positioning vs market, equity vesting status, recent retention grants.
- **Hiring / promotion data**: time-to-fill, internal promotion rate, manager hire-from-internal rate.
- **Glassdoor / Blind / Comparably**: scores, trend, themes.

### Qualitative
- **Pulse survey open-ends**: top themes from "what would you change."
- **Exit interview themes** (rolling 12 months).
- **Skip-level conversations** with senior leaders.
- **Manager 1:1 patterns** (themes managers are surfacing).
- **All-hands Q&A patterns**: what questions does the team keep asking?

## Synthesis framework

Map signals across five dimensions:

### 1. Trust in leadership
- Pulse survey: "I trust senior leadership to make good decisions" trend.
- Glassdoor: leadership ratings.
- Exit interviews: leadership-related themes.
- Indicator: trust drift > 5 points QoQ is a yellow flag.

### 2. Manager quality
- Pulse survey: "My manager helps me grow" / "My manager gives useful feedback."
- Retention: attrition rate by manager.
- Indicator: high-attrition managers drive significant org-level damage.

### 3. Strategic clarity
- Pulse survey: "I understand how my work connects to company goals."
- Q&A patterns: do the same strategic questions keep coming up?
- Indicator: clarity drops typically follow strategy shifts that weren't communicated well.

### 4. Compensation fairness
- Comp band positioning vs market.
- Pulse survey: "I'm fairly compensated for my work."
- Internal pay equity audit (gender, ethnicity, geography).
- Glassdoor / Blind salary commentary.
- Indicator: compensation issues compound silently and surface at retention crises.

### 5. Day-to-day experience
- Engagement patterns: are people working healthy hours?
- Burnout signals: PTO usage rates, sick day patterns.
- Recognition: pulse survey "My contributions are valued."
- Indicator: this dimension correlates strongly with retention 6-12 months out.

## Output: a leadership-level diagnostic

The deliverable is a 5-15 page assessment for the CEO/board. Structure:

```
## Org Health Diagnostic — <period>

## Headline
[2-3 sentences on overall state]

## Score by dimension
| Dimension | Score | Trend | Drivers |
|---|---|---|---|
| Trust in leadership | <N>/5 | up/flat/down | <key drivers> |
| Manager quality | <N>/5 | ... | ... |
| Strategic clarity | <N>/5 | ... | ... |
| Compensation fairness | <N>/5 | ... | ... |
| Day-to-day experience | <N>/5 | ... | ... |

## Strengths
[What's working — be specific, with evidence]

## Risks
[What's concerning — with severity rating]

## Hot spots
[Specific functions, locations, or cohorts in distress]

## Recommendations
[Prioritized actions for the next 1-2 quarters]

## Watchouts
[Leading indicators to monitor]
```

For each dimension and finding, cite the underlying data so leadership can dig deeper if they want.

## Frequency

Quarterly is standard for mature orgs. Semi-annually is acceptable in steady-state. Triggered diagnostics make sense after major events (layoff, leadership change, public incident).

## Common mistakes

- Single-source diagnostics. Pulse survey alone misses the bigger picture.
- No trend data. Single snapshots are misleading.
- Glossing over hot spots. The diagnostic loses credibility if it doesn't surface uncomfortable findings.
- Recommendations without owners. Assessment without action plan is theater.
- Too many recommendations. Pick 3-5 for a quarter; the rest waits.

## Cross-references

For employee-survey analysis (one survey at a time), use `employee-survey-analyst`. For broader culture work, use `culture-architect`. For leadership-team development implications, use `leadership-development`. For comp-related findings specifically, use `compensation-benchmarker`. For exit-interview synthesis, use `voc-synthesis` (adapted for employees) or `qualitative-analyst`. For board reporting on org health, use `board-deck-builder` and `board-report-builder`.
