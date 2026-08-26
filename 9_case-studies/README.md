# Case Studies

> **Purpose:** These case studies run real AI systems through the full governance framework in this repo, end to end. Where the other folders contain the machinery — the framework, controls, templates, operating model — these show the machine running. Each case study is both a worked example and a demonstration that the framework is operational, not theoretical.

---

## Why case studies matter

A governance framework is only as good as its application. It is easy to write a policy; it is hard to prove that policy produces defensible decisions on a real system with real data and real stakeholders. These case studies close that gap. They take a system from intake to monitoring, showing exactly which artefact governs each stage and how they connect.

They also demonstrate the two things that most distinguish good governance from governance theatre:

- **Data governance as the foundation.** In the credit scoring case, the pivotal moment is remediating data governance *before* assessing risk — because a risk assessment built on un-profiled data is worthless. This is the repo's central thesis, proven in practice.
- **Proportionality.** The chatbot case applies a deliberately light touch, because it is limited-risk. Governance that treats every system as high-risk is not rigorous — it is indiscriminate, and it buries the systems that actually matter.

---

## The case studies

### 1. Credit Scoring Model (High-Risk)

[`credit-scoring-case-study.md`](credit-scoring-case-study.md)

A consumer credit scoring model at a mid-market lender — a textbook Annex III high-risk system. This case runs the full machinery: intake, data governance remediation, risk assessment (including a Critical bias finding and its mitigation), controls mapping, human oversight design, model and system cards, evidence pack, Tier 1 approval, and ongoing monitoring that catches data drift before it degrades the model. This is the framework at full stretch.

**Read this to see:** how a high-risk system is governed end to end, and why data governance is the foundation everything else rests on.

### 2. Customer-Service GenAI Chatbot (Limited-Risk)

[`genai-chatbot-case-study.md`](genai-chatbot-case-study.md)

A vendor-provided GenAI chatbot answering routine customer questions — a limited-risk system whose real obligation is Article 50 transparency, which is **live now** (unlike the high-risk obligations deferred to December 2027 by the Digital Omnibus). This case shows the framework applying a proportionate, light touch, getting the one mandatory thing (transparency) right, and shifting the governance focus to vendor assurance because the model is bought, not built.

**Read this to see:** proportionality in action, and why "limited-risk" never means "no obligations."

---

## The contrast is the point

Read together, these two cases show the same framework applied to radically different systems — full machinery for the high-risk model, a light touch for the limited-risk chatbot. That is proportionality working as intended: governance scaled to risk, rigorous where it matters and restrained where it doesn't.

---

## Run your own

Each case study ends with a short "try it yourself" guide. To govern your own AI system, start with the [`intake-form.md`](../6_templates/intake-form.md) and follow the linked artefacts through each stage. The [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md) tells you what to produce at each stage, who owns it, and how often to review it.
