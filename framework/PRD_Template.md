# AI PRD Template

| | |
|---|---|
| **Owner** | |
| **Product / Feature** | |
| **Status** | Draft / In Review / Approved |
| **Last Updated** | |

---

# 1. Discovery — Problem & Context

## 1.1 Problem & Opportunity

- **Problem:**
- **Why it matters (users & business):**
- **Evidence:**
- **Why now:**

## 1.2 Target Users

| Role | Buyer or User? | Goals | Constraints |
|---|---|---|---|
| | | | |
| | | | |

## 1.3 Pain Points

1.
2.
3.

## 1.4 Goals & Non-Goals

**Goals**
1.
2.
3.

**AI hypothesis:** If we build [X] for [user], they will [outcome] because [mechanism].

**Guardrail metrics** (must not regress)
-

**Non-goals**
-

---

# 2. Design — Solution Shape

## 2.1 Solution

Describe the solution in 2–3 sentences, then list the end-to-end user steps (mark AI-mediated steps).

1.
2.
3.

**Alternatives considered & why rejected:**
-

## 2.2 Features

**MVP**
1.
2.
3.

**Future**
-

## 2.3 Key Flows

- Wireframe / prototype link:
- Critical screens:
- AI moments: where input is captured, how output is shown, how users can correct it.

## 2.4 Non-Functional Requirements

- **Fallback:** What happens when the model fails or returns low-confidence output?
- **Latency target:**
- **Cost target:** $ per request / engagement
- **Accessibility / i18n:**

---

# 3. Build — AI Implementation

## 3.1 Model & AI Design

| Component | Model | Why | Rough cost/call |
|---|---|---|---|
| | | | |

- **Key capabilities relied on:** (context length, tool use, vision, JSON output, etc.)
- **Known limitations & mitigations:**
- **Inputs:** (fields, types, sources)
- **Output format:** (schema description — no need for full JSON)
- **RAG / retrieval:** (corpus, chunk strategy, embedding model, top-k) — skip if not applicable

## 3.2 Tech Stack

| Layer | Choice | Why |
|---|---|---|
| **Frontend** | | |
| **Backend / API** | | |
| **Orchestration** | | |
| **Auth** | | |
| **Database** | | |
| **Vector store** | | |
| **Model provider** | | |
| **Hosting** | | |
| **Observability** | | |

**Key constraints:** scalability target, latency budget, data residency, uptime SLO.

## 3.3 Evaluation

| Dimension | How measured | Target |
|---|---|---|
| Accuracy / factuality | | |
| Relevance | | |
| Hallucination rate | | |
| Latency | | |
| Cost | | |

- **Test cases:** typical, edge (missing data, ambiguous input, out-of-domain), adversarial
- **Method:** automated script / LLM-as-judge / human spot-check

---

# 4. Launch — Deploy & Operate

## 4.1 Launch Plan

| Phase | Audience | Goal | Exit criteria | Timing |
|---|---|---|---|---|
| Alpha | Internal | | | |
| Closed pilot | | | | |
| GA | | | | |

**Rollback plan:**

## 4.2 Success Metrics

| Layer | Metric | Target | Source |
|---|---|---|---|
| **North star** | | | |
| **User** | | | |
| **Business** | | | |
| **AI quality** | | | |
| **Guardrails** | | | |

## 4.3 Risks & Legal

- **Top risks & mitigations:**
- **Data handling:** storage, encryption, retention, deletion
- **Model provider terms:** zero-retention, no training on user data
- **Regulatory scope:** GDPR, SOC2, sector-specific
- **Content safety:** moderation, prompt-injection defense, audit logging

---

# Appendix

## Open Questions
-

## References & Links
- Wireframes:
- Prototype:
- Master prompt:
- Eval criteria / test set:
