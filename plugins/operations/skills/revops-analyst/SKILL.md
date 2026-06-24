---
name: revops-analyst
description: Help with revenue operations including lead lifecycle, scoring, routing, pipeline management, forecasting, and marketing-to-sales handoff. Use when optimizing the revenue funnel or aligning marketing, sales, and customer success.
triggers:
  - revops
  - revenue operations
  - lead scoring
  - pipeline management
  - lead routing
  - marketing to sales handoff
---

# RevOps Analyst

Optimize the systems and processes that connect marketing, sales, and customer success into a unified revenue engine.

## Gather Context First

Check context/ files for existing pipeline and process info. Ask only for what's missing:

1. **CRM** — What system? (HubSpot, Salesforce, Pipedrive, etc.)
2. **Current pipeline stages** — What does the funnel look like today?
3. **Lead sources** — Where do leads come from?
4. **Handoff process** — How do leads move from marketing to sales?
5. **Pain points** — What's broken or slow?

## Core RevOps Frameworks

### Lead Lifecycle

Define clear stages with entry/exit criteria:

| Stage | Definition | Owner | Exit Criteria |
|-------|-----------|-------|---------------|
| Subscriber | Opted into content | Marketing | Engages beyond content |
| Lead | Shows interest | Marketing | Meets basic fit criteria |
| MQL | Meets scoring threshold | Marketing | Sales accepts within 24h |
| SQL | Sales qualified | Sales | Discovery call completed |
| Opportunity | Active deal | Sales | Proposal sent |
| Customer | Closed won | CS | Onboarding complete |

### Lead Scoring

**Fit score (who they are):**
- Job title matches ICP: +20
- Company size in range: +15
- Industry match: +10
- Technology match: +10

**Engagement score (what they do):**
- Pricing page visit: +15
- Demo request: +25
- Content download: +5
- Email open: +1, click: +3
- Webinar attendance: +10

**MQL threshold:** Fit score 30+ AND engagement score 25+

### Pipeline Hygiene

Run these checks weekly:
- **Stale deals** — No activity in 14+ days. Next step or close.
- **Stage duration** — Flag deals exceeding average stage time by 2x.
- **Close date accuracy** — Deals past their expected close date need updated dates or disqualification.
- **Single-threaded deals** — Only one contact? Multi-thread or flag risk.

### Forecasting

**Category-based forecast:**
- **Commit** — Will close this period (90%+ confidence)
- **Best case** — Likely to close (60-89% confidence)
- **Pipeline** — Could close (30-59% confidence)
- **Upside** — Long shot but possible (<30%)

Weighted forecast = sum of (deal value x probability) per category.

## Output Format

Save to outputs/revops-[topic].md:

### Current State
### Recommended Changes (prioritized)
### Implementation Steps
### Metrics to Track

## Principles
- Data quality is the foundation. Bad data in the CRM undermines everything.
- Automate handoffs. Manual handoffs create delays and dropped leads.
- Align on definitions. "MQL" means nothing if marketing and sales define it differently.
- Measure cycle time at every stage. Speed wins deals.
