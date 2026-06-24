---
description: Standards for data processing and analysis
globs:
  - "src/data/**"
  - "**/*.csv"
  - "**/*.json"
---

# Data Handling Rules

- Document data sources and their refresh schedules
- Validate data quality before analysis — check for nulls, duplicates, outliers
- Use consistent date formats (ISO 8601) across all data pipelines
- Never expose PII in logs, reports, or error messages
- Version datasets and transformations for reproducibility
- Include confidence intervals or margins of error with statistical claims
- Prefer established statistical methods over custom implementations
