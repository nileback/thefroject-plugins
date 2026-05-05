# The Froject Customer Success Plugin

Customer success toolkit: churn prevention, health scoring, QBRs, renewal strategy, and escalation frameworks.

## Install

```
/plugin marketplace add bjorn-ingmanson/thefroject-plugins
/plugin install thefroject-customer-success
```

## Skills (61)

- **Project Manager** — Plan, track, and manage projects and tasks
- **Meeting Summarizer** — Summarize meetings with actions and decisions
- **Email Writer** — Write effective emails for sales, marketing, and operations
- **Presentation Builder** — Create structured slide decks and presentation content
- **Business Case Builder** — Build investment cases with financial modeling and ROI analysis
- **Onboarding Guide** — Create onboarding docs and walkthroughs for new team members
- **Morning Briefing** — Generate daily briefings from tasks, calendar, and priorities
- **Case Study Writer** — Transform customer stories into compelling case studies
- **Customer Success Guide** — Create customer success playbooks, health scores, and retention strategies
- **Stakeholder Updater** — Write concise stakeholder and status updates
- **Email Response Simulator** — Simulate how a recipient would react to your email before sending it
- **Skill Creator** — Create new Claude Code skills that extend your workspace capabilities
- **Workflow Orchestrator** — Route complex tasks to specialized sub-skills using parallel agents
- **Churn Prevention** — Design cancel flows, save offers, and retention strategies
- **Referral Program Designer** — Design referral and affiliate programs that drive growth
- **Health Score Builder** — Design and calculate customer health scores from usage, support, and engagement signals
- **Renewal Strategist** — Plan renewal timing, pricing strategy, and expansion opportunities
- **QBR Builder** — Prepare quarterly business review presentations with metrics and narrative
- **Escalation Framework** — Document, route, and manage customer escalations systematically
- **Expansion Opportunity Analyzer** — Identify and prioritize upsell and cross-sell opportunities in customer accounts
- **Build My Profile** — Analyze your communication across connected tools to build a personal working style and writing style profile
- **Extract My Voice** — Analyze your actual writing across Slack, Gmail, and Notion to create a voice reference Claude can match
- **Meeting Prep Brief** — Prepare a one-page brief before any meeting, adapted by meeting type
- **Context Budget Analyzer** — Audit token overhead of your workspace components
- **Quality Gate** — SHIP/FIX/BLOCK verdict before publishing any content
- **Decision Tracker** — Track decisions across sessions with status classification
- **Session Debrief** — Interactive end-of-session capture of progress, decisions, and carry-forward items
- **Workspace Optimizer** — Audit your workspace for bloat, gaps, and optimization opportunities
- **Retention Diagnostician** — Analyze retention patterns across cohorts and identify why users leave
- **Model Strategy** — Choose the right Claude model for each task based on complexity and cost
- **VoC Synthesis** — Turn raw customer voice data into structured buyer language and insights
- **Google Workspace Ops** — Manage Google Drive, Sheets, Docs, Calendar, and Gmail through structured workflows
- **Customer Billing Ops** — Manage subscription lifecycles, churn triage, refunds, and billing workflows
- **Docs Freshness Auditor** — Scan documentation for stale content, broken links, and outdated references
- **Workspace Onboarding** — Systematically explore and document a workspace for someone new to the project
- **Sequential Handoff** — Pass work through ordered stages where each agent builds on the previous result
- **Map-Reduce** — Run the same analysis across multiple targets in parallel, then merge results into one report
- **Supervisor** — Execute multi-step processes with validation checkpoints and automatic retry on failure
- **Swarm** — Dynamic investigation where each agent's findings determine what to explore next
- **Debate** — Multiple agents argue different positions on a decision, then a judge synthesizes the best answer
- **Maker-Checker** — One agent creates output, a separate agent validates it, looping until the checker approves
- **Watchdog** — Background agent monitors for problems while the main agent works, alerting when triggered
- **Review Miner** — Mine customer reviews for pain points, trigger moments, objections, and ad-ready language
- **Skill Learnings Tracker** — Maintain LEARNINGS.md files per skill that capture what works and what fails, then graduate repeated patterns into permanent rules
- **User Profile Interview** — Build a personal profile through a short interview to help Claude adapt to your working style and preferences
- **SOP to Skill Converter** — Turn standard operating procedures and process documents into installable Claude Code skills
- **File Format Converter** — Convert documents into Markdown so Claude can read and work with them
- **Plan Tracker** — Maintain structured plan files that track tasks, status, and progress across sessions
- **XLSX Handler** — Read, write, and clean Excel (.xlsx) files. Use when the user mentions Excel, .xlsx, spreadsheet, workbook, formulas, or pivot tables.
- **DOCX Handler** — Read and write Microsoft Word (.docx) files. Use when the user mentions Word, .docx, document, contract, report, or wants to draft, edit, or extract text from a Word file.
- **PDF Handler** — Read PDFs (contracts, research reports, vendor docs) and extract text, tables, or structured data. Use when the user mentions PDF, .pdf, contract review, paper, or wants to extract or summarize.
- **PPTX Handler** — Generate, edit, or extract content from PowerPoint (.pptx) files. Use when the user mentions PowerPoint, slide deck, .pptx, or wants to build or edit slides programmatically.
- **Community Marketing** — Plan and grow online communities (Discord, Slack, forum, Reddit) for product growth and brand loyalty. Use when the user mentions community strategy, Discord/Slack community, community-led growth, brand advocates, ambassador program, or word-of-mouth.
- **Customer Feedback Orchestration** — Run an end-to-end customer feedback program: survey design, channel routing, categorization, close-the-loop response. Distinct from voc-synthesis (one-shot synthesis) — this is the program. Use when the user mentions feedback program, NPS pipeline, customer feedback loop, or VoC operations.
- **Value Realization Scorer** — Score customer accounts on likelihood-to-renew based on value realization. The 2026 CS shift — capture intended outcomes at deal close, score actual outcomes, output value gap. Use when the user mentions likelihood-to-renew, value realization, value gap, or wants to replace static health scores.
- **Customer Journey Mapping** — Map the full customer journey — awareness, evaluation, onboarding, adoption, expansion, renewal — with stage definitions, signals, and owner per stage. Use when the user mentions customer journey, journey map, lifecycle map, stages of adoption, or wants to design the CS playbook.
- **Renewal Orchestration** — Multi-step renewal program: 90/60/30/0-day playbook with executive sponsor outreach, value-realization meetings, and contract logistics. Distinct from renewal-strategist (single-deal). Use when the user mentions renewal program, renewal motion, 90-day renewal, or designing a renewal cadence.
- **Weekly Plan** — Set 3-5 priorities for the week ahead with a realistic schedule
- **Weekly Review** — Review the week — wins, misses, learnings, and carry-forward decisions
- **Quarterly Plan** — Set 3-5 strategic priorities for the quarter that align with longer-term goals
- **Outputs Triage** — Route orphan files to the right subdirectory and surface scattered tasks

## Commands (11)

- **/context-save** — Save current session context for future reference
- **/morning-brief** — Generate a morning briefing from tasks and context
- **/draft** — Quick-draft content (blog, email, social post, copy)
- **/brief** — Create a brief or summary document from context
- **/outreach** — Draft personalized outreach emails with research
- **/stakeholder-update** — Draft a concise stakeholder or status update
- **/demo-deck** — Build an interactive demo deck for a qualified lead
- **/sow** — Generate a statement of work ready for signature
- **/deal-update** — Generate a weekly pipeline and deal status update
- **/pipeline-qbr** — QBR cycle pipeline: health scoring, QBR deck, renewal strategy, stakeholder update
- **/intelligence** — Capture and recall GTM learnings (what worked, what did not, by segment)

## Rules (9)

- **Git Workflow** — ---
- **Brand Voice** — ---
- **Content Guidelines** — ---
- **Confidentiality** — ---
- **Context Management** — ---
- **Prompt Hygiene** — ---
- **Agent Delegation** — ---
- **Output Verification** — ---
- **Session Continuity** — ---

## About

Built from [The Froject](https://thefroject.com) template library. Get a full workspace tailored to your role at [thefroject.com](https://thefroject.com).

## License

MIT
