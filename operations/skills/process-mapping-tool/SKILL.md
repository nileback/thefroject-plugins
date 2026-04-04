---
name: process-mapping-tool
description: Document business processes end-to-end with workflow steps, owners, handoffs, timing, and improvement opportunities. Use when standardizing processes, onboarding team members, or identifying inefficiencies.
triggers:
  - process map
  - workflow documentation
  - process documentation
  - map this process
---

# Process Mapping Tool

Document how work actually flows, not how people think it flows. The gap between the two is where inefficiency lives.

## Input Required

1. **Process name** — what process are you mapping
2. **Process scope** — start point, end point, what is in and out of scope
3. **Process participants** — who is involved (roles, not just names)
4. **Current documentation** — any existing SOPs, wikis, or tribal knowledge
5. **Pain points** — known bottlenecks, errors, or complaints

## Process Mapping Steps

### Step 1 — Define the Process Boundaries

| Element | Detail |
|---------|--------|
| **Process name** | [Clear, specific name] |
| **Purpose** | [What outcome does this process produce?] |
| **Trigger** | [What initiates this process?] |
| **Start** | [First step/event] |
| **End** | [Final step/deliverable] |
| **In scope** | [What is included] |
| **Out of scope** | [What is explicitly excluded] |
| **Frequency** | [How often does this process run?] |
| **Volume** | [How many instances per period?] |

### Step 2 — Map the Current State (As-Is)

Document each step:

| # | Step | Owner | Input | Action | Output | System/Tool | Time | Decision? |
|---|------|-------|-------|--------|--------|------------|------|----------|
| 1 | [Name] | [Role] | [What is needed] | [What happens] | [What is produced] | [Tool used] | [Duration] | No |
| 2 | [Name] | [Role] | | | | | | Yes → Go to step X or Y |
| 3 | | | | | | | | |

### Step 3 — Identify Handoffs

Every handoff is a potential failure point:

| From | To | Handoff Method | Information Transferred | Risk of Loss/Delay |
|------|-----|---------------|------------------------|-------------------|
| [Role A] | [Role B] | [Email/Slack/Tool/Meeting] | [What gets passed] | [Low/Med/High] |

### Step 4 — Measure the Process

| Metric | Value | Benchmark |
|--------|-------|----------|
| **Total cycle time** | [End-to-end duration] | [Industry or internal target] |
| **Active work time** | [Time spent actually working] | |
| **Wait time** | [Time in queues or waiting] | |
| **Rework rate** | [% of instances requiring rework] | |
| **Error rate** | [% of instances with errors] | |
| **Handoffs** | [Number of handoffs] | |
| **Decision points** | [Number of decisions] | |
| **Systems touched** | [Number of different tools] | |

**Process efficiency = Active work time / Total cycle time × 100**

### Step 5 — Identify Improvement Opportunities

| Issue | Type | Impact | Root Cause | Proposed Fix | Effort |
|-------|------|--------|-----------|-------------|--------|
| [Bottleneck at step X] | Bottleneck | [Hours/$ wasted] | [Why it happens] | [Fix] | [L/M/H] |
| [Manual data entry between systems] | Waste | | | [Automate] | |
| [Approval required for low-risk items] | Over-processing | | | [Remove for <$X] | |
| [Rework after step Y] | Quality | | | [Add validation earlier] | |

**Common waste types:**
- **Waiting** — queues, approvals, handoffs
- **Over-processing** — steps that add effort but not value
- **Rework** — fixing errors from earlier steps
- **Motion** — switching between tools or systems
- **Handoffs** — each handoff risks information loss

### Step 6 — Design the Future State (To-Be)

Apply improvements and map the new process:

| Change | Before | After | Expected Impact |
|--------|--------|-------|----------------|
| [Eliminate step X] | [X hours] | [0 hours] | [Saves Y hours/week] |
| [Automate handoff] | [Manual email] | [Automated notification] | [Reduces errors by Z%] |
| [Combine roles] | [2 handoffs] | [0 handoffs] | [Saves N hours/instance] |

## Output Format

Save to `reference/process-[name].md`:

```markdown
# Process Map — [Process Name]
**Owner:** [Name/Role] | **Last updated:** [Date] | **Version:** [N]

## Overview
[Purpose, trigger, scope — 3-4 sentences]

## Current State
[Step table with timing and ownership]

## Metrics
[Key process metrics]

## Improvement Opportunities
[Ranked by impact and effort]

## Future State
[Improved process map]

## Implementation Plan
| Phase | Change | Owner | Timeline |
|-------|--------|-------|---------|
```

## Principles

- Map how the process actually works, not how it is supposed to work. Interview the people who do the work, not just the managers.
- The simplest process that achieves the outcome is the best process. Every step should justify its existence.
- Process documentation is maintenance, not a one-time project. Set a review cadence and an owner.
