# PRD Creation — AI-Powered Product Requirement Documents

An agentic pipeline built on Claude Code that turns raw research and stakeholder answers into a structured, dual-format PRD (Markdown + interactive HTML).

## How it works

```
inputs/          →   /research-sync   →   framework/user_research.md
                          ↓
                    /prd-interview    →   inputs/prd-answers.md
                          ↓
                   /update-artifacts  →   framework/mockups.html
                                          framework/reusable_design_system.html
                          ↓
                    /generate-prd     →   outputs/prd.md
                                          outputs/prd.html
```

Drop your raw research into `inputs/`, run the four commands in order, and get a complete PRD at the end.

## Quickstart

**1. Add your research files to `inputs/`**

Accepted formats: interview transcripts, survey exports, problem briefs, competitive analysis notes, support ticket summaries (`.txt`, `.md`, `.csv`).

**2. Synthesize research**

```
/research-sync
```

Reads all files in `inputs/` (except `prd-answers.md`) and rewrites `framework/user_research.md` with structured findings.

**3. Run the PRD interview**

```
/prd-interview
```

Guided Q&A through all PRD sections. Each section shows practical hints to help you answer well. Type `pause` to stop and resume later; type `skip` to defer a section.

**4. Refresh HTML artifacts**

```
/update-artifacts
```

Rewrites `framework/mockups.html` and `framework/reusable_design_system.html` with real product content from your research and answers. Edit `framework/data_flow.html` manually to match your actual tech stack.

**5. Generate the final PRD**

```
/generate-prd
```

Assembles everything into `outputs/prd.md` (descriptive) and `outputs/prd.html` (interactive with embedded design artifacts).

## Directory structure

```
inputs/                          # Raw research files you bring in
outputs/                         # Final deliverables (prd.md, prd.html)
framework/
  PRD_Template.md                # Structured template (4 sections, 12 sub-sections)
  prd-hints.md                   # Section-specific tips shown during /prd-interview
  user_research.md               # Synthesized research (written by /research-sync)
  mockups.html                   # Key flows & wireframes artifact
  reusable_design_system.html    # Design system artifact
  data_flow.html                 # Tech infrastructure diagram (edit manually)
.claude/
  commands/                      # Slash command definitions
  agents/                        # Specialized subagents (user_researcher, engineer, strategist)
```

## PRD structure

The template covers four phases of product development:

| Section | Contents |
|---|---|
| **1. Discovery** | Problem & opportunity, target users, pain points, goals & non-goals |
| **2. Design** | Solution shape, features (MVP vs future), key flows, non-functional requirements |
| **3. Build** | Model & AI design, tech stack, evaluation criteria |
| **4. Launch** | Launch plan, success metrics, risks & legal |

## Ad-hoc agents

Three specialized agents can be invoked at any time for focused review:

- `user_researcher` — synthesize research, identify pain points, refine personas
- `engineer` — assess technical feasibility, estimate effort, flag risks
- `strategist` — frame for leadership, write executive summaries, assess business impact

## Requirements

- [Claude Code](https://claude.ai/code) CLI

## References

- [html-effectiveness](https://github.com/ThariqS/html-effectiveness) by Thariq Shihipar — HTML artifact approach for embedding interactive design artifacts in PRDs
- [claude-code-pm-course](https://github.com/carlvellotti/claude-code-pm-course) by Carl Vellotti — PM workflow patterns for Claude Code that informed the interview and research-sync structure

## License

Apache 2.0 — see [LICENSE](LICENSE).
