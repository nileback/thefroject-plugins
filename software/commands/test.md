# /test — Run Tests

Run the project's test suite and report results.

1. Detect the test framework (check package.json, pyproject.toml, etc.)
2. Run the full test suite (or specified tests)
3. Report: total, passed, failed, skipped
4. For any failures: show the error, identify the root cause, suggest a fix
5. If no tests exist, suggest which tests to write first

Usage: `/test` or `/test [specific-file-or-pattern]`
