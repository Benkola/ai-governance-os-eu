# NIST Generative AI Profile — Addendum

> **Purpose:** The NIST AI RMF Generative AI Profile (NIST-AI-600-1) identifies risks unique to or amplified by generative AI, and suggests actions across the four NIST functions to manage them. This addendum overlays those GenAI-specific risks onto the base crosswalk (`nist-ai-rmf-crosswalk.md`), showing how this repo's artefacts address them — and pointing to the GenAI case study where they're worked through in practice.
>
> **When to use:** Alongside the base NIST crosswalk whenever the AI system in question is generative (LLMs, image/audio/video generation, RAG systems). Classical ML uses the base crosswalk; GenAI uses both.
>
> **Read with:** `nist-ai-rmf-crosswalk.md` (the base) and `9_case-studies/genai-governance-case-study.md` (these risks worked through end to end).

---

## Why GenAI Needs Its Own Profile

Generative AI introduces risks that classical predictive ML does not, and amplifies some that it shares. A credit model can be biased or inaccurate; it cannot fabricate a plausible-sounding falsehood, leak its training data through a clever prompt, or generate harmful content on demand. The NIST GenAI Profile names these distinctly so they don't fall through the gaps of a framework built for predictive systems.

The key shift: with predictive AI, the risk is in the *decision*. With generative AI, the risk is in the *output itself* — what the model says, produces, or reveals.

---

## The GenAI Risk Categories (NIST-AI-600-1) and How This Repo Addresses Them

| NIST GenAI risk | What it is | Repo treatment | Case study reference |
|-----------------|-----------|----------------|----------------------|
| **Confabulation (hallucination)** | The model produces confident, plausible, false content | Risk register (GenAI risk entry), retrieval grounding controls, "route to human when uncertain" design | GA-01 in the GenAI case study — a hallucinated fee traced to stale source data |
| **Dangerous / violent / hateful content** | The model generates harmful outputs | Output monitoring, tone/toxicity sampling, guardrails, escalation for sensitive topics | Monitoring section of the GenAI case study |
| **Data privacy / leakage** | The model reveals training data, PII, or confidential info | Scoped retrieval (no cross-context), no PII in prompts, output scanning, system-prompt protection | GA-03 in the GenAI case study |
| **Information integrity** | The model contributes to misinformation at scale | Transparency (Art 50 disclosure), grounding, human oversight for public-facing content | Controls section of the GenAI case study |
| **Information security** | New attack surfaces — prompt injection, jailbreaks | Input filtering, instruction hierarchy, output validation, red-team testing | GA-02 in the GenAI case study |
| **Intellectual property** | The model reproduces copyrighted content | Reliance on GPAI provider's copyright policy (AI Act Chapter V), output constraints | GA-05 in the GenAI case study |
| **Harmful bias / homogenisation** | Training biases surface or outputs converge harmfully | Bias/tone monitoring, testing across scenarios | GA-04 in the GenAI case study |
| **Value chain / component integration** | Risk from the foundation-model provider and integration | Vendor governance framework, GPAI documentation reliance, provider/deployer split | Stage 1 + vendor governance link in the GenAI case study |

---

## GenAI Actions Across the Four NIST Functions

The GenAI Profile suggests actions within each NIST function. Here's how this repo operationalises them:

### GOVERN (GenAI overlay)
- Establish policies specific to generative AI use (acceptable use, prohibited uses) → `operating-model.md`, `ai-documentation-standard.md`
- Govern the foundation-model provider as a critical dependency → `vendor-governance-framework.md`
- Confirm GPAI provider obligations (Chapter V documentation) are met and filed → `intake-form.md`, GenAI case study Stage 1

### MAP (GenAI overlay)
- Identify GenAI-specific risks using a GenAI taxonomy (OWASP Top 10 for LLMs alongside this profile) → `risk-register.md`, GenAI case study Stage 2
- Map the generative risk surface: what the model could say, leak, or generate → GenAI case study risk table

### MEASURE (GenAI overlay)
- Use GenAI-appropriate evaluation — hallucination rate, toxicity, guardrail triggers — not just accuracy → `ai-monitoring-playbook.md`, GenAI case study Stage 5
- Recognise that GenAI evaluation leans on sampled human review (no single "correct" answer) → GenAI case study monitoring section

### MANAGE (GenAI overlay)
- Design guardrails as active controls (grounding, filtering, scoping), not just documentation → GenAI case study Stage 3
- Handle GenAI incidents (harmful/false output) with the incident playbook, recognising the root cause is often data (stale content) → `ai-incident-response-playbook.md`, GenAI case study Stage 6

---

## The GenAI Governance Principle

Generative AI does not need a separate governance framework — it needs the same framework with a GenAI-aware risk layer. The lifecycle is identical (intake → classify → assess → control → document → monitor → respond); what changes is the risk surface at each stage. This addendum, the base crosswalk, and the GenAI case study together show that the framework flexes to cover generative systems without being rebuilt.

And the recurring lesson holds even here: in the worked GenAI case study, the most serious incident — a hallucination that harmed a customer — traced back to a stale source document. A data governance failure. Even in the most advanced generative systems, the foundation is still data.

