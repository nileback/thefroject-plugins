# /tdd-cycle — Test-Driven Development Cycle

Build a feature using strict red-green-refactor TDD.

## Workflow

### 1. Red — Write a failing test
- Write the smallest test that describes the next piece of behavior
- Run it — confirm it fails for the right reason
- If it passes already, the behavior exists — write a different test

### 2. Green — Make it pass
- Write the minimum code to make the test pass
- No extra features, no premature optimization
- Run the test — confirm it passes

### 3. Refactor — Clean up
- Improve the code without changing behavior
- Run tests after each refactoring step
- Focus on: naming, duplication, complexity

### 4. Repeat
- Pick the next behavior. Write the next failing test.
- Continue until the feature is complete.

## Rules
- Never write production code without a failing test
- Never write more than one failing test at a time
- Keep the cycle under 5 minutes per iteration

Usage: `/tdd-cycle [feature description]`
