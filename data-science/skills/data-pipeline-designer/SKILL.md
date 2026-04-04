---
name: data-pipeline-designer
description: Design data pipelines, ETL/ELT workflows, and data architecture. Use when building data ingestion, transformation, or analytics infrastructure.
triggers:
  - data pipeline
  - ETL design
  - data architecture
---

# Data Pipeline Designer

Design data pipelines that are reliable, observable, and maintainable. Follow the medallion architecture pattern (Bronze/Silver/Gold) for layered data quality.

## Phase 1 — Requirements

Before designing, answer these questions:

| Question | Answer | Design Implication |
|----------|--------|-------------------|
| What business questions will this data answer? | [Questions] | Determines what to capture |
| What systems produce the data? | [Source systems] | Determines ingestion method |
| What is the data volume? | [Rows/day, GB/day] | Determines storage and compute choices |
| What is the freshness requirement? | [Real-time / Hourly / Daily] | Determines batch vs. streaming |
| Who consumes the data? | [Analysts / ML models / APIs / Dashboards] | Determines serving layer format |
| What compliance requirements apply? | [GDPR / HIPAA / PCI / None] | Determines encryption, masking, retention |

## Phase 2 — Architecture (Medallion Pattern)

Use the Bronze/Silver/Gold layering pattern:

```
[Sources] → Ingestion → [Bronze] → Cleaning → [Silver] → Modeling → [Gold] → [Consumers]
```

### Bronze Layer (Raw)
- **Purpose:** Exact copy of source data with minimal transformation
- **Format:** Source format preserved (JSON, CSV, Avro, etc.)
- **Schema:** Schema-on-read. Store everything, transform nothing
- **Retention:** Long-term (months to years). This is your recovery layer
- **Partitioning:** By ingestion date (`year/month/day/`)
- **Quality checks:** Record count validation, schema detection, duplicate detection

### Silver Layer (Cleaned)
- **Purpose:** Deduplicated, typed, validated data ready for analysis
- **Format:** Columnar (Parquet, Delta, Iceberg)
- **Schema:** Enforced. Schema-on-write with validation
- **Transformations:** Deduplication (by business key + event timestamp), type casting, null handling, PII masking/tokenization, timestamp normalization to UTC
- **Quality checks:** Null rate thresholds, value range validation, referential integrity

### Gold Layer (Modeled)
- **Purpose:** Business-ready datasets optimized for specific use cases
- **Format:** Aggregated tables, materialized views, feature stores
- **Modeling approach:** Star schema (fact + dimension) or wide denormalized tables depending on consumer
- **Transformations:** Business logic (revenue calculations, status derivations), aggregations, cross-Silver joins, derived metrics and KPIs
- **Quality checks:** Metric comparison with source-of-truth, trend anomaly detection

## Phase 3 — Ingestion Design

Choose the right ingestion pattern:

| Pattern | Latency | Complexity | Best For |
|---------|---------|-----------|----------|
| **Batch (scheduled)** | Hours | Low | Daily reports, analytics, data warehouse loads |
| **Micro-batch** | Minutes | Medium | Near-real-time dashboards, frequent updates |
| **Streaming** | Seconds | High | Real-time alerts, live features, event processing |
| **CDC (Change Data Capture)** | Seconds-Minutes | Medium-High | Database replication, keeping systems in sync |

### Ingestion Specification
| Source | Method | Frequency | Format | Volume | Auth | Error Handling |
|--------|--------|-----------|--------|--------|------|---------------|
| [System] | API / CDC / File drop / Webhook | [Schedule] | [Format] | [Volume] | [Method] | [Retry policy] |

## Phase 4 — Transformation Design

For each transformation step, document:

```
Transform: [Name]
Input: [Source table(s)]
Output: [Target table]
Logic: [Business rule in plain language]
SQL/Code: [Implementation]
Idempotent: Yes/No (must be Yes for production)
Dependencies: [Upstream transforms that must complete first]
```

**Idempotency rule:** Every transformation must produce the same result whether run once or ten times. Use `MERGE`/`UPSERT` over `INSERT` and `CREATE OR REPLACE` over `CREATE`.

## Phase 5 — Data Quality Framework

Implement quality checks at every layer boundary:

| Check Type | Layer | Example | Action on Failure |
|-----------|-------|---------|------------------|
| **Schema validation** | Bronze → Silver | Expected columns present, types correct | Block and alert |
| **Completeness** | Bronze → Silver | Null rate below threshold per column | Block or flag |
| **Uniqueness** | Silver | No duplicate business keys | Deduplicate and log |
| **Freshness** | All | Data arrived within SLA window | Alert |
| **Volume** | All | Row count within expected range (±20% of average) | Alert |
| **Accuracy** | Gold | Metric matches source-of-truth within tolerance | Alert and investigate |

### Alerting Rules
- **P1 (page on-call):** Pipeline failure, data loss, SLA breach on critical pipeline
- **P2 (alert in channel):** Quality check failure, volume anomaly, partial data
- **P3 (daily report):** Warning thresholds, performance degradation, approaching capacity

## Phase 6 — Orchestration

Define the DAG (Directed Acyclic Graph) of pipeline tasks:

```
[Ingest Source A] ──> [Bronze A] ──> [Silver A] ──┐
                                                    ├──> [Gold: Combined] ──> [Dashboard]
[Ingest Source B] ──> [Bronze B] ──> [Silver B] ──┘
```

For each task:
| Task | Schedule | Timeout | Retries | Retry Delay | Dependency | Alert On |
|------|----------|---------|---------|-------------|-----------|----------|
| [Name] | [Cron/trigger] | [Minutes] | [Count] | [Backoff] | [Upstream tasks] | [Failure/SLA breach] |

## Phase 7 — Schema Evolution

Plan for schema changes before they happen:
- **New column:** Add as nullable, backfill if needed (low risk)
- **Column removed:** Deprecate first (stop writing), keep for N days, then drop
- **Column type changed:** Create new column with new type, migrate consumers, drop old (high risk)
- **Column renamed:** Add new name as alias, migrate consumers, drop old
- **Rule:** Never make a breaking change without a migration plan and consumer notification.

## Output Format

Save to `outputs/pipeline-design-[pipeline-slug].md` with:

1. Requirements table
2. Architecture diagram (text-based)
3. Layer specifications (Bronze/Silver/Gold)
4. Ingestion spec per source
5. Transformation documentation per step
6. Data quality rules per layer
7. Orchestration DAG with schedules
8. Schema definitions with evolution plan
9. Runbook: how to debug common failures

## Do NOT
- Skip data quality checks — bad data propagates downstream and erodes trust in the entire data platform
- Design without understanding downstream consumers — the Gold layer exists to serve them, not to mirror the source
- Ignore schema evolution — source systems change without warning. Plan for it
- Build non-idempotent transformations — every pipeline task must be safe to retry
- Store raw and transformed data in the same location — keep layers separate for debuggability and recovery
