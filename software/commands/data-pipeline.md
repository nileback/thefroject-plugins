# /data-pipeline — Data Pipeline Management

Design a new data pipeline or troubleshoot an existing one.

## Design Workflow

1. **Requirements** — Source, destination, frequency, volume, SLA
2. **Architecture** — Draw the flow: source → ingestion → transform → serve
3. **Schema** — Define input/output schemas with types and constraints
4. **Quality** — Add validation checks, null handling, dedup logic
5. **Orchestration** — Scheduling, dependencies, retry, alerting
6. **Implementation** — Write the pipeline code/config

## Troubleshoot Workflow

1. **Symptoms** — What's failing? Missing data, stale data, errors?
2. **Trace** — Follow data from source to failure point
3. **Diagnose** — Check: source availability, schema changes, resource limits, dependency failures
4. **Fix** — Address root cause with proper error handling
5. **Prevent** — Add monitoring/alerting for this failure mode

## Output Format

### Pipeline Spec
- **Name:** [name]
- **Flow:** [source] → [transform] → [destination]
- **Schedule:** [cron or trigger]
- **SLA:** [freshness requirement]
- **Schema:** [table with columns, types, constraints]

Usage: `/data-pipeline [design|troubleshoot] [description]`
