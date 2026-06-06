# Digital & AI — Agent Context

## Business

Digital & AI (digitalandai.co.uk) delivers fixed-price HubSpot implementations for property operators and growing teams. Ed Lobbett is the founder and sole operator, rebuilding from solo consulting back toward a small team. Deep HubSpot expertise, digital transformation background.

The business operates across three connected areas:
- **BD and pipeline** — cold outbound is the primary pipeline source right now, supported by LinkedIn and warm relationship work
- **HubSpot delivery** — the core service; configuration, reporting, integrations, AI readiness
- **Strategy and new ventures** — evaluating adjacent opportunities, developing content, building toward a broader operational scope

This agent operates across all three. Execution and memory layer only — strategy and judgment stays with Ed.

---

## Pipeline (as of early June 2026)

**Hivve** — finance integration project, should close next week. First appeared ~6 weeks ago. Chase if no movement by end of week.

**Kiasa** — new HubSpot implementation, significant pain. Delivery work should complete next week.

**Melissa** — cold outreach response last week, expected follow-up this week but hasn't come. Chase Monday morning.

No other live opportunities currently. Pipeline is thin — the outbound campaign is the primary mechanism for filling it.

---

## Offer shape

Current offer is HubSpot Sprints — fixed-price packaged remediation or additional function projects. Audits have been sold to larger companies but tend to convert into sprints rather than standing alone; worth reviewing the audit-to-sprint conversion at some point.

Areas under development:
- AI components within HubSpot delivery
- Fractional CDO/CCO positioning
- Lighter-touch ongoing support model — current marketing targets bleeding-neck pain which may be too direct and narrow the addressable market
- Property sector specialism — regulatory and digital changes make this worth developing properly
- More content and specifics needed across all of the above

---

## Pipeline and growth — 3-month view

**Pipeline source:** Outbound only. No inbound or referral currently running. Two undeveloped channels worth building toward: MSP partnerships (logic is sound, nothing done yet) and inbound via content (entirely dependent on content that doesn't exist yet).

**Now → early July (4-5 weeks):** Convert what's in the pipeline. Add LinkedIn as a parallel track to outbound and monitor performance more carefully — scale alone isn't moving the needle. Goal is a handful of deals commissioned before the summer gap closes. UK sales slow significantly from early July; anything not commissioned by then is unlikely until September.

**July → September:** Use the gap productively across three workstreams:
- Build credibility infrastructure — HubSpot content, AI market positioning, property sector specialism
- Fix Malt profile — currently ~60 views/month, nothing converting; this is a solvable problem
- Develop fractional CDO/CCO positioning ready to take to market in September

**By September:** A clearer offer stack (Sprints + fractional + lighter-touch support), credibility infrastructure that supports inbound, and a pipeline that isn't solely dependent on cold email volume.

---

## Current focus (as of early June 2026)

**Outbound campaign:** A custom sequencer (Vite/React + Supabase, at `~/Dev/outbound-ui`) is running cold email to HubSpot-positive companies in property and founder-led verticals. Apollo is the contact/company source. 18 sending inboxes, 270 sends/day capacity. The campaign has meaningful volume (930 step-1 sends) but weak response rate. Current diagnosis: Microsoft-heavy recipient mix, copy too broad, LinkedIn halo may have assisted early results. Next steps: Google MX test cohort, sharper pain-led copy, LinkedIn-assisted A-list, parallel high-context outreach. Mid-July is the relevant cash window.

**Outbound system build:** Zapmail Zapbox send integration is the next technical step — the UI and scheduling logic are complete, actual send execution is not yet wired. Reply polling and auto-cancellation follow.

**Context files for outbound detail:**
- `outbound_tooling_technical_doc` — full system architecture, Supabase schema, scheduling logic
- `outbound_data_sending_segmentation_handover.md` — current data state, batch history, performance analysis, next actions

---

## Stack

**Machine:** MacBook Air 15-inch, M2, 2023 — 8GB RAM, macOS  
**Shell:** zsh  
**Primary working directory:** `~/company-orchestration-lab/`  
**Outbound UI:** `~/Dev/outbound-ui/`

**This agent:** Hermes (`~/.hermes/`)  
**Memory:** Honcho (dialectic user modelling) + MEMORY.md + USER.md  
**Context:** This AGENTS.md (global) + project-level AGENTS.md files per workstream

**Model APIs:**
- Gemini 3.1 Flash — AI Studio API key (`GEMINI_API_KEY`) — default for most tasks, free tier 1,500 req/day
- DeepSeek V4 Flash — research and content tasks
- Claude Code — coding execution (Claude Pro subscription)

**MCP connections:**
- HubSpot — CRM, pipeline, contacts
- Google Drive — documents
- Gmail — email

**Research tools:**
- Tavily — web search ($0.008/query)
- Perplexity Sonar — deep research reports (~$0.50/report)

---

## Interaction modes

**In-office:** Claude Desktop (voice + Cowork) for thinking and judgment. Hermes handles background tasks, crons, and execution.

**Out of office:** Discord voice channel (private server) for real-time two-way voice. Telegram for async task triggers when talking isn't possible.

---

## Conventions

- Surface decisions involving clients, commercial commitments, or irreversible actions — do not act autonomously
- HubSpot: always confirm before making live changes to pipelines or contact records
- Outbound UI: never modify sequence_sends or sequence_contacts records without confirming — suppression errors are hard to unpick
- Research tasks: Tavily for web lookups, Perplexity for deep research reports
- Coding tasks: use Claude Code; keep sessions focused on one feature or file at a time to manage context size
- New projects and strategy: flag for Ed rather than developing a direction independently — surface the opportunity and a quick read, then wait
- Cost: flag if approaching Gemini free tier limit (1,500 req/day) in heavy sessions

---

## Project-level context files

As new workstreams develop, each gets its own AGENTS.md in its working directory. This global file covers stable business and stack context only. Do not expand this file with project-specific operational detail — put that in the relevant project file.

---

## What has been tried and ruled out

- **Paperclip** — org-chart agent governance, wrong abstraction, burned 4M tokens in first run. Not reinstalling.
- **Ruflo/RuVector** — Claude Code coding swarm tool, not suited to personal/business context memory. Not reinstalling.
- **Ollama local models** — not viable on 8GB M2. Needs 16GB+.
- **OpenCode** — bug: only shows OpenAI models. Not viable yet.
