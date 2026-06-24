---
name: process-optimizer
description: Analyze existing business processes and recommend improvements. Use when workflows feel slow, error-prone, or unclear.
triggers:
  - optimize process
  - improve workflow
  - process improvement
---

# Process Optimizer

Analyze business processes systematically to find friction, waste, and bottlenecks, then design targeted improvements.

## Phase 1 — Process Discovery

Before optimizing, understand the current state completely:

1. **Define boundaries** — Where does this process start (trigger event) and end (completion criteria)?
2. **Walk the process** — Follow a real item through the entire workflow. Do not rely on documentation alone; observe what actually happens
3. **Interview participants** — Ask each role: "What slows you down? What do you do that feels unnecessary? Where do mistakes happen?"
4. **Collect data** — Cycle time (end-to-end), processing time (hands-on work), wait time, error rate, volume, rework rate

## Phase 2 — Current State Map

Build a text-based process map using this format:

```
[Trigger] → Step 1 (Owner, Avg time) → [Decision?]
  → YES → Step 2a (Owner, Avg time) → ...
  → NO → Step 2b (Owner, Avg time) → ...
... → [End state]
```

For each step, capture:
| Step | Owner | Avg Duration | Wait Before | Tools Used | Error Rate |
|------|-------|-------------|-------------|------------|-----------|
| [N] | [Role] | [Time] | [Time] | [Tool] | [%] |

**Key metrics to calculate:**
- **Process efficiency ratio** = Processing time / Total cycle time. Below 25% indicates significant waste
- **Handoff count** — Every handoff introduces delay and error risk
- **Decision points** — Each adds complexity and potential for inconsistency
- **Rework loops** — Where does work flow backwards?

## Phase 3 — Waste Identification (Lean DOWNTIME)

Classify every waste using the eight Lean wastes:

| Waste Type | What to Look For | Example |
|-----------|-----------------|---------|
| **D**efects | Rework, errors, corrections | Report rejected and returned for fixes |
| **O**verproduction | Doing more than needed | Creating 5 approval levels when 2 suffice |
| **W**aiting | Idle time between steps | 3-day wait for manager approval on a $50 expense |
| **N**on-utilized talent | People doing work below their skill | Senior engineer doing manual data entry |
| **T**ransportation | Moving information between systems | Copy-pasting from email to spreadsheet to CRM |
| **I**nventory | Backlog buildup | 200 tickets in queue with no triage |
| **M**otion | Unnecessary steps or clicks | Logging into 4 systems to complete one task |
| **E**xtra processing | Over-engineering, gold-plating | Writing a full report when a Slack message would suffice |

## Phase 4 — Root Cause Analysis

For each major waste or bottleneck, use the "5 Whys" technique:

```
Problem: Invoices take 14 days to process
Why 1: Because they sit in the approval queue for 10 days
Why 2: Because the approver has 200+ items in their queue
Why 3: Because all invoices over $100 require their approval
Why 4: Because the approval threshold was set 5 years ago when the team was smaller
Why 5: Because no one has reviewed the approval policy since
Root cause: Approval threshold is outdated for current volume
```

## Phase 5 — Future State Design

Apply improvements in this priority order (the Lean hierarchy):

1. **Eliminate** — Remove the step entirely. Ask: "What happens if we stop doing this?"
2. **Simplify** — Reduce the complexity of the step. Fewer fields, fewer approvals, clearer criteria
3. **Combine** — Merge sequential steps done by the same person
4. **Automate** — Only automate after eliminating, simplifying, and combining. Automating a bad process makes it faster at being bad

For each proposed change, score it:

| Change | Waste Removed | Impact (1-5) | Effort (1-5) | Risk | Priority |
|--------|-------------|-------------|-------------|------|----------|
| [Description] | [Type] | [Score] | [Score] | [H/M/L] | [1-N] |

## Phase 6 — Implementation Plan

Group changes into waves:

### Wave 1: Quick wins (this week)
Changes with high impact and low effort that can be implemented immediately without approval.

### Wave 2: Tactical improvements (this month)
Changes that require coordination or minor system changes.

### Wave 3: Structural changes (this quarter)
Changes that require process redesign, system updates, or organizational alignment.

For each wave, define: owner, deadline, success metric, and rollback plan.

## Output Format

Save to `outputs/process-optimization-[process-slug].md` with:

- Current state process map with metrics
- Waste inventory table
- Root cause analysis for top 3 bottlenecks
- Future state process map
- Prioritized improvement list with effort/impact scores
- Implementation plan by wave
- Before/after metrics targets

## Do NOT
- Propose automation before eliminating unnecessary steps
- Optimize a process without measuring its current performance first
- Recommend changes without talking to the people who execute the process
- Design the future state without defining how to measure improvement
- Present all changes as equal priority — sequence by impact and effort
