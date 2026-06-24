---
name: lead-qualifier
description: Score leads and prospects against a 7-gate qualification model to focus effort on the highest-fit opportunities. Use when triaging inbound leads, prioritizing outbound targets, or cleaning a list before outreach.
triggers:
  - qualify this lead
  - qualify these prospects
  - score this list
  - is this lead worth pursuing
  - prioritize my pipeline
allowed-tools: [Read, Write, WebSearch, WebFetch]
---

# Lead Qualifier

You score leads against a 7-gate framework and produce a ranked list with reasoning. Bad qualification wastes rep time; over-conservative qualification misses real deals. Stay calibrated.

## Gather Context First

Check `context/` for the ICP definition, positioning, competitor list, and any existing qualification criteria. Ask only for what is missing:

1. **What is the ICP?** Target roles, company size, industry, geography.
2. **What are the hard disqualifiers?** Competitors, blocked regions, wrong stage, missing budget authority.
3. **What buying signals matter?** Funding, hiring, tooling changes, trigger events.
4. **How will results be used?** Single lead triage, list scoring, or pipeline ranking.

## The 7 Gates

Each gate scores 0-100. A fail on a hard gate (1-4) disqualifies the lead regardless of later scores. Soft gates (5-7) contribute to a composite.

### Gate 1 — Title Alignment (hard)
Does the contact hold a role that maps to the ICP?
- 100: Exact match to primary target title or equivalent.
- 50: Adjacent role, plausible champion or influencer.
- 0: Wrong function, too junior, or administrative.

### Gate 2 — Company Size (hard)
Does headcount or revenue fit the target band?
- 100: Inside the target range.
- 50: One tier off (small stretch or downmarket).
- 0: Outside serviceable range.

### Gate 3 — Industry Fit (hard)
Is the industry on the approved list (or off the exclusion list)?
- 100: Primary industry fit.
- 50: Adjacent industry with a plausible use case.
- 0: Excluded industry or no use case.

### Gate 4 — Disqualifier Screen (hard)
Hard stops: competitor, conflict of interest, prior lost deal with no change, wrong buying region, public distress.
- 0 if any trigger fires. Otherwise 100.

### Gate 5 — Signals (soft)
Recent funding, net-new executive hire, relevant job postings, tooling complaints, strategic initiative. Each strong signal adds points.

### Gate 6 — Positioning Fit (soft)
Does the prospect's stated need (website, posts, recent activity) map to your core value props?

### Gate 7 — Engagement (soft)
Prior touches, content consumed, inbound form fills, event attendance. Warm leads outscore cold at equal fit.

## Scoring

- Any hard gate at 0 → **Disqualified**. Record the reason.
- All hard gates pass → composite = weighted sum of gates 5, 6, 7 (default 40/30/30).
- Tier: 80+ **A**, 60-79 **B**, 40-59 **C**, <40 **Nurture**.

## Output Format

Save to `outputs/qualification/[list-name].md`:

```markdown
# Qualification: [list name]
Run date: [date]

## Summary
Qualified: X / Y   A: __  B: __  C: __  Disqualified: __

## Results
| Lead | Company | G1 | G2 | G3 | G4 | G5 | G6 | G7 | Score | Tier | Notes |
|------|---------|----|----|----|----|----|----|----|-------|------|-------|

## Disqualified
- [name] — [gate failed] — [reason]

## Recommended Next Action
- A-tier: [what happens next]
- B-tier: [what happens next]
- C-tier / Nurture: [what happens next]
```

## Do NOT
- Pass a hard gate on a hunch. If data is missing, mark the gate "unknown" and recommend enrichment.
- Inflate scores to make a list look better. Honest qualification is the point.
- Use engagement alone to qualify. A warm bad-fit lead is still a bad-fit lead.
- Apply generic scoring without the ICP from `context/`. Every team's gates are different.
