# /sow — Generate Statement of Work

Generate a ready-to-sign statement of work from proposal context.

## Before you start
Read these skill files if they exist:
- `.claude/skills/proposal-voice/` — copywriting rules for all client-facing docs
- `.claude/skills/pricing-guidelines/` — tiers, engagement models, pricing copy rules

## Workflow
1. Gather inputs:
   - Read any existing proposal or demo deck in `outputs/`
   - Client name, project name, and engagement type
   - Scope agreed during sales process
   - Timeline and milestones
   - Pricing and payment terms (reference pricing-guidelines)
2. Generate the SOW:
   - **Parties** — Your company and the client, with contacts
   - **Background** — Brief context on why this engagement exists
   - **Scope of work** — Specific deliverables with acceptance criteria
   - **Out of scope** — Explicit boundaries to prevent scope creep
   - **Timeline** — Milestones with dates and dependencies
   - **Team** — Who's involved and their roles
   - **Investment** — Pricing breakdown, payment schedule, terms
   - **Assumptions** — What needs to be true for this to work
   - **Change process** — How scope changes are handled
3. Save to `outputs/sow-[client-name].md`

Usage: `/sow [client name] [optional: engagement type or reference to proposal]`
Examples:
- `/sow Acme Corp — based on the demo-proposal in outputs/`
- `/sow Northwind Traders — 3-month advisory engagement`
