# PRD Creation — Project Guide

This repo is an agentic pipeline for creating AI product requirement documents. It turns raw research and answers into a structured, dual-format PRD (Markdown + interactive HTML).

---

## Directory Guide

| Directory | Purpose |
|---|---|
| `.claude/agents/` | Specialized subagents: engineer, strategist, user_researcher |
| `.claude/commands/` | Slash commands — the executable workflow |
| `framework/` | Template-based working documents: PRD template, user research doc, HTML artifacts. These evolve with your project. |
| `inputs/` | Raw external data you bring in: interview transcripts, problem briefs, market reports, survey exports. |
| `outputs/` | Final deliverables: `prd.md` (descriptive) and `prd.html` (interactive with embedded artifacts). |

---

## Workflow (run in order)

```
1. Drop raw research files into inputs/
         ↓
2. /research-sync
   Reads inputs/, synthesizes with user_researcher agent → rewrites framework/user_research.md
         ↓
3. /prd-interview
   Guided Q&A through all PRD sections → saves answers to inputs/prd-answers.md
   Type "pause" at any time to stop; re-run to resume from where you left off.
         ↓
4. /update-artifacts
   Uses research + PRD answers → refreshes framework/mockups.html + framework/reusable_design_system.html
   Edit framework/data_flow.html manually (or ask Claude) to match your actual tech stack (section 3.3).
         ↓
5. /generate-prd
   Assembles everything → writes outputs/prd.md + outputs/prd.html
```

---

## Command Cheatsheet

| Command | What it does | Reads | Writes |
|---|---|---|---|
| `/research-sync` | Synthesize research into structured findings | `inputs/*` | `framework/user_research.md` |
| `/prd-interview` | Walk through PRD sections Q&A | `framework/PRD_Template.md`, `inputs/prd-answers.md` | `inputs/prd-answers.md` |
| `/update-artifacts` | Refresh HTML artifacts with real product content | `framework/user_research.md`, `inputs/prd-answers.md` | `framework/mockups.html`, `framework/reusable_design_system.html` |
| `/generate-prd` | Produce final PRD in two formats | `inputs/prd-answers.md`, `framework/user_research.md`, `framework/*.html` | `outputs/prd.md`, `outputs/prd.html` |

---

## Inputs Convention

Drop any of the following into `inputs/`:
- Interview transcripts (`.txt`, `.md`)
- Survey exports (`.md`, `.csv`)
- Problem brief or one-pager (`.md`)
- Competitive analysis notes (`.md`)
- Support ticket summaries (`.md`, `.txt`)

`/research-sync` will read all files in `inputs/` except `prd-answers.md` and `.gitkeep`.

---

## HTML Artifacts → PRD Sections

The three HTML files in `framework/` are embedded into `outputs/prd.html` at these sections:

| File | Embedded at |
|---|---|
| `framework/mockups.html` | Section 2.4 — Key Flows & Wireframes |
| `framework/reusable_design_system.html` | Section 2.3 / design reference |
| `framework/data_flow.html` | Section 3.3 — Tech Infrastructure |

---

## Agents

The three agents in `.claude/agents/` can be invoked at any time for ad-hoc review:
- `user_researcher` — synthesize research, identify pain points, refine personas
- `engineer` — assess technical feasibility, estimate effort, flag risks
- `strategist` — frame for leadership, write executive summaries, assess business impact
