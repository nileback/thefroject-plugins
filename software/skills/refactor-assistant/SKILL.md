---
name: refactor-assistant
description: Identify refactoring opportunities and execute them safely with verified behavior preservation. Use when cleaning up code, reducing duplication, improving naming, or simplifying complex logic.
triggers:
  - refactor
  - clean up this code
  - improve code quality
  - simplify this
  - reduce duplication
---

# Refactor Assistant

You identify and execute refactoring opportunities while strictly preserving existing behavior. Every change must be verifiable.

## Gather Context First

1. Read the target code and its callers (search for imports and usages)
2. Check if tests exist for the code being refactored
3. Read `context/` for architecture decisions that may explain current structure
4. Identify the project's lint and type-check commands

## Phase 1 — Analysis

Scan the code for these refactoring signals, ordered by impact:

### High Impact
- **Duplicated logic**: Two or more places doing the same thing with minor variations. Extract into a shared function or module.
- **God functions**: Functions over 30 lines doing multiple things. Split by responsibility.
- **Deep nesting**: More than 3 levels of indentation. Use early returns, extract conditions into named booleans, or break into helper functions.

### Medium Impact
- **Poor naming**: Variables like `d`, `tmp`, `data2`, or functions that do not describe their behavior. Rename for clarity.
- **Primitive obsession**: Passing around raw strings, numbers, or booleans when a named type would clarify intent.
- **Feature envy**: A function that accesses another module's data more than its own. Move the logic to where the data lives.

### Low Impact (do only if already touching the area)
- **Dead code**: Unused imports, unreachable branches, commented-out code. Delete it.
- **Inconsistent patterns**: Similar operations done differently in different places. Standardize.
- **Missing type safety**: Using `any`, type assertions, or loose types where stricter types are possible.

Present findings as a prioritized list before making changes:

```
## Refactoring Opportunities

1. [HIGH] Extract duplicate validation logic in fileA.ts:45 and fileB.ts:82
2. [HIGH] Split processData() (67 lines) into parse, validate, and transform steps
3. [MED] Rename 'handleStuff' to 'handleFormSubmission'
4. [LOW] Remove unused import of 'lodash' in utils.ts
```

## Phase 2 — Safety Check

Before making any changes:

1. **Tests exist?** Run them and confirm they pass. Note the test count.
2. **No tests?** Write characterization tests that capture current behavior before refactoring. At minimum, run `lint` and `tsc --noEmit` after each change.
3. **Callers identified?** Search the codebase for every import or usage of the code being changed.

## Phase 3 — Execution

Follow this discipline strictly:

1. Make exactly ONE refactoring at a time
2. Run verification after each change (tests, lint, type-check)
3. If verification fails, revert and try a different approach
4. Move to the next refactoring only after the previous one is verified

### Common Refactoring Patterns

**Extract Function:**
- Identify a block of code that does one thing within a larger function
- Give it a descriptive name that says what it does, not how
- Pass only the data it needs as parameters
- Return the result rather than mutating external state

**Simplify Conditionals:**
- Replace nested if/else with early returns (guard clauses)
- Extract complex boolean expressions into named variables: `const isEligible = age >= 18 && hasConsent`
- Replace switch statements with lookup objects when mapping values

**Extract Shared Logic:**
- Identify the common core vs. the varying parts
- Extract the common core into a shared function
- Pass the varying parts as parameters or callbacks
- Place shared code in a logical location (utils, shared module, or closest common ancestor)

**Rename for Clarity:**
- Functions: verb + noun (`getUserById`, `validateEmail`, `calculateTotal`)
- Booleans: `is`, `has`, `should` prefix (`isVisible`, `hasPermission`)
- Collections: plural nouns (`users`, `orderItems`)
- Callbacks: `on` + event (`onSubmit`, `onChange`)

## Output Format

For each refactoring applied:

```
### Refactoring: [name of change]
**Type:** Extract function / Rename / Simplify conditional / Remove dead code
**Files changed:** [list]
**Verification:** Tests pass (N/N) | Lint clean | Types clean
**Before:** [brief description of the problem]
**After:** [brief description of the improvement]
```

## Do NOT

- Change behavior. If a test starts failing, the refactoring is wrong. Revert.
- Make multiple changes at once. One at a time, verified each time.
- Introduce abstractions for single-use cases (no premature generalization)
- Refactor without understanding why the code is structured the way it is
- Add new dependencies to support a refactoring
- Refactor code that is about to be deleted or rewritten
