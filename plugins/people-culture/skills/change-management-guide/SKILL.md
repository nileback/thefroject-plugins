---
name: change-management-guide
description: Plan organizational changes with communication strategies and rollout plans. Use when introducing new tools, restructuring, changing processes, or rolling out policies.
triggers:
  - change management
  - organizational change
  - rollout plan
---

# Change Management Guide

Plan organizational changes so people adopt them instead of resisting. Use the ADKAR framework (Awareness, Desire, Knowledge, Ability, Reinforcement) as the core methodology.

## Phase 1 — Change Assessment

Before planning communication or rollout, assess the change:

### Impact Analysis
| Dimension | Current State | Future State | Delta | Affected Groups |
|-----------|-------------|-------------|-------|----------------|
| Process | [How it works now] | [How it will work] | [What changes] | [Who] |
| Tools | [Current tools] | [New tools] | [What changes] | [Who] |
| Roles | [Current structure] | [New structure] | [What changes] | [Who] |
| Skills | [Current requirements] | [New requirements] | [Training gap] | [Who] |

### Change Severity Score
Rate each factor 1-5:
- **Scope** — How many people are affected?
- **Depth** — How much does their daily work change?
- **Speed** — How quickly must the change happen?
- **History** — How much change fatigue exists?

Total score determines the approach:
- **4-8:** Light touch (announcement + resources)
- **9-14:** Moderate (structured rollout with training)
- **15-20:** Heavy (phased rollout with champions, training, and ongoing support)

## Phase 2 — Stakeholder Mapping

Map every affected group using the influence/impact matrix:

```
            High Influence
                 |
    MANAGE       |      ENGAGE
    CLOSELY      |      ACTIVELY
                 |
Low Impact ------+------ High Impact
                 |
    MONITOR      |      KEEP
    (minimal)    |      INFORMED
                 |
            Low Influence
```

For each stakeholder group, document:
| Group | Impact Level | Influence | Current Sentiment | WIIFM | Key Concern |
|-------|-------------|-----------|------------------|-------|-------------|
| [Name] | H/M/L | H/M/L | Supportive/Neutral/Resistant | [What's in it for them] | [Primary worry] |

**Critical:** Identify 2-3 change champions per affected team. These are respected peers (not managers) who can model the new behavior and provide frontline support.

## Phase 3 — ADKAR Planning

For each stakeholder group, plan actions across all five ADKAR stages:

| Stage | Question | Key Action | Channel |
|-------|----------|-----------|---------|
| **Awareness** | Why is this change happening? | Share data-backed business case; connect to problems the audience recognizes | All-hands, email, 1:1s |
| **Desire** | What's in it for me? | Address personal impact per group; acknowledge what is lost; surface early adopter wins | Team meetings, champions |
| **Knowledge** | How do I operate in the new way? | Training (format, duration, schedule), reference materials, sandbox environment | Workshops, docs, video |
| **Ability** | Can I actually do this? | Hands-on practice, peer mentoring from champions, accessible help (office hours, Slack) | Pairing sessions, help desk |
| **Reinforcement** | Is this the new normal? | Celebrate milestones, remove revert option at the right time, add to onboarding | Public channels, performance reviews |

## Phase 4 — Communication Plan

### Communication Sequence
| Timing | Audience | Channel | Message | Owner |
|--------|---------|---------|---------|-------|
| T-4 weeks | Leadership | 1:1 meetings | Full briefing + talking points | Change sponsor |
| T-3 weeks | Change champions | Workshop | Deep dive + role expectations | Change lead |
| T-2 weeks | Directly affected | Team meetings | What, why, timeline, Q&A | Managers (with talking points) |
| T-1 week | Broader org | Email/all-hands | Summary announcement | Change sponsor |
| Launch day | All | Multiple channels | Go-live message + resources | Change lead |
| T+1 week | Directly affected | Check-in survey | Pulse check, collect issues | Change lead |
| T+2 weeks | All | Email update | Progress, fixes, wins | Change sponsor |
| T+1 month | All | All-hands | Results and recognition | Change sponsor |

### Message Framework
Every communication answers these four questions:
1. What is changing? (specific, not vague)
2. Why is it changing? (honest, data-supported)
3. How does it affect me? (personalized by audience)
4. Where do I go for help? (specific channel, person, or resource)

## Phase 5 — Rollout Execution

Choose a rollout strategy based on the severity score:

| Strategy | When to Use | Risk | Speed |
|----------|------------|------|-------|
| Big bang | Low complexity, urgent | Higher | Fast |
| Phased (by team) | Moderate complexity | Medium | Medium |
| Pilot then expand | High complexity, uncertain | Lower | Slow |
| Parallel run | Critical systems | Lowest | Slowest |

### Rollback Criteria
Define in advance: "We will pause or roll back if [specific measurable condition]." This builds confidence and shows that feedback matters.

## Phase 6 — Measurement

Track adoption using leading and lagging indicators:

| Metric | Measure | Target | Frequency |
|--------|---------|--------|-----------|
| Awareness | Survey: "Do you know about the change?" | >90% | Week 1 |
| Adoption | % using the new process/tool | >80% | Weekly |
| Proficiency | Error rate or time-on-task | Back to baseline | Monthly |
| Satisfaction | Pulse survey score | >3.5/5 | Bi-weekly then monthly |
| Business outcome | [The metric that justified the change] | [Target] | Monthly |

## Output Format

Save to `outputs/change-plan-[change-slug].md` with:

- Change assessment and severity score
- Stakeholder map with WIIFM statements
- ADKAR plan by stakeholder group
- Communication calendar
- Rollout timeline with rollback criteria
- Measurement dashboard

## Do NOT
- Announce a change without first briefing the people most affected
- Assume silence means agreement — it usually means confusion or resignation
- Skip the "what's in it for me" message for any stakeholder group
- Roll out a change without defining what success looks like
- Treat change management as a one-time announcement — it is an ongoing process
- Ignore resistance — it contains valuable information about risks you may have missed
