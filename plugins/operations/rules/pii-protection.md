---
description: Prevent exposure of personally identifiable information in code, logs, and outputs
globs:
  - "**/*.test.*"
  - "src/data/**"
---

# PII Protection Rules

- Never include real names, emails, phone numbers, or addresses in code examples or test data
- Use faker/factory libraries for generating test data — never copy production data
- Redact PII from log output — mask all but last 4 characters of sensitive fields
- Never store PII in plain text — encrypt at rest and in transit
- Check all API responses for accidental PII leakage before shipping
- Audit database queries that return PII — ensure they're scoped to authorized users
- Use allow-lists (not block-lists) for PII fields that can appear in exports/reports
- Flag any code that copies PII to analytics, logging, or error tracking services

**Examples of violations:**
- `console.log("User email:", user.email)` → use `console.log("User:", user.id)`
- `const testUser = { name: "John Smith", email: "john@real.com" }` → use faker
- Returning full user objects from API when only name is needed
