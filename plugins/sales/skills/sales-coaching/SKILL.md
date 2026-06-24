---
name: sales-coaching
description: Coach reps through call reviews, email teardowns, ride-alongs, and structured 1:1s. Manager-side companion to sales skills. Use when user mentions sales coaching, call review, rep development, ride-along, deal coaching, or improving a rep's performance.
triggers:
  - sales coaching
  - call review
  - rep development
  - email teardown
  - ride-along
  - 1:1 with rep
---

# Sales Coaching

Coach a sales rep through structured review of their actual work — calls, emails, deal motions. The goal is changed behavior, not abstract advice.

## Gather context

Ask if not provided:

1. **Rep tenure** — onboarding (under 90 days), ramping (3-6 months), tenured. Different coaching emphases.
2. **Current performance** — quota attainment, top-of-funnel activity, conversion rates per stage.
3. **What's the trigger?** — quota miss, specific deal lost, coaching request, regular cadence?
4. **Existing coaching cadence** — weekly 1:1, monthly skill review, quarterly career conversation?
5. **Source material** — call recordings, email threads, deal docs?

## The four formats

Coaching takes different shapes for different problems:

### 1. Call review (after the fact)
Listen to (or read transcript of) a real call. Use this rubric:

- **Open** — did the rep set the agenda, get permission, and earn the right to ask hard questions?
- **Discovery** — open vs. closed questions ratio, depth of follow-ups, surfaced both pain and impact.
- **Listen-talk ratio** — rep should be talking 30-40%, not 70%.
- **Demo or pitch** — tailored to what was learned in discovery, not canned.
- **Objection handling** — acknowledged, asked for clarification, addressed root cause.
- **Next steps** — concrete, time-bound, agreed by both parties.

Pick 1-2 areas to focus on. Don't overwhelm.

### 2. Email teardown
Pull a recent prospecting or follow-up email. Score it on:

- Subject line — specific, intriguing, not "Quick question".
- Opening — references something specific to the prospect (not "I came across your company").
- Value claim — single, specific, evidence-backed.
- CTA — single, concrete, low-friction (15-min call > demo).
- Length — under 100 words for cold outreach, under 250 for follow-ups.

Have the rep rewrite based on the feedback. Compare A/B.

### 3. Ride-along (live observation)
Sit in on a live call (or virtual call). Take notes against the call review rubric. Debrief within 60 minutes — feedback fades fast.

### 4. Deal coaching (working a specific deal)
Use the rep's deal as the case study. Walk through:
- Current state (stage, last activity, next step, blockers).
- Champion strength (who's selling internally for you?).
- Decision criteria (what does "won" require?).
- Competition (who else is in the deal? What's their advantage?).
- Risk register (top 3 things that could derail this).
- Next 2 weeks of plays.

## Cadence

For a typical 8-rep team:
- **Daily** — standup (5 min), review hot deals.
- **Weekly 1:1** (30 min) — deal coaching + skill focus from the prior week's call/email review.
- **Monthly skill review** (60 min) — listen to 2 calls, teardown 5 emails, set the next month's focus.
- **Quarterly career conversation** (60 min) — broader trajectory, strengths, growth, comp.

Adapt by tenure: ramping reps need 2x weekly cadence; tenured reps can drop to bi-weekly.

## Tracking change

Coaching only works if you track behavior change. After each session:

```
## Rep: <name> | <date>
## Focus areas this period
1. <skill> -> evidence-based example, what to change, how to measure
2. <skill> -> ...

## Last period's focus — progress check
1. <prior focus> -> <observed change / no change / regressed>
```

If a focus area shows no progress over 2-3 cycles, the issue is deeper than skill (motivation, fit, process). Address the actual problem.

## Output format

Save coaching notes to `outputs/sales-coaching/<rep-name>/<date>.md` per session. Roll up a quarterly view per rep at `outputs/sales-coaching/<rep-name>/quarterly-<Q>.md` with theme tracking.

## Common mistakes

- Generic feedback ("be more consultative"). Useless. Be specific to the call, the line, the moment.
- Too many focus areas at once. Pick 1-2.
- Coaching only when there's a problem. The best reps need coaching to stay sharp.
- Teaching from your own playbook only. Top reps have different motions; respect what's working.
- No follow-through. If you said you'd listen to next week's call, do it.

## Cross-references

For pipeline-level patterns that drive coaching themes, use `sales-pipeline`. For the cold outreach itself, use `cold-email-writer` and `sales-outreach-writer`. For the manager-side pipeline review motion, use `sales-pipeline`. For onboarding ramping reps, use `onboarding-designer`.
