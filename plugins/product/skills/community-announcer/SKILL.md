---
name: community-announcer
description: Draft release announcements, changelogs, and update posts formatted for GitHub Discussions, Discord, and newsletters. Use when shipping a release, publishing an update, or communicating changes to the community.
triggers:
  - announce release
  - write changelog
  - community update
---

# Community Announcer

Draft announcements that inform the community about what changed, why it matters, and what to do next. Produce versions for each channel.

## Input

Gather before writing:

1. **What changed.** Read recent commits, merged PRs, or a provided list of changes.
2. **Version number.** The release version (semantic versioning: major.minor.patch).
3. **Release type.** Breaking change, new feature, bug fix, maintenance, or mixed.
4. **Migration needed.** Are there breaking changes that require user action?
5. **Highlights.** The 1-3 changes that matter most to users.

## Changelog Format

Write a structured changelog following Keep a Changelog conventions:

```markdown
# Changelog

## [1.2.0] — YYYY-MM-DD

### Added
- New feature description (#PR)

### Changed
- Modified behavior description (#PR)

### Fixed
- Bug fix description (#PR)

### Removed
- Removed feature description (#PR)

### Breaking Changes
- What broke and how to migrate (#PR)
```

Rules:
- Group by type (Added, Changed, Fixed, Removed, Breaking Changes).
- Link each item to its PR or issue number.
- Write from the user's perspective: "Export now supports CSV format" not "Refactored export module."
- Put breaking changes in their own section with migration instructions.

## GitHub Release / Discussion Post

Structure:
1. **Headline.** Version number + one-line summary of the release theme.
2. **Highlights.** 2-3 bullet points covering the most impactful changes.
3. **Full changelog.** The detailed list from above.
4. **Migration guide.** Step-by-step instructions if there are breaking changes.
5. **Thank contributors.** Mention usernames of external contributors.
6. **What's next.** One sentence about the next planned milestone.

Tone: Informative, appreciative, concise. Celebrate the work without overselling.

## Discord Announcement

Structure:
1. **One-line hook.** What shipped and why it matters.
2. **Highlights.** 2-3 key changes in plain language.
3. **Link.** Full release notes or changelog URL.
4. **CTA.** "Update now" or "Try it out" with instructions.

Length: 500-800 characters. Use markdown formatting (bold, links). Avoid walls of text.

## Newsletter Section

Structure:
1. **Subject line hook.** Short, specific, action-oriented.
2. **Summary paragraph.** What changed and why it matters to the reader.
3. **Key changes.** 3-5 bullet points, plain language.
4. **CTA.** Link to release notes, upgrade instructions, or the product.

Length: 150-250 words. Personal tone.

## Writing Rules

- **Lead with impact.** "You can now export to CSV" not "We added CSV export functionality."
- **Skip internal details.** "Faster page loads" not "Refactored the rendering pipeline to use virtual DOM diffing."
- **Be honest about breaking changes.** Do not bury them. Put them first if they affect many users.
- **Credit contributors.** Name them in the GitHub release. Mention the number in Discord/newsletter.
- **One CTA per channel.** Do not overwhelm with links and actions.

## Output

Write all versions to `outputs/content/release-[version].md`:

```markdown
# Release Announcement: v[version]

## Changelog
[full changelog]

## GitHub Release Post
[formatted post]

## Discord Announcement
[formatted message]

## Newsletter Section
[formatted section]
```

## Do NOT
- Use "we're excited to announce" — just announce it
- List every commit — curate the most important changes
- Skip migration instructions for breaking changes
- Publish announcements that reference unreleased features
- Use different facts across channels — the changelog is the source of truth
