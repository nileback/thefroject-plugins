---
name: github-community-triage
description: Scan open GitHub issues and pull requests, categorize by type and urgency, suggest labels and assignees, and produce a triage report. Use when managing community contributions or when the issue backlog needs attention.
triggers:
  - triage issues
  - github triage
  - community triage
---

# GitHub Community Triage

Scan the open issues and pull requests in a repository, classify them, and produce a prioritized triage report. This keeps the backlog actionable and community contributors unblocked.

## Phase 1 — Gather

1. List all open issues, sorted by most recently updated.
2. List all open pull requests, sorted by most recently updated.
3. For each item, note: title, author, labels, assignee, age (days open), last activity date, comment count.

## Phase 2 — Classify Issues

### By Type
Assign exactly one type to each issue:

| Type | Signals |
|------|---------|
| **Bug** | "doesn't work", "error", "crash", stack trace, reproduction steps |
| **Feature Request** | "would be nice", "add support for", "please consider" |
| **Question** | "how do I", "is it possible", "what does X mean" |
| **Documentation** | "docs say", "README is wrong", "outdated instructions" |
| **Duplicate** | Same root cause or request as another open issue |
| **Not Actionable** | Vague, no reproduction steps, unclear what is being asked |

### By Urgency

| Urgency | Criteria |
|---------|----------|
| **Critical** | Data loss, security vulnerability, complete feature broken, blocking multiple users |
| **High** | Important feature broken with workaround, regression from recent release |
| **Medium** | Bug with workaround, feature request with strong demand (many thumbs up) |
| **Low** | Minor cosmetic issue, edge case, nice-to-have feature |

## Phase 3 — Classify Pull Requests

| Status | Criteria |
|--------|----------|
| **Ready for review** | Tests pass, no conflicts, description is clear |
| **Needs work** | Tests failing, merge conflicts, missing description or tests |
| **Stale** | No activity in 14+ days, author has not responded to feedback |
| **Draft** | Explicitly marked as draft or WIP |

## Phase 4 — Suggest Actions

For each item, suggest one action:

### Issues
- **Label:** Suggest labels based on type and urgency
- **Assign:** Suggest an assignee based on the area of code affected (check CODEOWNERS or recent commit history)
- **Close:** Recommend closing duplicates, answered questions, and not-actionable issues (draft a close comment)
- **Milestone:** Suggest a milestone if the issue fits a planned release
- **Respond:** Draft a response for questions or issues needing clarification

### Pull Requests
- **Review:** Flag PRs that are ready and have waited >48 hours
- **Request changes:** Flag PRs with failing tests or missing descriptions
- **Close:** Recommend closing stale PRs (draft a polite close comment)
- **Merge:** Flag PRs that are approved, tests pass, and ready to merge

## Phase 5 — Report

Write the triage report to `outputs/triage-report-[date].md`:

```markdown
# Triage Report — [Date]
Repository: [owner/repo]
Open Issues: [count] | Open PRs: [count]

## Issues Needing Immediate Attention
| # | Title | Type | Urgency | Suggested Action |
|---|-------|------|---------|-----------------|

## PRs Ready for Review
| # | Title | Author | Age | Status |
|---|-------|--------|-----|--------|

## Stale Items (>14 days, no activity)
| # | Title | Type | Days Open | Suggested Action |
|---|-------|------|-----------|-----------------|

## Quick Wins (can be closed now)
| # | Title | Reason to Close | Draft Comment |
|---|-------|-----------------|---------------|

## Summary
- New since last triage: [count]
- Resolved since last triage: [count]
- Oldest open issue: #[number] ([days] days)
- Most active issue: #[number] ([comments] comments)
```

## Do NOT
- Close issues without drafting a comment explaining why
- Assign urgency based on how loudly someone complains — assess technical impact
- Label PRs as "stale" if the author is waiting on reviewer feedback (that is on the maintainers)
- Triage private or security-sensitive issues in a public report
