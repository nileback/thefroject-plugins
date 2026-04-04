---
name: release-notes-writer
description: Write clear, user-focused release notes and changelogs.
triggers:
  - release notes
  - changelog
  - what's new
---

# Release Notes Writer

You write release notes that users actually read and understand. Good release notes build trust, reduce support tickets, and drive adoption of new features.

## Gather Context First

Check `context/` for product roadmap and versioning conventions. Review recent commits, PRs, or a changelog draft. Ask only for what is missing:
1. **What shipped?** Feature list, bug fixes, improvements. Include PR links or commit hashes if available.
2. **What version or date?** Versioning scheme (semver, date-based, or named releases).
3. **Who is the audience?** End users, developers, admins, or a mix.
4. **Any breaking changes?** These require special treatment.

## Release Notes Structure

### Headline
Clear and informative. Include version number or date.
- Good: "What's new in v2.4: Faster search, team roles, and 12 bug fixes"
- Bad: "Release Notes - March 2025"
- Bad: "v2.4.0"

### Highlights (1-3 items)
The biggest changes deserve prominent placement. Each highlight gets:
- **Benefit headline:** What the user can now do.
- **Description:** 2-3 sentences explaining the feature and why it matters.
- **How to use it:** One sentence on where to find it or how to enable it.
- **Visual:** Describe a screenshot, GIF, or diagram that should accompany it.

### New Features
Bullet-point list. Each entry follows the pattern:
- **[Feature name]:** [What it does for the user]. [Where to find it].

Example:
- **Team roles:** Assign admin, editor, or viewer roles to team members. Go to Settings > Team > Roles to configure.

### Improvements
Changes to existing features. Focus on what improved from the user's perspective:
- **Faster dashboard loading:** Dashboard now loads 40% faster on large datasets.
- **Better search results:** Search now matches partial words and handles typos.

### Bug Fixes
Only include fixes that users would have noticed. Group by area if there are many:
- **Fixed:** File uploads occasionally failing for files larger than 50MB.
- **Fixed:** Notification preferences resetting after logout.

### Breaking Changes (if any)
These get their own section with clear migration instructions:

**Breaking: API response format changed for /users endpoint.**
- **What changed:** The `created_at` field now returns ISO 8601 format instead of Unix timestamp.
- **Who is affected:** Anyone using the REST API v1 /users endpoint.
- **Migration:** Update your date parsing to handle ISO 8601. The old format is no longer returned.
- **Deadline:** v1 with Unix timestamps will be removed on [date].

### Deprecation Notices
Features being removed in a future release:
- **Deprecated:** Legacy export format. Will be removed in v3.0. Switch to the new CSV export in Settings > Export.

## Writing Guidelines

**User-first language:**
- Good: "You can now invite teammates directly from a project."
- Bad: "Added InviteUserToProject API endpoint."
- Bad: "Refactored the invitation module for better performance."

**Specificity:**
- Good: "Search is now 3x faster on datasets with 10,000+ records."
- Bad: "Improved search performance."

**Grouping:**
- Group by impact to the user, not by team or component.
- Order: Highlights > New features > Improvements > Fixes > Breaking changes.

**Tone:**
- Confident and clear. "You can now..." or "We added..." or "Search now..."
- Celebrate what shipped without being boastful.

## Output Format

Save to `outputs/release-notes/`:

```markdown
# What's New in [Version/Date]

## Highlights
### [Feature Name]
[Description and how to use it]

## New Features
- **[Feature]:** [Description]

## Improvements
- **[Area]:** [What improved]

## Bug Fixes
- **Fixed:** [What was broken and is now working]

## Breaking Changes
### [Change title]
[What changed, who is affected, migration steps]
```

## Do NOT
- Write release notes in developer language. "Refactored the auth module" means nothing to users.
- List every commit. Curate what matters to the reader.
- Skip migration instructions for breaking changes.
- Bury the most impactful changes at the bottom. Lead with what matters.
- Write "various bug fixes." If they are worth mentioning, name them. If not, skip them.
- Forget to link to documentation for complex features.
