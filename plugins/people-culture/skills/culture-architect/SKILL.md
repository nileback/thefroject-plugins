---
name: culture-architect
description: Design and maintain organizational culture as the company scales. Covers values articulation, behaviors, rituals, hiring filters, onboarding immersion, and culture monitoring. Distinct from dei-audit-guide which is compliance-focused. Use when user mentions company culture, scaling culture, values, culture deck, or rituals.
triggers:
  - company culture
  - scaling culture
  - culture values
  - culture deck
  - rituals
  - culture at scale
---

# Culture Architect

Help an org articulate, embed, and maintain its culture as it grows. Culture is what people do when no one is watching — and what they decide is "how we do things here." It's mostly invisible until it's broken.

## Gather context

Ask if not provided:

1. **Stage** — under 30, 30-100, 100-300, 300+. Different problems at each.
2. **What triggered the conversation?** — values feel hollow, new hires don't fit, two offices have different cultures, founder noticed people-managers diverging?
3. **Existing artifacts** — values document, culture deck, employee handbook? Read them first.
4. **Recent signals** — Glassdoor reviews, exit interviews, engagement scores, public mentions?
5. **Founder/CEO involvement** — culture without exec investment fades. How committed is leadership?

## Stage-by-stage challenges

| Stage | Primary challenge | Typical work |
|---|---|---|
| Under 30 | Culture is just "how the founders behave." Implicit. | Articulate it before it's diluted. |
| 30-100 | First diverse hires don't share founder context. Subcultures form. | Explicit values, hiring filters, onboarding. |
| 100-300 | Multiple offices or remote. Manager layer thickens. | Manager training, ritual design, culture champions. |
| 300+ | Culture is set. Drift is the enemy. | Monitoring, refresh, intentional sub-culture work. |

Match the program scope to the stage. Don't build 300-person infrastructure for a 40-person company.

## Values articulation

A working values document has 5-7 values, each with:
- **One word or short phrase** (the value name).
- **One sentence** explaining what it means.
- **A behavioral expansion** — what people DO when they live this value.
- **What it is NOT** — common misinterpretations.
- **An example or story** — a recent moment that exemplified it.

Values must be falsifiable. "We value excellence" is meaningless. "We ship before we think it's polished, then iterate based on usage" is a value.

Test each candidate value: can someone violate it? If no, it's not a value, it's a platitude.

## Behaviors and rituals

Values become real through behaviors. Behaviors become permanent through rituals. Examples by value:

- **Customer-first**: every all-hands opens with a customer story. Every PRD has a "customer impact" section.
- **Ship fast**: Friday demos. Public dashboard of weekly ships. "Done > perfect" as a hiring rubric.
- **Direct feedback**: monthly peer feedback round. Public retros. Manager 1:1s include "what should I do differently."

Pick 1-2 rituals per value. More than 2 dilutes.

## Hiring as the largest culture lever

The fastest way to change culture is changing hiring. The fastest way to maintain it is filtering.

- Embed values in interviewing (each value gets a behavioral question).
- Add a "culture-add" interviewer separate from skills interviewers (not "culture-fit" — that protects existing biases).
- Hold the bar visibly. The first false-positive hire after a values-aligned hire is a signal to everyone.

## Onboarding as the second-largest lever

First 30 days are when new hires learn "how we do things here." Use them.

- First-day exposure to values (with stories, not slides).
- First-week shadow rotations across teams.
- First-month buddy from a different team.
- First-quarter check on whether the new hire feels values-aligned. Ask explicitly.

## Monitoring (300+)

Once culture is set, drift is the risk. Monitor with:
- Quarterly engagement surveys with values-tied questions.
- Glassdoor + Blind reviews — read them, don't just report on them.
- Exit interview themes — what's the modal reason people leave?
- New-hire 90-day surveys ("did the company match what was described in interviews?").

## Output format

For values articulation: `outputs/culture/values.md` with the 5-7 values, behavioral expansions, and stories.

For program design: `outputs/culture/<initiative>.md` with goal, audience, timeline, rituals introduced, success metrics.

For monitoring: `outputs/culture/monitor-<quarter>.md` with engagement results, Glassdoor themes, exit themes, and the next quarter's culture work.

## Common mistakes

- Naming values that nobody could disagree with ("integrity", "respect"). Generic = unenforceable.
- Designing rituals founders don't participate in. They die quietly.
- Treating culture as something HR owns. Culture is everyone's, especially the CEO's.
- Refreshing values too often. Pick them once, live with them for years.
- Confusing perks with culture. Free lunch is not a culture; how decisions get made is.

## Cross-references

For DEI-specific work (compliance, inclusion programs), use `dei-audit-guide`. For onboarding design specifically, use `onboarding-designer`. For employee engagement signal analysis, use `employee-survey-analyst`. For internal communications that reinforce culture, use `internal-comms`. For org design and reporting structure, use `org-designer`.
