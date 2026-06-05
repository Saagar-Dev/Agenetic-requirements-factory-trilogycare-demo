# 🏭 Agenetic-requirements-factory-trilogycare-demo

> Paste a messy business problem. 6 specialist BA agents work simultaneously to produce a complete, engineer-ready requirements package — including a visual process flow diagram and entity-relationship diagram.

[![Built with Claude](https://img.shields.io/badge/Powered%20by-Claude%20Haiku-orange)](https://anthropic.com)
[![Agentic AI](https://img.shields.io/badge/Type-Multi--Agent-blueviolet)](https://docs.anthropic.com)
[![Pure HTML](https://img.shields.io/badge/Stack-Vanilla%20HTML%2FJS-blue)](https://developer.mozilla.org)

---

## What Is This?

A single-file agentic AI demo that turns a rough stakeholder description into a complete engineering requirements package in real time. It directly demonstrates the core deliverable of a Technical BA / Solutions Analyst role: *producing artefacts that engineers can act on without a follow-up call.*

**The Scenario:** You paste in a messy business problem — the kind of notes you'd get from a discovery call. Six specialist agents immediately start working in parallel, each producing a different professional artefact. The results appear live as each agent writes sections.

---

## The 6 Agents

| Agent | Emoji | Specialty | Primary Output |
|-------|-------|-----------|----------------|
| **Scout** | 🔭 | Process Analyst | Current state process map + **visual swim-lane flow diagram** |
| **Scribe** | 📝 | Requirements Analyst | Numbered FRD + user stories with Gherkin `Given/When/Then` |
| **Schema** | 🗃️ | Data Analyst | Data dictionary + **visual entity-relationship diagram** |
| **Nexus** | 🔌 | Integration Analyst | OpenAPI-style endpoint specs with request/response payloads |
| **Guard** | 🛡️ | Risk & QA Analyst | RAID log + UAT test scripts (TC-001, TC-002…) |
| **Exec** | 📊 | Executive Summariser | CIO-ready 1-pager (waits for other 5 to complete first) |

---

## 8 Output Tabs

| Tab | Type | Content |
|-----|------|---------|
| 🔭 **Process Flow** | Text | Step-by-step current state, actors, pain points, automation opportunities |
| 📊 **Process Diagram** | **Visual SVG** | Swim-lane flowchart — actors as columns, steps as shapes, decisions as diamonds |
| 📝 **User Stories** | Text | FR-001, FR-002... + Given/When/Then stories with priority and story points |
| 🗃️ **Data Model** | Text | Entity descriptions, field specs, data dictionary |
| 🔗 **ER Diagram** | **Visual SVG** | Entity boxes with field types, PK/FK markers, relationship lines and cardinality |
| 🔌 **API Spec** | Text | Endpoint specs, request/response JSON payloads, auth patterns, error codes |
| 🛡️ **Risk + UAT** | Text | RAID log with severity, UAT test scripts with expected results |
| 📊 **Exec Summary** | Text | Problem, solution, business case, timeline, resources, top risks |

---

## What Each Output Looks Like

### User Stories (Scribe — Gherkin format)
```
US-003 · Digital KYC Verification  [Priority: High] [Story Points: 5]

As a new B2B client
I want to complete identity verification digitally
So that my account is approved within 24 hours

GIVEN I have completed the registration form and uploaded documents
WHEN I submit my application
THEN my ABN is validated against the ASIC API in real time
AND a credit check is triggered via CreditorWatch
AND I receive an email confirmation within 2 minutes

Acceptance Criteria:
✓ ABN validation returns result within 3 seconds
✓ Rejected ABNs display a clear error message with ASIC reference
✓ Documents are scanned for fraud indicators before approval
```

### API Spec (Nexus — OpenAPI style)
```
POST /api/v1/clients/onboard
Auth: Bearer token (OAuth 2.0, scope: client:write)
Content-Type: application/json

Request:
{
  "abn": "string (11 digits, validated)",
  "business_name": "string (max 200 chars)",
  "primary_contact": {
    "name": "string",
    "email": "email format",
    "phone": "AU mobile +61 format"
  },
  "documents": [{
    "type": "DRIVER_LICENCE | PASSPORT | MEDICARE",
    "file_url": "string (pre-signed S3 URL)"
  }]
}

Response 201: { "client_id": "uuid", "status": "PENDING_KYC" }
Errors: 400 (validation), 409 (ABN exists), 503 (KYC service down)
```

---

## Visual Diagrams

### Process Flow Diagram (📊 tab)
Rendered as an SVG swim-lane diagram directly in the browser:
- **Columns** = actors (e.g. Customer, System, Finance Team, External API)
- **Pill shapes** = start and end points
- **Rectangles** = process steps, colour-coded by actor
- **Diamonds** = decision points with Yes/No branches
- **Dashed arrows** = cross-lane handoffs
- Click **⤢ Full Screen** to zoom in

### ER Diagram (🔗 tab)
Rendered as an SVG entity-relationship diagram:
- Entity boxes with amber header and field rows
- 🔑 Primary keys highlighted green with `PK` badge
- 🔗 Foreign keys highlighted blue with `FK` badge
- Bezier curve relationship lines with cardinality labels (1:1, 1:N, N:M)
- Click **⤢ Full Screen** to zoom in

---

## PDF Export

Click **⬇ Export as PDF** in the victory screen. This opens a print-ready window containing:

- **Dark cover page** — project name, brief excerpt, stats (sections, flags, agents, diagrams)
- One page per completed tab
- Both SVG diagrams rendered on dark backgrounds with full colour
- All code blocks, tables, and Gherkin stories formatted for print
- Section IDs, titles, and agent attribution throughout

Use your browser's print dialog to save as PDF.

---

## 4 Built-In Example Briefs

| Example | Business Context |
|---------|-----------------|
| 🏦 **Fintech onboarding** | B2B fintech, manual KYC, 200 clients/month, ASIC compliance, Thought Machine Vault |
| 🧾 **Invoice automation** | 400 invoices/month, Netsuite ERP, manual PO matching, $50k approval threshold |
| 🎫 **AI support routing** | 800 tickets/day, Zendesk, 8 queues, P1/P2 SLA, fraud flagging |
| 📦 **Inventory sync** | Shopify + Deposco WMS, 1,200 orders/day, $15k/month lost sales |

---

## How It Maps to the Role

| JD Requirement | What the Demo Proves |
|----------------|---------------------|
| "Write requirements engineers can act on without a follow-up call" | Scribe + Nexus output — Gherkin stories, OpenAPI specs, specific field names |
| "Build and test agentic prototypes to validate a hypothesis" | This demo IS the prototype — running, live, Claude API |
| "Produce clean artefacts at every stage" | 8 tabs, each a different artefact type |
| "Exec-readable summaries" | Exec tab — CIO 1-pager with timeline and resource ask |
| "Lead technical discovery with operational teams" | Scout maps full process, actors, system touchpoints |
| "Agentic / MCP build experience" | 6 parallel agents, tool use, cross-agent sequencing |
| "Identify automation opportunities end-to-end" | Scout explicitly flags automation candidates |

---

## Mission Progress Bar

A real-time amber progress bar sits above the agent list:
- Fills as agents complete (averaged across all 6 agent progress values)
- Label shows: `3 / 6 agents complete · 2 running` + `12 sections · 8 flags`
- Transitions **green** when all 6 agents finish

---

## Architecture

```
6 agents sharing a global rate limiter (2.0s gap = ~30 calls/min)

Scout  Scribe  Schema  Nexus  Guard         Exec (waits)
  |      |       |       |      |               |
  ▼      ▼       ▼       ▼      ▼               ▼
analyse_brief → create_diagram → write_section → flag_item
                     |
               [SVG rendered client-side]
               [Injected into visual tab]
```

- **Exec agent waits** for all 5 other agents to complete, then reads their outputs and synthesises the executive summary
- **Diagram fallback**: if Scout or Schema finish without calling the diagram tool, a dedicated fallback API call fires automatically
- **Message trimming**: conversations are safely trimmed keeping `msgs[0]` + last 8 messages, never splitting a tool_use/tool_result pair

---

## Running Locally

```bash
# Serve over HTTP (required — file:// blocks API calls)
npx serve .
# or
python3 -m http.server 8080

# Open
open http://localhost:8080/req_factory.html
```

Enter your Anthropic API key (`sk-ant-...`) in the intro screen.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| AI | Claude Haiku (`claude-haiku-4-5-20251001`) |
| Markdown rendering | marked.js v9 |
| Diagrams | Pure SVG (no library) |
| Build | None — single HTML file, zero dependencies |

---

## About

Built by **Saagar Devadiga** — Data Engineer & AI Developer, Brisbane, Australia.
MSc Data Science · Queensland University of Technology

> *"The role asks you to stand up a Claude agent before bringing it to the engineering team. This is that agent — except it produces the entire requirements package the engineering team needs."*

---
*Powered by [Anthropic Claude](https://anthropic.com) · Diagrams rendered in pure SVG*
