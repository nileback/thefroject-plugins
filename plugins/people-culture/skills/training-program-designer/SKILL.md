---
name: training-program-designer
description: Design structured training programs with learning objectives, content modules, delivery methods, assessment criteria, and success metrics. Use when building onboarding programs, upskilling initiatives, or role-specific training paths.
triggers:
  - training program
  - learning path
  - upskilling plan
  - onboarding program
  - training design
---

# Training Program Designer

Build training programs that change behavior, not just transfer information. The measure of a good program is what people do differently afterward.

## Input Required

1. **Training need** — what gap are you addressing (skills assessment, role requirement, compliance)
2. **Target audience** — who will participate, their current skill level, learning preferences
3. **Business goal** — what business outcome should improve as a result
4. **Constraints** — timeline, budget, technology, participant availability
5. **Existing resources** — current training materials, SME availability, tools

## Program Design Process

### Step 1 — Needs Analysis

| Element | Detail |
|---------|--------|
| **Current state** | [What can participants do now?] |
| **Desired state** | [What should they be able to do after?] |
| **Gap** | [Specific skills or knowledge missing] |
| **Root cause** | [Is training the right solution? Or is it a process/tool/incentive issue?] |
| **Business impact** | [What improves when this gap is closed?] |

### Step 2 — Define Learning Objectives

Write objectives using the formula: **By the end of this [module/program], participants will be able to [observable action] [to what standard] [under what conditions].**

| Module | Learning Objective | Bloom's Level | Assessment Method |
|--------|-------------------|-------------|------------------|
| [Module 1] | [Objective] | Remember/Understand/Apply/Analyze/Evaluate/Create | [How you verify] |
| [Module 2] | | | |

### Step 3 — Design the Learning Path

| Week | Module | Topic | Format | Duration | Pre-work | Assessment |
|------|--------|-------|--------|----------|---------|-----------|
| 1 | Foundations | [Topic] | [Live/Self-paced/Blended] | [Hours] | [Reading/video] | [Quiz/exercise] |
| 2 | Core skills | [Topic] | | | | |
| 3 | Practice | [Topic] | | | | |
| 4 | Application | [Topic] | | | | |

**Format options and when to use them:**

| Format | Best For | Engagement Level | Cost |
|--------|---------|-----------------|------|
| Self-paced e-learning | Knowledge transfer, compliance, large audiences | Low-Medium | Low per learner |
| Live workshop | Skill practice, discussion, complex topics | High | Medium |
| Coaching/mentoring | Behavior change, leadership, nuanced skills | Very high | High per learner |
| Job shadowing | Process learning, role transitions | High | Low (just time) |
| Simulations/role-play | Sales, customer interaction, crisis response | Very high | Medium |
| Peer learning groups | Knowledge sharing, problem solving | Medium-High | Low |

### Step 4 — Content Development

For each module, outline:

| Element | Content |
|---------|---------|
| **Hook** | [Why should they care? Real scenario or problem] |
| **Concepts** | [Key information to convey — aim for 3-5 main points] |
| **Examples** | [Real scenarios from your organization] |
| **Practice** | [Hands-on exercise that applies the concepts] |
| **Assessment** | [How you verify learning happened] |
| **Resources** | [Reference materials for later use] |

### Step 5 — Success Metrics (Kirkpatrick Model)

| Level | Question | Metric | Method | When |
|-------|---------|--------|--------|------|
| **1 — Reaction** | Did they find it valuable? | Satisfaction score, NPS | Post-training survey | Immediately after |
| **2 — Learning** | Did they learn it? | Assessment scores, skill demos | Quiz, practical assessment | End of training |
| **3 — Behavior** | Are they using it? | Behavior observation, manager feedback | Check-ins, 360 review | 30-90 days after |
| **4 — Results** | Did it impact the business? | [Specific business KPI] | Data analysis | 90-180 days after |

## Output Format

Save to `outputs/training-program-[name].md`:

```markdown
# Training Program — [Name]
**Audience:** [Who] | **Duration:** [Timeline] | **Format:** [Delivery method]

## Business Case
[Why this program exists and what it should achieve]

## Learning Objectives
[Numbered list]

## Program Schedule
[Week-by-week module table]

## Module Outlines
[Content plan for each module]

## Assessment Plan
[How learning is measured at each level]

## Success Metrics
[KPIs with targets and measurement timeline]

## Resources Required
| Resource | Purpose | Cost | Status |
|----------|---------|------|--------|
```

## Principles

- Adults learn by doing, not by listening. Every module should include practice.
- Training without reinforcement decays within 30 days. Plan for follow-up touchpoints.
- If you cannot articulate the business outcome, question whether training is the solution. Many performance problems are caused by unclear expectations, broken processes, or misaligned incentives, not lack of knowledge.
