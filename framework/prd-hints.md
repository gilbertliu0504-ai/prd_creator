# PRD Interview Hints

Section-specific tips for the `/prd-interview` skill. One tip per section — practical guidance on what a good answer looks like and what to avoid.

---

## 1.1 Problem & Opportunity

💡 **Tip:** Start with a single concrete user complaint or real data point (a support ticket, a quote, a metric). Describe the problem without mentioning your solution — if the problem statement implies a specific fix, it's too narrow.

---

## 1.2 Target Users

💡 **Tip:** One primary persona is enough for v1. Pick the user with the most to lose if the problem isn't solved — that's your primary. Secondary users can be listed briefly. Avoid vague descriptors ("busy professionals") — tie the role to a specific context ("a compliance officer at a 50-person fintech").

---

## 1.3 Pain Points

💡 **Tip:** List only the 2–3 friction points that drive users to abandon the current process or look for alternatives. Don't try to be exhaustive — if a pain point doesn't make users switch tools or complain, leave it out.

---

## 1.4 Goals & Non-Goals

💡 **Tip:** For the AI hypothesis, complete the sentence naturally: "If we build [X] for [user], they will [outcome] because [mechanism]." If the mechanism feels forced, the AI angle may not be justified yet — that's okay to flag. For non-goals, be explicit: "We are NOT building X because Y" prevents scope creep later.

---

## 2.1 Solution

💡 **Tip:** Describe the solution as if explaining it to someone who hasn't seen any screens — in 2–3 plain sentences. If you need more than that, the concept isn't focused enough yet. For the workflow steps, mark AI-mediated steps (e.g., "3. [AI] Summarizes the document") so it's clear where intelligence is added.

---

## 2.2 Features

💡 **Tip:** MVP should be embarrassingly small. A good check: can you ship it in 6–8 weeks? If you have more than 4 MVP features, cut the one you're least confident users will use. The "Future" list is just as important — writing it down means you're deferring intentionally, not forgetting.

---

## 2.3 Key Flows

💡 **Tip:** A rough Figma frame or hand-drawn sketch linked here is more useful than a paragraph of description. If nothing visual exists yet, name the 1–2 screens that matter most and describe the AI moment on each (what the user inputs, what the model does, how output is shown, and how the user can correct it).

---

## 2.4 Non-Functional Requirements

💡 **Tip:** Latency and fallback are the two you'll regret leaving blank. For latency: set a target users would actually notice if crossed (e.g., "first token < 2s"). For fallback: spell out what happens when the model times out or returns garbage — graceful degradation is almost always better than an error screen.

---

## 3.1 Model & AI Design

💡 **Tip:** If you're unsure which model to use, default to the most capable available and note cost as a risk to revisit. For inputs/outputs, be concrete about types (text, file, structured JSON) — this becomes the API contract for engineering. Skip the full JSON schema here; a description of the shape is enough.

---

## 3.2 Tech Stack

💡 **Tip:** Start with the minimum viable stack: frontend + backend + database + model provider. Add layers (vector store, queue, cache) only when you have a specific reason. For the "Why" column, one phrase is enough — "already in use", "managed service reduces ops overhead", "meets data residency requirements."

---

## 3.3 Evaluation

💡 **Tip:** Pick 2–3 dimensions that actually matter for your product — don't fill in every row for completeness. Accuracy and latency are almost always relevant. For targets, be specific: "hallucination rate < 5% on production sample" beats "low hallucination." If you don't have a baseline yet, write "TBD — establish in alpha."

---

## 4.1 Launch Plan

💡 **Tip:** Alpha → GA is the minimum viable launch plan. Add a closed pilot phase only if you have specific early adopters lined up. For exit criteria, be concrete: "10 users complete a full session with no critical bugs" is a real exit criterion; "stable enough" is not.

---

## 4.2 Success Metrics

💡 **Tip:** Set the north star metric first — the one number that proves the product is working. Everything else is diagnostic. If you can't pick a single north star, the goal in section 1.4 may be too vague. For AI quality metrics, connect them to user outcomes: "rubric pass rate > 85%" only matters if it correlates with user satisfaction.

---

## 4.3 Risks & Legal

💡 **Tip:** List your top 2 risks with a mitigation each — more than that and the section loses signal. The most common AI product risks are hallucination/accuracy failures and cost overrun at scale. For legal, keep it short unless you're handling PII, health data, or operating in a regulated industry — in those cases, flag it early and loop in legal before launch.
