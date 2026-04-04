---
name: tdd-workflow
description: Guide test-driven development with strict red-green-refactor discipline. Use when building new features from scratch, implementing algorithms, or working on code that needs high reliability.
triggers:
  - tdd
  - test-driven
  - red green refactor
  - build this with tests first
---

# TDD Workflow

You guide test-driven development with strict discipline. TDD is not "write tests." It is a design technique that uses tests to drive the structure of code, one small step at a time.

## Gather Context First

1. What behavior needs to be built? (user story, spec, or description)
2. What testing framework is available? (check `package.json` or project config)
3. Is there existing code to extend, or are we building from scratch?
4. What are the acceptance criteria? (how do we know when we are done?)

## The Red-Green-Refactor Cycle

### Red — Write a Failing Test

1. Choose the next smallest behavior to implement
2. Write a test that describes the expected behavior
3. Run the test. It MUST fail. If it passes, the test is not testing new behavior.
4. Verify the test fails for the RIGHT reason (not a syntax error or import issue)

**What makes a good "Red" test:**
- Tests one specific behavior (not two, not three, one)
- Has a descriptive name: `should [expected] when [condition]`
- Fails with a clear, understandable error message
- Is small enough that the code to make it pass is obvious

### Green — Make It Pass

1. Write the MINIMUM code to make the failing test pass
2. It is okay if the code is ugly, hardcoded, or simplistic at this stage
3. Run ALL tests (not just the new one). Everything must be green.
4. If you wrote more code than strictly necessary, you skipped ahead. Step back.

**The discipline of "minimum":**
- If the test expects a specific return value, it is okay to hardcode that value
- The next test will force you to generalize
- Resist the urge to write the "real" implementation. The tests will guide you there.

### Refactor — Clean Up

1. With all tests green, look for improvements:
   - Remove duplication between production code and test code
   - Improve naming for clarity
   - Extract methods or functions that do one thing
   - Simplify complex conditionals
2. Run ALL tests after each refactoring change
3. If any test fails, revert the refactoring and try again
4. Do NOT add new behavior during refactoring. Only restructure.

## TDD Cycle Progression

A typical feature builds up through progressively more specific tests:

```
Cycle 1: should return empty result when given no input
Cycle 2: should return single item when given one valid input
Cycle 3: should return multiple items in correct order
Cycle 4: should filter out invalid items
Cycle 5: should handle edge case (empty string, null, boundary value)
Cycle 6: should throw descriptive error for malformed input
```

Each cycle takes 3-10 minutes. If a cycle takes longer than 15 minutes, the step is too big. Break it down.

## Test Ordering Strategy

Start with the simplest case and add complexity:

1. **Degenerate cases**: null input, empty input, zero, nothing to do
2. **Simple valid cases**: one item, happy path with minimal data
3. **Multiple items**: lists, collections, combinations
4. **Edge cases**: boundary values, special characters, maximum sizes
5. **Error cases**: invalid input, missing data, failure modes
6. **Integration**: how this interacts with other components

## When to Use TDD

**Good fit for TDD:**
- Pure functions and business logic
- Algorithms and data transformations
- State machines and workflow engines
- API endpoint handlers
- Validation logic
- Any code where correctness matters more than speed of writing

**Awkward fit for TDD (use test-after instead):**
- UI layout and styling (hard to express as test assertions)
- Exploratory prototypes (requirements are unclear)
- One-time scripts or migrations
- Integration with external services (mock-heavy tests add little value)

## Output Format

For each TDD cycle, present:

```
### Cycle [N]: [behavior being added]

**Red — Test:**
[test code]

**Green — Implementation:**
[minimum code to pass]

**Refactor:**
[changes made, or "No refactoring needed"]

**All tests passing:** [count] / [count]
```

## Do NOT

- Write production code before a failing test exists
- Write more than one failing test at a time (one red test, then green, then refactor)
- Skip the refactor step. It is where the design emerges.
- Write tests that test implementation details (internal state, private methods)
- Hardcode values permanently. Hardcoding is okay temporarily; the next test forces generalization.
- Take steps that are too large. If you cannot make the test pass in under 5 minutes, the step is too big.
- Refactor while tests are red. Green first, then refactor.
