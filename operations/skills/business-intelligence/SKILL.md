---
name: business-intelligence
description: Build cross-functional business reports — pull data from multiple sources, normalize, build a dashboard or report, write the narrative. Ops-side workflow for non-engineers. Distinct from data-analyst which is development-tagged. Use when user mentions BI, business intelligence, KPI dashboard, exec reporting, or cross-functional metrics.
triggers:
  - business intelligence
  - bi report
  - kpi dashboard
  - exec dashboard
  - cross-functional metrics
  - operational reporting
---

# Business Intelligence

Build a business report or dashboard that an exec or leadership team will actually use. Three things kill BI deliverables: too much data, no narrative, no action.

## Gather context

Ask if not provided:

1. **Audience** — exec leadership, board, function head, ops team?
2. **Decision** — what's the report meant to inform? (Strategic shift, operational tweak, status check?)
3. **Cadence** — one-time, weekly, monthly, quarterly?
4. **Data sources** — what's available (CRM, finance system, product analytics, support system, marketing automation)?
5. **Tools** — Notion, Looker, Tableau, Sigma, Metabase, Excel, Google Sheets?

## The report architecture

Every business report has three layers. Each serves a different reader:

### Layer 1: The headline (one sentence)
What's the single most important thing the reader needs to know? State it at the top.

Examples:
- "Net new ARR is 18% below plan; the gap is concentrated in mid-market segment."
- "Customer health is improving across all segments except enterprise; root cause is delayed onboarding."

### Layer 2: The dashboard (one page / one screen)
The 5-7 metrics that explain the headline:
- Each metric: number, change vs. baseline (last period, plan, year-ago), trend chart, color-code (green / yellow / red).
- Group related metrics together.
- Avoid more than 7 metrics on the top view. Drilldowns live below.

### Layer 3: The narrative (written commentary)
For each yellow or red metric:
- Why is it where it is? (Concrete root cause, not "headwinds.")
- What's being done about it?
- Who owns it?
- When will it improve?

For green metrics, brief acknowledgment is enough. Most attention goes to problems.

## Workflow

### Step 1: Define the right metrics
Avoid vanity metrics. Each metric should:
- Map directly to a strategic priority.
- Have a baseline (plan, last period, year-ago).
- Have a target (where should we be?).
- Have an owner (a single named person).

A typical exec dashboard has metric groups:
- **Revenue** — net new ARR, expansion ARR, churn ARR, total ARR, ARR retention.
- **Pipeline** — total open pipeline, qualified pipeline, coverage ratio, expected close.
- **Customer** — health score distribution, NPS, churn count, top expansion accounts.
- **Product / engineering** — release velocity, customer-facing bugs, uptime.
- **People** — headcount vs plan, attrition rate, open reqs, eNPS.
- **Cash** — runway, monthly burn, cash collected.

Pick 1-2 from each group; not all of them. 5-7 total at the top level.

### Step 2: Source the data
- Pull from canonical systems (the CRM is truth for revenue; the finance system is truth for cash).
- Document each metric's source and refresh frequency.
- Flag any metric that requires manual aggregation — it'll drift.
- For self-serve BI tools (Looker, Sigma), build queries the team can refresh themselves.

### Step 3: Build the visual
- Tables for precise numbers. Charts for trends. Don't mix.
- Same time-window across all charts (don't show last week in one and last quarter in another).
- Sparklines for compact trends.
- Color-coding consistent: green = on plan, yellow = at-risk, red = off-plan.

### Step 4: Write the narrative
- 3-5 sentences per problem metric.
- Lead with the cause, not the symptom.
- Include the owner and timeline.
- Avoid corporate hedging ("we're seeing some softness"). Be direct.

### Step 5: Distribute and discuss
- Pre-read sent 24 hours before the meeting.
- Meeting opens with the headline, not the metrics.
- 10 minutes max on data; 50 minutes on decisions.

## Output format

For each report cycle, save `outputs/business-intelligence/<period>-report.md`:

```
## Headline
<one sentence>

## Dashboard
| Metric | Current | vs. Plan | vs. Last | Trend | Owner |
|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... |

## Narrative
### <metric in red or yellow>
- Cause: ...
- Action: ...
- Owner: ...
- ETA: ...

(repeat per problem metric)

## Notes
- <Methodology change, data caveat, or context>

## Decisions needed
- <decision> — <by whom> — <by when>
```

For dashboards in BI tools, document the URL, refresh cadence, and ownership in `outputs/business-intelligence/dashboards.md`.

## Common mistakes

- Showing 30 metrics. Reader can't focus.
- No baseline. "Revenue is $1.2M" tells the reader nothing.
- Vague narrative. "Pipeline is soft due to seasonality." Why? What's being done?
- Different time-windows on different charts. Untrustworthy.
- No owner or ETA. Reader can't follow up.

## Cross-references

For finance-specific reporting, use `financial-report-writer` and `saas-metrics-coach`. For board-level reports, use `board-report-builder` and (when added) `board-deck-builder`. For investor-update writing, use `investor-update-writer`. For development-side data analysis, use `data-analyst`. For decision documentation, use `decision-tracker`.
