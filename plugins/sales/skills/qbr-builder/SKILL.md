---
name: qbr-builder
description: Build quarterly business review presentations that demonstrate value, align on goals, and deepen the customer relationship. Use 2-3 weeks before scheduled QBR meetings.
triggers:
  - QBR
  - quarterly business review
  - business review
  - customer review
---

# QBR Builder

A QBR is not a product demo or a support recap. It is a strategic conversation about the customer's business outcomes and how your partnership drives them.

## Input Required

1. **Customer goals** — what they wanted to achieve this quarter (check previous QBR in `outputs/`)
2. **Usage data** — adoption metrics, feature usage, active users
3. **Support data** — ticket volume, resolution times, satisfaction scores
4. **Value metrics** — measurable outcomes tied to their goals
5. **Account context** — org changes, budget shifts, competitive activity
6. **Relationship data** — stakeholder map, engagement level, NPS responses

## QBR Structure

### Section 1 — Partnership Summary (2 min)

One slide. Set the frame for the conversation:

| Element | Content |
|---------|---------|
| **Relationship tenure** | [X months/years] |
| **Current investment** | [$ARR] |
| **Products/modules** | [What they use] |
| **Key stakeholders** | [Names and roles in the meeting] |
| **This quarter's focus** | [Agreed goals from last QBR] |

### Section 2 — Goals and Outcomes (10 min)

For each goal set last quarter:

| Goal | Target | Actual | Status | Evidence |
|------|--------|--------|--------|---------|
| [Goal 1] | [Metric] | [Metric] | ✅/⚠️/❌ | [Data source] |
| [Goal 2] | | | | |

For each goal, prepare a brief narrative:
- What was the goal?
- What did we do together to pursue it?
- What was the measurable result?
- What did we learn?

### Section 3 — Usage and Adoption (5 min)

| Metric | Last Quarter | This Quarter | Change | Benchmark |
|--------|-------------|-------------|--------|-----------|
| Active users | | | | [vs. similar customers] |
| Feature adoption | | | | |
| Key action frequency | | | | |
| Time in product | | | | |

Highlight:
- Features they should be using but are not
- Adoption trends (growing, flat, declining)
- Power users who could champion expansion

### Section 4 — Support and Health (3 min)

| Metric | Value | Trend | Context |
|--------|-------|-------|---------|
| Tickets opened | | | |
| Avg resolution time | | | |
| CSAT score | | | |
| Open issues | | [List any P1/P2] | |

### Section 5 — Value Delivered (10 min)

This is the most important section. Quantify the value:

| Value Area | Metric | Impact | Dollar Value |
|-----------|--------|--------|-------------|
| [Time saved] | [Hours/week] | [Total hours this quarter] | [$equivalent] |
| [Cost avoided] | | | |
| [Revenue enabled] | | | |
| [Risk reduced] | | | |

**Total estimated value delivered: $[Amount]**
**ROI: [Value ÷ Investment]x**

### Section 6 — Next Quarter Goals (10 min)

Propose 2-4 goals for the next quarter. Make them:
- **Specific** — tied to a measurable outcome
- **Relevant** — aligned with their stated business priorities
- **Achievable** — realistic given adoption and resources
- **Time-bound** — completable within the quarter

| Goal | Metric | Target | Actions Required | Owner |
|------|--------|--------|-----------------|-------|
| | | | | |

### Section 7 — Roadmap Preview (5 min)

Share upcoming features or capabilities relevant to their use case. Connect each to a customer need:

| Feature | Relevance to [Customer] | Timeline |
|---------|------------------------|----------|
| | | |

## Output Format

Save to `outputs/qbr-[customer]-[quarter]-[year].md`:

```markdown
# QBR — [Customer] — [Quarter] [Year]

## Executive Summary
[3 sentences: what we achieved, what matters most, what's next]

## Goals Review
[Table with status]

## Value Delivered
[Quantified impact]

## Next Quarter Goals
[Proposed goals with metrics]

## Appendix
[Detailed data tables, usage charts, support log]
```

## Principles

- Spend 60% of the QBR looking forward, 40% looking back. The customer already lived the past quarter. They want to know what is next.
- Bring insights the customer does not already have. Benchmark them against similar companies. Surface usage patterns they have not noticed.
- End with agreed next steps and owners. A QBR without action items was a presentation, not a partnership conversation.
