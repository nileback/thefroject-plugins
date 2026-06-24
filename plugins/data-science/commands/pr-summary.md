# /pr-summary — Generate PR Description

Generate a well-structured pull request description from the current branch changes.

## Workflow

1. **Diff analysis** — Run `git diff main...HEAD` to see all changes
2. **Commit history** — Run `git log main..HEAD --oneline` for commit context
3. **Categorize changes** — Group by: new features, bug fixes, refactors, tests, docs
4. **Write summary** — Draft the PR description

## PR Format

```markdown
## Summary
[1-3 sentences: what this PR does and why]

## Changes
- [Change 1]
- [Change 2]

## Testing
- [ ] Unit tests added/updated
- [ ] Manual testing completed
- [ ] Edge cases covered

## Notes for reviewers
[Anything reviewers should know: tricky parts, open questions, follow-ups]
```

## Verification
- Confirm all changed files are mentioned or covered by the summary
- Flag any changes that look unintentional (formatting-only files, unrelated changes)

Usage: `/pr-summary`
