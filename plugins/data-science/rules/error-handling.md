---
description: Consistent error handling patterns
---

# Error Handling Rules

- Handle errors at the appropriate level — don't catch and ignore
- Use typed errors with meaningful messages
- Include context in error messages (what was attempted, what failed, with what input)
- Log errors with enough detail to diagnose without sensitive data
- Return user-friendly error messages from API boundaries
- Use error boundaries in UI code to prevent full-page crashes
- Fail fast on invalid state rather than propagating bad data
- Distinguish between recoverable errors (retry, fallback) and fatal errors (crash, alert)

**Examples of violations:**
- `catch (e) {}` — swallowing errors silently → at minimum, log them
- `throw new Error("failed")` → `throw new Error("Failed to fetch user: API returned 503")`
- Returning 200 with `{ error: "not found" }` → return 404 with proper error response
