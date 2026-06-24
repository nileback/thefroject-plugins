# /deal-update — Pipeline Status Update

Generate a weekly pipeline and deal status update.

## Workflow
1. Read context files:
   - `context/current-data.md` for pipeline metrics
   - Any deal notes, CRM exports, or call transcripts in `outputs/`
2. For each active deal, summarize:
   - **Stage** — Where it is in the pipeline
   - **Last action** — What happened since last update
   - **Next step** — Specific action with owner and date
   - **Risk** — Any blockers or concerns (flag stalled deals)
   - **Forecast** — Commit, best case, or upside
3. Compile the update:
   - **Pipeline snapshot** — Total value, deal count, weighted forecast
   - **Wins this week** — Closed deals with value
   - **Movement** — Deals that advanced or regressed
   - **At risk** — Deals stalled 2+ weeks with suggested actions
   - **New pipeline** — Deals added this week
   - **Focus items** — Top 3 actions for next week
4. Save to `outputs/deal-updates/week-[date].md`

Usage: `/deal-update [optional: specific focus area]`
Examples:
- `/deal-update`
- `/deal-update enterprise deals only`
- `/deal-update focus on deals closing this month`
