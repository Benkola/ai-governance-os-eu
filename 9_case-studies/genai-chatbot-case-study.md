# Case Study: Governing a Customer-Service GenAI Chatbot (Limited-Risk)

> **Purpose:** A deliberate contrast to the credit scoring case study. That system was high-risk and required the full governance machinery. This one is *limited-risk*, and the point of this case study is proportionality: governance should scale to risk, not apply maximum rigour to everything. It also focuses on Article 50 transparency — the obligation that is **live now** (from 2 August 2026), unlike the high-risk obligations that were deferred to December 2027.
>
> **Why this matters:** A common governance failure is treating every AI system as if it were high-risk. That buries teams in documentation, breeds resentment, and ironically weakens governance of the systems that actually matter. This case study shows the framework applying a light touch correctly — and getting the one thing that *is* mandatory (transparency) right.
>
> **The scenario:** "NorthBank" (same fictional lender) deploys a GenAI chatbot on its website to answer customer questions about products, branches, and account basics. It does not make decisions about customers; it provides information and routes complex queries to human agents.

---

## The System

| Attribute | Detail |
|-----------|--------|
| **System name** | NorthBank Customer Assistant (GenAI chatbot) |
| **Business purpose** | Answer routine customer questions; route complex queries to agents |
| **Users** | Website visitors and customers (natural persons) |
| **AI type** | Vendor-provided large language model (via API), with retrieval over NorthBank's public FAQ content |
| **What it does NOT do** | Make lending, pricing, or eligibility decisions; process transactions; give regulated financial advice |

---

## Stage 1 — Intake and Classification

*Artefact used: [`intake-form.md`](../6_templates/intake-form.md)*

**Prohibited practices (Article 5):** None.

**High-risk classification (Annex III):** The chatbot does not fall under any Annex III category. It does not assess creditworthiness, make employment decisions, or perform any high-risk function. It provides information. Classification: **Limited-Risk**.

**Transparency obligations (Article 50):** This is the operative gate. Because the system interacts directly with natural persons, Article 50(1) applies: users must be told they are dealing with an AI system, not a human. This obligation is **in force now** — it was not deferred by the Omnibus.

**Data governance readiness:** Lightweight. The chatbot retrieves over public FAQ content, so the data governance burden is minimal — but the team still confirms the content source is catalogued and the vendor's data handling is understood.

**Intake outcome:** Limited-risk. The full high-risk machinery (Annex IV documentation, conformity assessment, Tier 1 approval) does **not** apply. The [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md) proportionality matrix confirms this: limited-risk systems need intake, classification, a lightweight risk record, transparency implementation, and monitoring — not the full evidence pack.

---

## Stage 2 — The One Thing That Is Mandatory: Transparency

*Artefact used: [`eu-ai-act-controls-map.md`](../4_eu-ai-act/eu-ai-act-controls-map.md) — Article 50*

Article 50 is where a limited-risk system's real obligations live. NorthBank implements:

**Disclosure (Article 50(1)):** The chatbot opens every conversation with clear text: "You're chatting with NorthBank's AI assistant. For complex queries, I can connect you to a person." No attempt to make the bot seem human. The disclosure is unavoidable, not buried in a privacy policy.

**Handoff clarity:** When the bot routes to a human agent, the transition is explicit — the customer is told they are now speaking with a person.

**Content boundaries:** Because the bot uses generative AI, NorthBank ensures it does not present AI-generated text as authoritative financial advice. Responses on regulated topics are constrained and routed to humans.

**Note on synthetic content marking (Article 50(2)):** This chatbot produces conversational text in a clearly-disclosed AI context, so the machine-readable marking obligation for synthetic content is handled through the disclosure. For systems that generate images, audio, or video, the Article 50(2) machine-readable marking requirement is more involved — and note that legacy generative systems on the market before 2 August 2026 had until **2 December 2026** to implement it under the Omnibus.

---

## Stage 3 — Vendor Assessment (Because the Model Is Bought, Not Built)

*Artefact used: [`supplier-due-diligence-checklist.md`](../3_scorecards/supplier-due-diligence-checklist.md)*

The chatbot runs on a vendor LLM, so the governance focus shifts to vendor assurance:
- Does the vendor provide adequate documentation of the model's capabilities and limitations?
- What are the data processing terms — is customer conversation data used for vendor model training? (NorthBank confirms it is not.)
- Is the vendor's data handling GDPR-compliant?
- What happens if the vendor changes the model behind the API?

The vendor relationship is the main risk surface for a limited-risk, bought-in system — quite different from the credit scoring model, where the risk was in NorthBank's own data and model.

---

## Stage 4 — Lightweight Monitoring

*Artefact used: [`governance-cadence.md`](../1_framework/governance-cadence.md)*

Proportionate monitoring:
- **Transparency check:** periodic confirmation that the AI disclosure is present and functioning.
- **Content quality:** sampling of chatbot responses for accuracy and appropriateness.
- **Escalation quality:** confirming complex queries actually route to humans.
- **Annual review:** re-confirm the risk classification hasn't changed (e.g., if someone proposes letting the bot give account-specific advice, that would re-open the classification).

No monthly bias audits, no Tier 1 committee, no Annex IV pack. The cadence is light because the risk is low.

---

## What This Case Study Demonstrates

1. **Proportionality is a feature, not a loophole.** The framework applied a genuinely light touch here — and that is correct. Loading this chatbot with high-risk documentation would waste effort and teach the organisation that governance is bureaucratic noise. Right-sizing governance is itself a governance skill.

2. **"Limited-risk" is not "no obligations."** The transparency duty is real, mandatory, and live now. A team that dismissed this chatbot as "low-risk, ignore it" would miss the one obligation that actually applies — and it applies today, not in December 2027.

3. **The live gate is transparency.** While the industry conversation is dominated by the high-risk deferral, the obligations that bind *right now* are transparency, AI literacy, and the prohibitions. A governance function that only prepares for high-risk misses what is already enforceable.

4. **Bought AI shifts the risk surface.** For a vendor-provided system, governance is largely vendor assurance. The [`supplier-due-diligence-checklist.md`](../3_scorecards/supplier-due-diligence-checklist.md) does more work here than the risk register does.

---

## The Two Case Studies Side by Side

| Dimension | Credit Scoring (high-risk) | Chatbot (limited-risk) |
|-----------|---------------------------|------------------------|
| Risk tier | High-risk (Annex III) | Limited-risk |
| Key deadline | 2 December 2027 (deferred) | Article 50 — **live now** |
| Governance weight | Full machinery | Light touch |
| Main risk surface | Own data and model (bias, drift) | Vendor and transparency |
| Approval level | Tier 1 Committee | Tier 2 Working Group |
| Documentation | Full evidence pack + Annex IV | Intake + transparency record |
| Primary artefact | Risk register, model card | Transparency implementation, vendor checklist |

Same framework. Radically different application. That is proportionality working as intended.
