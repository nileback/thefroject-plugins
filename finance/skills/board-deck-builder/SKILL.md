---
name: board-deck-builder
description: Build a board meeting deck — visual slide-formatted update with metrics, narrative, key decisions, risks. Distinct from board-report-builder (narrative document). For the slide file production use pptx-handler. Use when user mentions board deck, board meeting deck, board update slides, or quarterly board materials.
triggers:
  - board deck
  - board meeting deck
  - board update slides
  - quarterly board materials
  - board presentation
---

# Board Deck Builder

Build a board meeting deck that gets the board engaged on the right things. The deck is the artifact; the meeting is the goal. A well-built deck makes the meeting useful.

## Gather context

Ask if not provided:

1. **Stage** — seed, Series A/B/C, growth, mature? Different boards expect different rigor.
2. **Board composition** — VC investors, independent directors, founder, customers? Affects tone and detail.
3. **Last meeting** — what did the board ask about? What's pending?
4. **Cadence** — quarterly is standard; some companies do every 6 weeks during active fundraising.
5. **Strategic moment** — fundraise prep, pivot, expansion, layoff? Affects the narrative arc.
6. **Length budget** — typical 25-40 slides for a 2-hour meeting.

## Standard structure

Most board decks follow a 6-section structure. Adapt order and emphasis based on the strategic moment.

### Section 1: Executive summary (1-2 slides)
- Top-of-mind: 3-5 bullets on what's most important right now.
- Asks: what specifically does the team want from the board this meeting? Decisions, intros, advice.

### Section 2: Metrics dashboard (3-5 slides)
- Headline metric chart (ARR, MRR, GMV, active users — whatever the company runs on).
- Pipeline / commercial metrics.
- Customer metrics (NPS, retention, expansion).
- Team metrics (headcount vs plan, attrition).
- Cash and runway.

Each slide: one chart, headline takeaway at the top, brief commentary at the bottom. No walls of numbers.

### Section 3: Strategic priorities (3-5 slides)
For each company priority (set in the most recent annual or quarterly planning):
- What's the priority, restated.
- Status: green / yellow / red with one-line rationale.
- Progress this quarter.
- Risks / blockers.
- Asks (if any).

### Section 4: Functional updates (5-10 slides)
One slide per major function (product, engineering, sales, marketing, CS, people, finance). Brief — top 3 things shipped, top 3 priorities for next quarter, key risks.

Don't go deeper than this in the deck; it kills meeting flow. Detailed function deep-dives belong in pre-reads or separate working sessions.

### Section 5: Topics for discussion (3-7 slides)
The most important section. The team picks 1-3 strategic topics for board input. Each gets 2-3 slides:
- Slide A: framing — what's the question, why now, what's at stake.
- Slide B: options — the 2-4 paths considered.
- Slide C: recommendation — what the team thinks, with reasoning, and what specifically the board's input is needed on.

The discussion section is what makes the meeting valuable. Without it, board meetings are status updates the team could have sent in writing.

### Section 6: Appendix (variable)
Detailed financials, customer logo lists, segment breakdowns. Reference, not presented.

## Tone and craft

- **Lead with the headline.** Every slide has a takeaway-first structure: title is the conclusion, body is the evidence.
- **One idea per slide.** If you need two ideas, you need two slides.
- **No surprises.** A board deck should never reveal critical bad news for the first time. Tell investors before the meeting.
- **Specific, not vague.** "Customer success is making progress" is useless. "NPS up 12 points to 47, driven by new onboarding flow shipped Feb 2" is useful.
- **Show the logos.** Include actual customer names (with permission) — investors love seeing the brands.
- **Quote customers occasionally.** "Their net retention isn't an abstraction" lands much harder when it's a quote from a real person.

## Build process

1. **Outline first** — bullet the deck section by section in markdown before opening the slide tool.
2. **Pre-meeting socialization** — send pre-read 48 hours before to investors. Get questions in advance; address them in the deck or pre-meeting.
3. **Rehearse** — at least one walk-through with the leadership team.
4. **Assign owners** — every slide has an owner who can defend it.
5. **Time-box rehearsal** — board meetings always run long. Plan to leave 30 min slack for unscheduled discussion.

## Output format

Save the outline to `outputs/board-deck/<period>-outline.md` first. Then generate the slide file via `pptx-handler` to `outputs/board-deck/<period>.pptx`.

The outline structure:
```
## Slide 1: Title — <takeaway>
[1-3 bullets of body content]

## Slide 2: <title>
[content]
```

After the meeting, save action items and decisions to `outputs/board-deck/<period>-followups.md`.

## Common mistakes

- All status, no discussion. Board's value is unlocked by debate, not updates.
- Surprises in the deck. Investors hate finding out about a churned customer or missed quota at the meeting.
- Too detailed. 60-slide decks lose the room.
- Pre-read sent the night before. Investors don't have time to engage.
- No clear asks. Board members want to help; they need to know how.

## Cross-references

For narrative / written board reports (instead of slides), use `board-report-builder`. For investor updates between board meetings, use `investor-update-writer`. For the underlying financial scenario modeling, use (when added) `scenario-modeling` and existing `forecast-modeler`. For slide file production, use `pptx-handler`. For pre-meeting brief, see chief-of-staff exec meeting prep workflow.
