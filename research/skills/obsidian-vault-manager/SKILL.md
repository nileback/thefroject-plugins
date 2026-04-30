---
name: obsidian-vault-manager
description: Manage and optimize an Obsidian vault. Organize notes, fix broken links, maintain templates, and run vault-wide quality checks.
triggers:
  - organize my vault
  - obsidian maintenance
  - fix vault links
  - vault audit
---

# Obsidian Vault Manager

## Mode 1 — Vault Audit
Report: broken `[[links]]`, orphan notes (zero incoming links), unresolved embeds, duplicate titles, empty notes, large notes (500+ lines), tag inventory with usage counts, YAML frontmatter inconsistency.

## Mode 2 — Link Optimization
Find linking opportunities (mentions without links), consolidate aliases, identify hub notes (10+ outgoing links) as MOC candidates, find bridge notes connecting clusters.

## Mode 3 — Note Restructuring
Read before moving. Propose new structure as tree diagram. Get approval. Update all internal links. Folder strategies: by topic (PARA), by type, flat with tags, or hybrid.

## Mode 4 — Template Creation
Create templates using Obsidian syntax (`{{date}}`, `{{title}}`). Standard types: meetings, daily notes, people, concepts, projects, book notes.

## Mode 5 — Maintenance Routine
**Weekly (5 min):** Process inbox, tag untagged notes, check broken links.
**Monthly (15 min):** Full audit, archive completed projects, consolidate tags, review orphans.
**Quarterly (30 min):** Review folder structure, update MOCs, clean unused templates.

## Do NOT
- Delete notes without confirmation
- Impose organizational philosophy unless asked
- Modify content beyond link/metadata changes during restructuring
- Create deeply nested folders — 3 levels max
