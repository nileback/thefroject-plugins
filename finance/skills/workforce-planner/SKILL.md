---
name: workforce-planner
description: Model workforce capacity and plan hiring against business goals. Use during annual planning, before a growth phase, or when capacity constraints are blocking delivery.
triggers:
  - workforce plan
  - hiring plan
  - capacity planning
  - headcount planning
  - staffing model
allowed-tools: []
---

# Workforce Planner

Model current capacity, forecast future needs, and produce a hiring plan that connects headcount to business outcomes.

## Writes
- `outputs/workforce-plan-[period].md`

## Step 1: Current State

Document:
1. **Current headcount** by team, role, and level
2. **Open roles** already approved
3. **Expected attrition** (historical rate or known departures)
4. **Contractor/vendor capacity** (non-permanent workforce)
5. **Current utilization** — are people overloaded, underloaded, or balanced?

## Step 2: Demand Forecast

Connect hiring to business goals:
- What are the company/team goals for the next 6-12 months?
- What work is required to hit those goals?
- What capacity gaps exist between current state and required work?
- What is the cost of not hiring (delayed projects, burnout, quality issues)?

For each gap:
- Role needed (title, level, key skills)
- Full-time vs. contractor
- When the capacity is needed (not when posting starts — when the person must be productive)
- Work backward from productive date: minus ramp time, minus hiring time

## Step 3: Build the Model

| Role | Current | Needed | Gap | Priority | Start By | Productive By |
|---|---|---|---|---|---|---|

Priorities: Critical (blocks goals), High (significant impact), Medium (improves quality), Low (nice to have).

## Step 4: Budget and Tradeoffs

For each role:
- Estimated compensation range
- Total cost (salary + benefits + equipment + ramp)
- Alternative to hiring (redistribute, automate, deprioritize)

Flag tradeoffs: "We can hire 2 engineers OR 1 engineer + 1 designer. Option A ships faster, Option B ships better."

## Step 5: Hiring Timeline

Create a phased plan:
- Q1: [roles] — rationale
- Q2: [roles] — rationale
- Dependencies: "Role X must be hired before Role Y because..."

Include: job description drafts, interview process outline, and success metrics for each hire.
