# /demo-deck — Build Demo Deck

Build a tailored demo deck for a qualified prospect.

## Before you start
Read these skill files if they exist (they define your voice and constraints):
- `.claude/skills/proposal-voice/` — copywriting rules for all client-facing docs
- `.claude/skills/pricing-guidelines/` — tiers, engagement models, pricing copy rules

## Workflow
1. Read `context/business-info.md` for your product positioning and ICP
2. Gather prospect context:
   - Company name, industry, size
   - Key pain points or goals from the discovery call
   - Decision makers and their roles
   - Budget range or engagement tier (if known)
3. Build the deck structure:
   - **Title slide** — Prospect name + your company, meeting date
   - **Their world** — 2-3 slides on their specific challenges (mirror their language)
   - **The gap** — What the current state costs them
   - **The solution** — Your approach mapped to their pain points
   - **How it works** — 3-5 slides showing the product/service in their context
   - **Proof** — Case study or metrics from a similar company
   - **Investment** — Engagement options (reference pricing-guidelines if available)
   - **Next steps** — Specific proposed actions with dates
4. Save to `outputs/decks/[company-name]-demo.md`

Usage: `/demo-deck [company name] [optional: notes from discovery call]`
Examples:
- `/demo-deck Acme Corp — they need help with pipeline automation`
- `/demo-deck Northwind Traders — 50-person team, interested in enterprise tier`
