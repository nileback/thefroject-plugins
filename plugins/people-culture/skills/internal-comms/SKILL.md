---
name: internal-comms
description: Write internal communications for the org — all-hands updates, change announcements, sensitive memos (layoffs, restructuring), exec emails, status updates. Use when the user mentions all-hands, internal memo, change announcement, company-wide message, or write to the team.
triggers:
  - all-hands update
  - internal announcement
  - change announcement
  - company memo
  - write to the team
  - exec email to staff
---

# Internal Comms

Write messages directed inside the organization. The audience already trusts the brand; the goal is clarity, not persuasion. Tone is professional, candid, and human — not marketing.

## Identify the message type first

Before drafting, name the type. Each has its own conventions:

- **All-hands update** — periodic, mostly positive, mixes business + people. Length: 400-600 words.
- **Change announcement** — process or tooling change, neutral tone, focuses on what / why / when. Length: 200-400 words.
- **Sensitive memo** — layoffs, restructuring, public crisis. Direct, no euphemisms, name the action plainly. Length: 200-400 words.
- **Exec email to staff** — single-topic, signed by a named leader, often Q&A invitation at the end. Length: 200-400 words.
- **Status update** — ongoing project, what shipped, what's next, blockers. Length: 150-300 words.
- **Recognition / culture moment** — wins, work anniversaries, team milestones. Length: 100-200 words.

If the user says "send this out" without specifying, ask which type to default to.

## Universal rules

- **Lead with the news.** First paragraph carries the action or change. No throat-clearing.
- **Why before what.** State the reason once, near the top. Don't bury motivation in paragraph four.
- **Plain language.** No corporate jargon. "We're cutting the X program" not "We're sunsetting the X initiative."
- **One message per memo.** A layoff note is not the place to also announce a new hire. Separate.
- **Name decisions, name owners.** "We decided X. Y owns next steps." Avoid passive voice on the decisions.
- **Don't spin.** Internal audiences detect spin instantly and lose trust. If the news is bad, say it's bad.

## Sensitive memos (layoffs, restructuring, public crises)

Special handling. Mistakes here damage the company for years.

- Do not use euphemisms ("right-sizing", "exiting", "decisioning"). Say "layoffs", "letting people go", "reducing headcount".
- Lead with the action and who's affected. Don't bury it.
- Acknowledge impact before explaining cause. People don't want the strategy first.
- State what's done already (severance, support, references) before what's next.
- Sign with a real person, not "The Leadership Team." A name takes responsibility.
- Write a separate short note to managers BEFORE the company-wide one — they need to be ready for questions.

## Output format

Save the draft to `outputs/internal-comms/<date>-<topic>.md` with a header block at the top:

```
## Internal: <Topic>
- Type: <message type>
- From: <named sender>
- Audience: <all-hands / department / managers>
- Send via: <email / Slack / both>
- Embargo: <"none" or date>
```

Then the message body. Then a "Q&A prep" section anticipating the top 3-5 questions someone might have, with suggested answers. Include the Q&A section even if the user didn't ask for it — it's almost always needed before sending.

## Cross-references

For external announcements (press releases, social posts), see `launch-playbook` or `press-release-writer` (if available). For one-off exec stakeholder updates (board, investors), see `stakeholder-updater`. For change-management plans behind the announcement, see `change-management-guide`. For brand-consistent tone, see `brand-voice-builder`.
