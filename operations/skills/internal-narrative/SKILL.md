---
name: internal-narrative
description: Build the story leadership tells the company. Distinct from external positioning (what we tell customers) and internal-comms (specific announcements). The internal narrative is the through-line that connects strategy, decisions, and culture for employees.
triggers:
  - internal narrative
  - what story do we tell
  - all-hands narrative
  - town hall message
  - leadership story
  - internal positioning
---

# Internal Narrative

The story you tell the company about itself. Without one, every quarterly meeting is a list of things; with one, every meeting reinforces a coherent direction.

## Why it matters

The internal narrative does work the company depends on:

- **Hiring**: candidates evaluate the future they're joining.
- **Retention**: employees stay when the story still excites them.
- **Strategy alignment**: teams make consistent micro-decisions when they share the narrative.
- **Resilience**: when a quarter goes badly, the narrative explains the setback as part of a longer arc.
- **Culture transmission**: stories travel; values lists don't.

## Components of an internal narrative

A working internal narrative has five parts:

### 1. Where we came from
A short origin story. Not the marketing version; the human version. Founder context, why this problem matters, what was hard early.

### 2. Where we are now
Honest assessment. Wins (specific, recent), losses (specific, recent), what's working, what's not. Internal audiences detect spin instantly.

### 3. Where we're going
The 1-3 year picture. Not a financial target; a state of the world. "We'll be the default tool for X" is more durable than "we'll hit $50M ARR."

### 4. Why now (and why us)
Why this is the moment. Why this team can do it. Why competitors won't get there first.

### 5. What we'll be remembered for
The lasting impact. The reason joining this company will matter in 10 years.

## Distinguishing internal from external

External positioning is about what we tell customers. Internal narrative is about what we tell the team about ourselves.

They overlap — values consistent in both — but they differ:
- External is short, polished, specific to the buying decision.
- Internal is longer, more human, includes failures and context.

Most companies have a polished external positioning and a vague internal narrative. The result: employees don't know how to talk about the company beyond the website copy.

## When to refresh

The internal narrative needs refresh when:

- The company has hit a meaningful milestone (PMF, scale, profitability).
- Strategy has shifted (new market, new product, pivot).
- A wave of new hires has arrived who weren't there for the previous narrative.
- Engagement scores show drift (people don't know what they're working toward).
- The CEO finds themselves ad-libbing the company story differently each time.

Cadence: explicit refresh annually, with mini-updates each quarter.

## How to build it

### Step 1: Capture inputs
- Founder origin story (verbal interview).
- Last 12 months of wins and losses (concrete examples).
- Strategic direction (from the leadership team).
- Customer impact stories (specific, named).
- Cultural moments (defining events).

### Step 2: Draft the five components
Each section short. The whole narrative readable in 5-10 minutes.

### Step 3: Test with employees
Read it to a sample of employees. Watch their faces. Where do they perk up? Where do they zone out? Where do they push back?

### Step 4: Refine and version
Save it as an internal artifact. Reference it in:
- Onboarding (every new hire reads it).
- Quarterly all-hands (CEO references it explicitly).
- 1:1s when manager talks to the report about the bigger picture.
- Recruiting conversations (interviewees deserve to hear it).

## Output format

Save to `reference/internal-narrative.md` (lives long-term in the workspace). Structure:

```
# Internal Narrative — <Year>

## Where we came from
[Founder context and origin]

## Where we are now
[Honest assessment: wins, losses, position]

## Where we're going
[1-3 year picture]

## Why now, why us
[Timing and team uniqueness]

## What we'll be remembered for
[Long-term impact]

---
Last updated: <date>
Next refresh: <date>
```

For specific moments (all-hands, town halls), draft delivery scripts at `outputs/internal-narrative/<date>-<event>.md` that pull selectively from the master narrative.

## Common mistakes

- Over-polishing. Internal audiences want honesty, not marketing copy.
- Listing achievements without arc. Achievements get forgotten; the arc that connects them gets remembered.
- No mention of failures. Erodes trust quickly.
- Different stories from different leaders. Misalignment shows; team gets confused.
- Treating it as a one-time deliverable. It needs maintenance.

## Cross-references

For external positioning (what we tell customers), use `positioning-generator` and `messaging-hierarchy`. For specific internal announcements (rather than the over-arching story), use `internal-comms`. For the all-hands cadence and structure, see `chief-of-staff` workflow 3. For investor narrative (different audience again), use `investor-update-writer`.
