# /fix-issue — Fix a Reported Issue

Systematically fix a bug or issue from report to resolution.

## Workflow

1. **Understand** — Read the issue description. What's the expected vs. actual behavior?
2. **Reproduce** — Find or write a test that demonstrates the failure
3. **Locate** — Use Grep/Glob to find the relevant code. Trace the data flow.
4. **Diagnose** — Identify the root cause (not just the symptom)
5. **Fix** — Apply the minimal change that addresses the root cause
6. **Test** — Run the test suite. Confirm the fix works and nothing else breaks.
7. **Document** — Summarize what caused the issue and how it was fixed

## If blocked
- If you can't reproduce: ask for more details (steps, environment, error messages)
- If the fix is risky: explain the risk and propose alternatives
- If tests don't exist: write a failing test first, then fix

Usage: `/fix-issue [issue description or link]`
