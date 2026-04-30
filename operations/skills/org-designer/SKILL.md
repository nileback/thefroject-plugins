---
name: org-designer
description: Design or redesign organization structures. Use when a team is growing, restructuring, or experiencing coordination problems. Covers team topologies, reporting lines, spans of control, and role clarity.
triggers:
  - org design
  - team structure
  - organization structure
  - reporting lines
  - restructure the team
  - team topology
allowed-tools: []
---

# Org Designer

Design organization structures that support the team's actual work, not just its headcount.

## Writes
- `outputs/org-design-[context].md`

## Step 1: Understand Current State

Ask:
1. Current team size and projected growth (6-12 months)
2. Current structure (org chart, reporting lines)
3. What is working well
4. What is breaking (coordination failures, unclear ownership, bottlenecks)
5. Key workflows that cross team boundaries

## Step 2: Apply Team Topology Principles

Four fundamental team types:
- **Stream-aligned** — organized around a flow of work (product area, customer segment, value stream)
- **Enabling** — helps other teams adopt new capabilities (platform, DevEx, learning)
- **Complicated subsystem** — owns a complex domain requiring specialist knowledge
- **Platform** — provides self-service capabilities to reduce cognitive load on stream teams

Three interaction modes:
- **Collaboration** — working closely together (temporary, high-bandwidth)
- **X-as-a-service** — consuming another team's output via API/interface (low-bandwidth)
- **Facilitating** — one team helping another grow a capability (temporary by design)

## Step 3: Design the Structure

For each proposed team:
- **Name and mission** — what this team exists to do
- **Type** — stream-aligned, enabling, platform, or subsystem
- **Size** — target headcount (5-9 per team, smaller for complex domains)
- **Key roles** — who must be on this team for it to function independently
- **Interfaces** — how it interacts with other teams and which mode
- **Ownership** — what this team owns end to end (code, process, outcome)

## Step 4: Validate

Check the design against:
- **Cognitive load** — can each team hold their full domain in their heads?
- **Dependencies** — how many teams need to coordinate for a typical feature?
- **Career paths** — can people grow without leaving the team?
- **Span of control** — no manager has more than 8-10 direct reports
- **Single-threaded ownership** — every important thing has exactly one owner

## Step 5: Transition Plan

If restructuring an existing org:
- What changes first, what can wait
- Communication plan (who hears what, when)
- Interim structure if needed during transition
- Success metrics (how you know the new structure is working)
