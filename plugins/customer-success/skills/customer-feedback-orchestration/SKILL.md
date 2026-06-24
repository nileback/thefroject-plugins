---
name: customer-feedback-orchestration
description: Design and run an end-to-end customer feedback program — surveys, in-app prompts, support tickets, social listening, then categorization, routing, and close-the-loop. Distinct from voc-synthesis which is one-shot. Use when user mentions feedback program, NPS pipeline, customer feedback loop, VoC operations, or feedback flywheel.
triggers:
  - feedback program
  - feedback loop
  - close the loop
  - nps pipeline
  - voc operations
  - customer feedback flywheel
---

# Customer Feedback Orchestration

Help the user build a continuous customer feedback program — not a one-time survey, but a system that captures, categorizes, routes, and closes the loop with customers across channels.

## Gather context

Ask if not provided:

1. **Current state** — what feedback do they collect today? (NPS, CSAT, support tickets, in-app prompts, social, sales calls, exit interviews)
2. **Tools** — survey tool, ticketing system, CRM, analytics. Don't recommend new tools unless current ones are missing capability.
3. **Volume** — customers, ARR, ticket volume, NPS responses per quarter.
4. **Goal** — product input? Retention diagnosis? Story collection for marketing? Specific decision (e.g., kill or invest in feature X)?
5. **Owner** — who runs this? (CS leader, product ops, founder, dedicated VoC role.)

## The four-stage pipeline

Every mature feedback program has these stages. Map current state to each:

### 1. Capture (where feedback enters)
- **Asked** — surveys (NPS quarterly, CSAT post-ticket, post-trial offboarding).
- **Volunteered** — in-app feedback button, support tickets, sales call notes, churn-survey responses.
- **Unprompted** — social mentions, review sites, podcasts, public Slack/Discord.

The mature program covers all three. Most companies only do one (usually surveys).

### 2. Categorize (what it's actually about)
Build a tagging schema with 3 levels:
- **Type**: bug, feature request, complaint, praise, question, churn signal.
- **Theme**: 8-15 product/journey themes (onboarding, billing, performance, integrations, etc.).
- **Severity**: blocker, major, minor.

Tag every piece of feedback within 48 hours of capture. Manual at low volume; AI-assisted at high volume (use the support categorization or qualitative-analyst skill).

### 3. Route (who acts on what)
Each tag combination has a default owner:
- Bug + blocker = engineering on-call.
- Feature request + popular theme = product PM.
- Praise = marketing (potential testimonial / case study lead).
- Churn signal = CS leader for save attempt.

Document routing in a one-page guide. Update quarterly.

### 4. Close the loop (tell the customer what happened)
This is what most programs miss. For every actionable piece of feedback:
- Acknowledge within 24h that you received it.
- Reply with what you'll do (or won't, and why).
- Follow up when the change ships.

Customers who get a "we fixed your thing" email after months of silence become evangelists.

## Output format

Save the program design to `outputs/feedback-orchestration/<date>-program.md` with:
- Capture inventory: every channel currently in use + recommended additions.
- Tagging schema (all three levels).
- Routing matrix (tag -> owner -> SLA).
- Close-the-loop templates (4-6 stock messages by feedback type).
- Reporting: monthly pulse on top themes, NPS trend, response rates.
- 90-day rollout plan if the program is greenfield.

## Common mistakes

- One-time NPS survey, no system around it.
- Tagging schema too granular (50 themes) — nobody can use it.
- No close-the-loop step. Customers stop submitting.
- Treating feedback as marketing (only collecting praise).
- Not weighting by customer tier — a feature request from your largest customer is not equal to one from a free user.

## Cross-references

For one-shot synthesis of existing feedback (no ongoing program), use `voc-synthesis`. For health scoring derived from this feedback, use `health-score-builder` and (when added) `value-realization-scorer`. For QBR-ready summaries, use `qbr-builder`. For the human side of categorization (NPS open-ends, qualitative), use `qualitative-analyst` and `review-miner`.
