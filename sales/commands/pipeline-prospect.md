# /pipeline-prospect: Lead Intelligence Pipeline

Run a five-stage pipeline from signal discovery through pipeline tracking. Present output at each stage for approval before continuing.

## Stage 1 — Signal Discovery

Scan for buying signals on the target company:
- Job postings (hiring for roles your product serves)
- Tech stack changes (new tools, migrations, platform shifts)
- Funding rounds, acquisitions, or leadership changes
- Company news, press releases, and social activity

Score each signal: **hot** (active need, time-sensitive), **warm** (relevant change, no urgency), or **cold** (general fit, no trigger).

Output: signal brief with scored list in `outputs/prospect-signals.md`.

## Stage 2 — Account Enrichment

Build a full account profile using available information and user input:
- Company: size, industry, tech stack, funding stage, growth trajectory
- Key stakeholders: decision makers, champions, gatekeepers (names, titles, LinkedIn) — ask the user to provide or verify these
- Existing relationships: mutual connections, past interactions, shared communities — ask the user for CRM data or known contacts

Output: enriched account profile appended to signal brief.

## Stage 3 — Warm Path Analysis

Map the shortest path to a warm introduction:
- Rank mutual connections by relationship strength and relevance
- Identify shared communities, events, Slack groups, or content engagement
- Find the single best intro path and two fallback options
- Draft a brief intro request message for each mutual connection

Output: warm path map with draft intro requests.

## Stage 4 — Outreach Drafting

Reference `context/` files for your product's value proposition and positioning. Write personalized outreach for three channels:
1. **Cold email** — reference a specific signal, state the value prop, soft CTA
2. **LinkedIn message** — shorter, conversational, reference shared context
3. **Warm intro** — message for the connector to forward, plus a direct follow-up

For email: include two subject line variants and two opening hook variants (A/B test ready). Every message must reference at least one signal from Stage 1.

Output: outreach drafts organized by channel.

## Stage 5 — Pipeline Tracking

Log the prospect in `outputs/prospect-pipeline.md` using this format:

```
## [Company Name]
- **Status:** researched | contacted | responded | meeting | qualified
- **Signals:** [top 2-3 signals]
- **Next action:** [specific step with date]
- **Owner:** [name]
```

If the file exists, append. If not, create it with a header and this entry.

Generate a weekly pipeline review prompt that summarizes all prospects by status and flags stale entries (no update in 7+ days).

## Usage

Run: `/pipeline-prospect [company name]`
Example: `/pipeline-prospect Acme Corp`
