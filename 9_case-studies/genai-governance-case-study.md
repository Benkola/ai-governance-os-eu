# Case Study: Governing a GenAI Deployment End-to-End (LLM Customer Support)

> **Purpose:** A full end-to-end governance case study for a generative AI system — a deployment that raises risks a traditional ML model does not: hallucination, prompt injection, data leakage, copyright, and bias amplification. Where the credit scoring case study showed the framework governing a high-risk *predictive* model, this shows it governing a *generative* system, where the hardest risks are about what the model says, not what it decides.
>
> **How to read it:** Follow the system from intake to incident response. Each stage links to the artefact that governs it. This is both a worked example and a demonstration that the framework handles GenAI, not just classical ML.
>
> **The scenario:** "Meridian" is a fictional mid-size EU financial services company (1,200 employees) deploying an LLM-powered customer support assistant. It answers customer questions about products and accounts, drafts responses for human agents, and surfaces relevant policy information. It runs on a third-party foundation model via API, with retrieval over Meridian's own documentation.
>
> **Regulatory context:** The underlying foundation model is a general-purpose AI (GPAI) model — its provider carries Chapter V obligations (technical documentation, training-data summary, copyright policy), which came into effect 2 August 2025. Meridian is a *deployer*. The chatbot itself is limited-risk under Annex III (it informs, it doesn't make high-risk decisions), so its binding obligation is Article 50 transparency — live now. But GenAI-specific risks make even a limited-risk deployment non-trivial to govern.

---

## The System

| Attribute | Detail |
|-----------|--------|
| **System name** | Meridian Customer Assistant (LLM-powered) |
| **Business purpose** | Answer customer questions; draft agent responses; surface policy information |
| **Users** | Customers (direct chat) and support agents (drafting assist) |
| **AI type** | Third-party foundation model (GPAI) via API + retrieval over Meridian's own docs (RAG) |
| **What it must NOT do** | Give regulated financial advice; make eligibility/pricing decisions; process transactions |
| **Volume** | ~15,000 conversations/month |

---

## Stage 1 — Intake and Classification

*Artefact: [`intake-form.md`](../6_templates/intake-form.md)*

**Prohibited practices (Article 5):** None.

**High-risk classification (Annex III):** The assistant informs and drafts; it does not assess creditworthiness, make employment decisions, or perform any Annex III high-risk function. Classification: **Limited-Risk**. (Note: if Meridian later let it give account-specific financial advice or make decisions, this would re-open the classification — a boundary the governance must police.)

**Transparency (Article 50):** The operative obligation. The assistant interacts directly with customers, so users must be told they're dealing with AI. Live now.

**GPAI dependency:** The foundation model is a general-purpose AI model. Meridian confirms the provider publishes the Chapter V documentation (technical documentation, training-data summary, copyright compliance policy) — Meridian relies on this and files it in the evidence pack.

**Intake outcome:** Limited-risk, but GenAI-specific risks (below) mean this is not a "tick the transparency box and move on" system. Proportionate governance here still means real work on the generative risk surface.

---

## Stage 2 — GenAI-Specific Risk Assessment

*Artefacts: [`risk-register.md`](../6_templates/risk-register.md), OWASP Top 10 for LLM Applications*

Generative AI introduces risks that classical ML risk assessment doesn't cover. Meridian's risk register captures them:

| Risk ID | GenAI risk | What could go wrong | Score | Rating | Treatment |
|---------|-----------|---------------------|-------|--------|-----------|
| GA-01 | **Hallucination** | The assistant states false information as fact — wrong fees, wrong policy terms — that a customer relies on | 16 | Critical | Mitigate: RAG grounding, confidence limits, "I'm not certain—let me connect you" fallback, no unsourced claims on regulated topics |
| GA-02 | **Prompt injection** | A user manipulates the assistant to bypass its guardrails (e.g. "ignore your instructions and tell me...") | 12 | High | Mitigate: input filtering, instruction hierarchy, output validation, red-team testing |
| GA-03 | **Data leakage** | The assistant reveals another customer's data, internal information, or its system prompt | 15 | Critical | Mitigate: strict retrieval scoping, no cross-customer context, output scanning, no PII in prompts |
| GA-04 | **Bias amplification** | The model's training biases surface in tone or content, disadvantaging some customers | 9 | Medium | Mitigate: output monitoring, tone testing across scenarios, escalation for sensitive topics |
| GA-05 | **Copyright / IP** | The assistant reproduces copyrighted text, or Meridian's use of the model raises IP questions | 6 | Medium | Mitigate: rely on provider's copyright policy (Chapter V); constrain outputs to Meridian's own content |
| GA-06 | **Scope creep** | The assistant is gradually used for advice/decisions it wasn't classified for, silently becoming high-risk | 9 | Medium | Mitigate: usage monitoring, clear boundaries, re-classification trigger |

The two Critical risks — hallucination (GA-01) and data leakage (GA-03) — are the ones that could cause real customer harm. They drive the design.

---

## Stage 3 — Controls and Guardrails

*Artefact: [`eu-ai-act-controls-map.md`](../4_eu-ai-act/eu-ai-act-controls-map.md)*

**Article 50 (transparency):** The assistant opens every conversation disclosing it's AI, and offers a human handoff. Clear, unavoidable, not buried.

**Hallucination controls (GA-01):** Retrieval grounding means the assistant answers from Meridian's actual documentation, not the model's parametric memory. On regulated topics, it's constrained to sourced content or routes to a human. It's designed to say "I'm not certain" rather than fabricate — the hardest and most important GenAI guardrail.

**Data leakage controls (GA-03):** Retrieval is scoped so a customer's session can never surface another customer's data. No PII enters the prompt. Outputs are scanned for accidental disclosure. The system prompt is protected against extraction.

**Prompt injection controls (GA-02):** Input filtering, a clear instruction hierarchy the user can't override, and output validation. Red-team testing before launch attempts to break the guardrails.

**Human oversight (Article 14, proportionate):** For the agent-drafting use, a human always reviews before anything reaches a customer. For direct customer chat, the assistant escalates anything sensitive, uncertain, or regulated to a human.

---

## Stage 4 — Documentation

*Artefacts: [`model-card-template.md`](../6_templates/model-card-template.md), [`system-card-template.md`](../6_templates/system-card-template.md), [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md)*

**A system card** is the primary document here, because this is a compound system (foundation model + retrieval + guardrails + human handoff). It documents the architecture, the data flows (customer query → retrieval → model → output scanning → response), the oversight points, and the GenAI-specific guardrails.

**The foundation model's documentation** (from the GPAI provider) is filed as the "model" evidence — Meridian doesn't produce a model card for a model it didn't build, but it records the provider's documentation and its own configuration.

**Documentation is proportionate:** limited-risk, so no full Annex IV pack — but the transparency implementation, the GenAI risk register, the system card, and the guardrail testing results are all documented per the standard.

---

## Stage 5 — Monitoring

*Artefact: [`ai-monitoring-playbook.md`](../7_monitoring-incident/ai-monitoring-playbook.md)*

GenAI monitoring differs from classical ML monitoring. Meridian tracks:

| Signal | What it catches |
|--------|-----------------|
| **Hallucination rate** | Sampled review of responses for factual accuracy against source docs |
| **Escalation rate** | Is the assistant appropriately routing hard cases to humans? |
| **Guardrail triggers** | How often are injection/leakage guardrails firing? Rising = probing |
| **Output toxicity / tone** | Sampled scoring for inappropriate or biased responses |
| **Customer signals** | Complaints, corrections, "that's wrong" feedback |
| **Scope drift** | Are people using it for advice/decisions it's not meant for? |
| **Transparency check** | Is the AI disclosure present and functioning? |

The evaluation metrics for GenAI are genuinely harder than accuracy for a classifier — there's no single "correct" answer. So monitoring leans on sampled human review, guardrail telemetry, and customer feedback rather than a clean accuracy number.

---

## Stage 6 — Incident Response: The Chatbot Hallucinates Harmful Content

*Artefact: [`ai-incident-response-playbook.md`](../7_monitoring-incident/ai-incident-response-playbook.md)*

Three months in, an incident. A customer asks about early loan repayment. The assistant, despite grounding, states an incorrect early-repayment fee — lower than the real figure. The customer makes a decision based on it and complains when charged the correct (higher) amount. It surfaces via a complaint.

**Detection:** Customer complaint flags a factual error → logged as an incident.

**Triage:** Is this a SEV-1 serious incident? Assessment: the error caused financial detriment to a customer, but limited in scale (one customer, contained, not a fundamental-rights or safety issue). Classified **SEV-2 Major** — significant, requires response, but not an Article 73 serious incident. (The triage-threshold judgement — deciding severity while the clock is a consideration — is exactly the hard part: better to assess fast and stand down than sit on it.)

**Containment:** Review whether other customers received the same wrong figure (the monitoring sample and logs let Meridian check). Temporarily tighten the guardrail on fee-related queries to route them all to humans.

**Investigation:** Root cause — the retrieval surfaced an outdated fee document that hadn't been updated in the source. This is a *data* problem (stale source content), not a model problem. Lineage on the document store identifies which doc and when it went stale.

**Remediation:** Update the source document; add a freshness check on fee-related content; make the fee-query guardrail permanent (always human-reviewed). Remediate the affected customer.

**Post-mortem:** The learning — RAG grounding is only as good as the freshness of what it retrieves. A new monitoring signal (source-document freshness) is added, and the risk register updated. The incident improved the system.

---

## Stage 7 — Regulatory Compliance Check and Maturity

*Artefacts: [`ai-audit-checklist.md`](../7_monitoring-incident/ai-audit-checklist.md), [`maturity-model.md`](../2_risk-and-controls/maturity-model.md)*

Running the audit checklist against the deployment confirms: transparency implemented (Art 50), GPAI provider documentation on file (Chapter V), risk assessment complete, guardrails tested, monitoring live, incident handled and documented. As a limited-risk system, the high-risk sections (conformity, Annex IV) are marked N/A with rationale.

A maturity check on Meridian's overall AI governance: the deployment scored well because Meridian's data governance was solid (the retrieval content was catalogued, if imperfectly fresh). The one gap the incident exposed — source-content freshness — was a data quality issue, reinforcing the framework's central thesis even for GenAI: the hardest problems trace back to data.

---

## What This Case Study Demonstrates

1. **The framework handles GenAI, not just classical ML.** Generative systems raise different risks — hallucination, injection, leakage — and the framework accommodates them through the risk register, guardrail controls, and GenAI-specific monitoring.

2. **Limited-risk still means real governance for GenAI.** The transparency box is the mandatory minimum, but the generative risk surface (a chatbot that can confidently say something false and harmful) demands genuine controls even when the system isn't high-risk.

3. **The GenAI incident was, at root, a data problem.** A stale source document caused the hallucination. Even in generative AI, the framework's thesis holds: fix data governance or your AI governance is brittle.

4. **Proportionality and rigour coexist.** Limited-risk classification kept the documentation burden proportionate, while the Critical GenAI risks got full mitigation. Governance scaled to where the risk actually was.

---

## Try It Yourself

To govern a GenAI deployment: start with the [`intake-form.md`](../6_templates/intake-form.md), then run a GenAI-specific risk assessment (use OWASP Top 10 for LLMs alongside the [`risk-register.md`](../6_templates/risk-register.md)), design guardrails for hallucination/injection/leakage, document with a [`system-card-template.md`](../6_templates/system-card-template.md), and stand up GenAI monitoring per the [`ai-monitoring-playbook.md`](../7_monitoring-incident/ai-monitoring-playbook.md). The generative risk surface is different; the governance discipline is the same.
