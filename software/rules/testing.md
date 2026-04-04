---
description: Standards for writing and maintaining tests
globs:
  - "**/*.test.*"
  - "**/*.spec.*"
  - "**/__tests__/**"
---

# Testing Rules

- Every new feature or bug fix must include tests
- Write tests before implementation when possible (TDD)
- Test behavior, not implementation details
- Use descriptive test names: `should [expected] when [condition]`
- Keep tests independent — no shared mutable state between tests
- Prefer unit tests for business logic, integration tests for workflows
- Mock external dependencies (APIs, databases), not internal modules
- Aim for meaningful coverage, not 100% line coverage
- Each test file should mirror the source file it tests

**Examples of violations:**
- `test('works')` → `test('should return 404 when user not found')`
- Testing that a function calls another function → test the output instead
- Tests that fail when run in different order → remove shared state
