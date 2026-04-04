# /deploy-check — Pre-Deployment Verification

Run a structured verification loop before merging or deploying. Report pass/fail for each check.

## Checks

Run these in order. Stop on critical failure (build broken), continue through warnings.

1. **Build** — Run the build command. Must succeed with zero errors.
2. **Type check** — Run the type checker (tsc --noEmit or equivalent). Zero errors required.
3. **Lint** — Run the linter. No errors (warnings acceptable if pre-existing).
4. **Tests** — Run the full test suite. All must pass.
5. **Security scan** — Check for known vulnerabilities in dependencies (npm audit or equivalent).
6. **Stub detection** — Grep changed files for: TODO, FIXME, placeholder, "fill in later", hardcoded test values, console.log, debugger statements.
7. **Diff review** — Review git diff for: debugging artifacts, commented-out code, unintended file changes, merge conflict markers.
8. **Dependencies** — Lockfile up to date, no known vulnerabilities.
9. **Breaking changes** — Check for API changes, removed exports, schema migrations. Document if found.
10. **Git state** — Clean branch, up to date with main, no untracked files that should be committed.

## Output

| Check | Status | Details |
|-------|--------|---------|
| Build | PASS/FAIL | ... |
| Type check | PASS/FAIL | ... |
| ... | ... | ... |

**Verdict:** SHIP (all pass) / FIX (failures found) / BLOCK (critical failure)

For each failure, include the specific error and a suggested fix.
