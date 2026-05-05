---
name: conflict-resolution
description: Mediate interpersonal disputes between employees, between teams, or between manager and direct report. Structured framework for diagnosis, conversation, resolution, and follow-up. Use when user mentions conflict resolution, team conflict, mediation, or how to handle a disagreement.
triggers:
  - conflict resolution
  - team conflict
  - mediate dispute
  - resolve disagreement
  - interpersonal issue
  - manager-employee conflict
---

# Conflict Resolution

Help a manager (or HR partner) work through a workplace conflict. This is sensitive work — mistakes leave lasting damage. Default to caution and humility.

## When NOT to use this skill

This skill helps with everyday interpersonal conflict (style differences, missed expectations, communication breakdowns). It is NOT appropriate for:
- Harassment, discrimination, or any conduct that may be illegal — escalate to HR/legal immediately.
- Performance management dressed up as conflict — that's a different skill (`performance-review-writer`).
- Active threat or safety concerns — escalate to HR/security.

If any of these surface during a conflict conversation, stop the mediation and escalate.

## Gather context

Ask if not provided:

1. **Who's involved?** Two individuals, a team, manager-and-report, cross-team?
2. **What's the surface issue?** What's been said or done?
3. **What's the impact?** Work blocked, trust eroded, retention risk?
4. **History?** First incident, repeat pattern, or longstanding tension?
5. **Power dynamics?** Same level, manager-report, senior-junior?
6. **Who's the user's role?** Manager of one party, manager of both, HR partner, peer, exec?

Listen for emotion words ("frustrated", "fed up", "blindsided"). They signal what the conversation is really about.

## The mediation framework

### Step 1: Separate symptom from cause
Most surface disagreements ("they missed the deadline") map to deeper issues ("I don't trust their judgment", "I felt excluded from the decision"). Help the user identify the real underlying issue before designing the conversation.

Common patterns:
- **Style mismatch** — one person values speed, the other values rigor. Both are right.
- **Unclear ownership** — two people each thought they owned the decision.
- **Untold expectations** — one person expected something the other didn't know about.
- **Trust erosion** — repeated small disappointments compound.
- **Status / credit** — visible work was reassigned or attributed to someone else.
- **Identity** — perceived disrespect of background, role, or expertise.

### Step 2: Plan the conversation
- **Who's in the room?** Just the two parties + mediator? Or one-on-ones first?
- **Where?** Neutral ground (not one party's office or favorite cafe).
- **When?** Not late Friday, not before someone's vacation, not during a stressful project crunch.
- **How long?** 60-90 minutes. Hard stop.
- **Ground rules?** Each person speaks uninterrupted. No interrupting, no eye-rolling. Agree to confidentiality.

### Step 3: Run the conversation
Use a four-act structure:

1. **Frame** (5 min) — mediator opens, restates the goal ("We're here to understand each other and agree on next steps."), confirms ground rules.
2. **Listen** (30-40 min) — each party explains their experience without interruption. Mediator asks clarifying questions. No defending or reacting allowed.
3. **Negotiate** (20-30 min) — surface what each person needs going forward. Look for overlap. Make agreements specific and time-bound.
4. **Close** (5-10 min) — recap agreements, schedule follow-up.

### Step 4: Follow up
- One-on-one check with each party 1 week later: how's it going?
- Joint check-in 1 month later: still working, or new issues?
- If unresolved after 6-8 weeks of effort, escalate.

## Output format

Save planning notes (before the conversation) to `outputs/conflict-resolution/<date>-<participants>-plan.md`:
- Surface issue + deeper cause hypothesis.
- Conversation plan (where, when, who).
- Talking points for the mediator.
- Pre-conversation prep with each party.

Save outcomes (after the conversation) to `outputs/conflict-resolution/<date>-<participants>-outcome.md`:
- What was agreed.
- Follow-up dates.
- Whether escalation is needed.

These files are sensitive. The user should store them in a private notes location and not commit to a shared repo.

## Common mistakes

- Skipping the diagnosis step. Mediating the wrong issue makes it worse.
- Letting one party dominate. The mediator's job is to balance speaking time.
- Forcing a hug-it-out resolution. Sometimes "we agree to disagree on style; here are the working norms" is the right outcome.
- No follow-up. Conversations don't fix things; behavior change does.
- Confusing conflict resolution with feedback. Feedback is delivered. Conflict requires negotiation.

## Cross-references

For documenting performance issues that need formal addressing (separate from conflict), use `performance-review-writer`. For team-wide health and engagement signals, use `employee-survey-analyst`. For broader org culture work, use `culture-architect` (when added). For policies that prevent conflict (e.g., expectations docs), use `policy-writer` and `sop-writer`.
