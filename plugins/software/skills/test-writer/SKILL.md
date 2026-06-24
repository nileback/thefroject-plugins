---
name: test-writer
description: Generate test suites with unit, integration, and edge case tests. Use when adding test coverage, writing regression tests, or setting up a testing strategy for new features.
triggers:
  - write tests
  - add tests
  - test this
  - add test coverage
  - write unit tests
---

# Test Writer

You write thorough, practical tests that catch real bugs and serve as living documentation.

## Gather Context First

1. Read the source file to understand all code paths, side effects, and return values
2. Identify the testing framework (`package.json`, `vitest.config`, `jest.config`, `pytest.ini`, etc.)
3. Check for existing tests in the same directory or a `__tests__` / `tests` folder
4. Read `reference/` for any project-specific testing conventions
5. Identify external dependencies that need mocking (APIs, databases, file system, timers)

## Test Design Process

### Step 1 — Map the behaviors

List every distinct behavior the code under test exhibits:

- What does it return or produce for valid inputs?
- What side effects does it trigger (state changes, API calls, DOM updates)?
- How does it handle invalid, missing, or unexpected inputs?
- What are the boundary conditions?

### Step 2 — Categorize by test type

**Unit tests** (isolated, fast, no external dependencies):
- Pure functions and their edge cases
- State transformations
- Validation logic
- Utility functions

**Integration tests** (multiple units working together):
- Component rendering with state management
- API call chains (mock the network, not the service layer)
- Database operations with test fixtures
- Multi-step workflows

**Edge case tests** (the cases that break production):
- Empty inputs: `null`, `undefined`, `""`, `[]`, `{}`
- Boundary values: `0`, `-1`, `Number.MAX_SAFE_INTEGER`, max-length strings
- Concurrent operations: race conditions, double submissions
- Error recovery: network timeouts, invalid JSON, full storage

### Step 3 — Write tests using the AAA pattern

Structure every test as:

```
// Arrange — set up inputs and expected outputs
// Act — call the function or trigger the behavior
// Assert — verify the result matches expectations
```

### Step 4 — Name tests descriptively

Use the pattern: `should [expected behavior] when [condition]`

Examples:
- `should return empty array when no items match the filter`
- `should throw ValidationError when email format is invalid`
- `should retry the request up to 3 times when the server returns 503`

## Mocking Strategy

**Mock these** (external boundaries):
- Network requests (use `msw`, `nock`, or framework-native mocks)
- Timers and dates (`vi.useFakeTimers()`, `jest.useFakeTimers()`)
- File system access
- Browser APIs (`localStorage`, `navigator`, `window.location`)
- Third-party services

**Do NOT mock these** (internal implementation):
- Private functions within the module under test
- Data transformations between internal layers
- State management internals (test the public API instead)

## Test Quality Checklist

- [ ] Each test is independent and can run in any order
- [ ] Each test has a single clear assertion (or closely related group)
- [ ] Test names describe behavior, not implementation
- [ ] No shared mutable state between tests
- [ ] Setup and teardown clean up after themselves
- [ ] Tests run fast (under 100ms for unit tests)
- [ ] Flaky conditions are eliminated (no `setTimeout` in tests, no reliance on timing)

## Output Format

```
## Test Plan for [file/module name]

### Coverage Summary
- **Behaviors identified:** [count]
- **Unit tests:** [count]
- **Integration tests:** [count]
- **Edge case tests:** [count]

### Test File
[complete test file with imports, describe blocks, and all tests]
```

Save the test file alongside the source: `[filename].test.ts` in the same directory, or in a mirrored path under `tests/`.

## Do NOT

- Write tests that verify implementation details (e.g., "function X was called 3 times")
- Use `test('works')` or `test('should work correctly')` as test names
- Copy-paste test bodies with minor tweaks. Use parameterized tests instead.
- Skip error cases. Most production bugs live in unhandled edge cases.
- Add `sleep()` or timing-dependent assertions. Use fake timers or event-based assertions.
- Write tests that pass when the code is broken (tautological assertions like `expect(true).toBe(true)`)
