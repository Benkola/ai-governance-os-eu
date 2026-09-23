# NIST AI RMF Crosswalk

> **Purpose:** Maps the NIST AI Risk Management Framework (AI RMF 1.0) to the artefacts and controls in this repo. The EU AI Act tells you *what* you must do; NIST AI RMF gives you a *structured way to organise* how you do it. Reading them together — obligation-driven (EU) and function-driven (NIST) — produces governance that is both compliant and coherent. This crosswalk lets a US or transatlantic organisation see how EU AI Act work maps onto the NIST functions they already use, and lets an EU organisation borrow NIST's structure.
>
> **How to use:** Find the NIST function/category you're working in, and this table points you to the repo artefact that operationalises it. Or work EU-first and use this to show your NIST alignment to a US-facing stakeholder.
>
> **Scope note:** NIST AI RMF is a voluntary framework, not a regulation. This crosswalk is a conceptual alignment, not a claim of certification or formal conformance.

---

## The Two Frameworks at a Glance

| | EU AI Act | NIST AI RMF 1.0 |
|--|-----------|------------------|
| **Type** | Binding regulation | Voluntary framework |
| **Structure** | Obligations by risk tier (prohibited / high / limited / minimal) | Four functions: Govern, Map, Measure, Manage |
| **Driver** | Legal compliance | Risk management outcomes |
| **Question it answers** | "What must we do?" | "How do we organise doing it well?" |
| **Geography** | EU (extraterritorial reach) | US-origin, globally used |

The two are complementary, not competing. NIST's four functions are a lifecycle of risk practice; the EU AI Act's obligations slot into them. An organisation doing EU AI Act work well is already doing most of what NIST describes — this crosswalk makes that explicit.

---

## The Four NIST Functions

| Function | What it covers | Repo artefacts that operationalise it |
|----------|----------------|----------------------------------------|
| **GOVERN** | Culture, accountability, structures, and processes for AI risk management across the organisation | Operating model, RACI, governance cadence, documentation standard |
| **MAP** | Establishing context and identifying risks — understanding the system, its purpose, and where risk lives | Intake form, risk register (identification), data governance dependency map |
| **MEASURE** | Analysing, assessing, and tracking risks using quantitative and qualitative methods | Risk register (scoring), monitoring playbook, model/system cards, maturity model |
| **MANAGE** | Prioritising and acting on risks — treatment, response, and ongoing management | Risk register (treatment), incident response playbook, vendor governance, audit checklist |

---

## Detailed Crosswalk

### GOVERN

| NIST Category | NIST Subcategory (paraphrased) | EU AI Act link | Repo artefact |
|---------------|-------------------------------|----------------|---------------|
| GOVERN 1 | Policies, processes, and procedures for AI risk are in place | Art 9 (risk management system) | `ai-governance-framework.md`, `operating-model.md` |
| GOVERN 2 | Accountability structures and roles are defined | Art 16, 22, 26 | `raci.md`, `operating-model.md` |
| GOVERN 3 | Workforce diversity, competence, and AI literacy | Art 4 (AI literacy) | `governance-cadence.md` (training tracking), `operating-model.md` |
| GOVERN 4 | Organisational culture supports critical thinking and safety | — (good practice) | `operating-model.md`, `ai-documentation-standard.md` |
| GOVERN 5 | Processes for stakeholder engagement and feedback | Art 26 (deployer duties) | `governance-cadence.md`, `operating-model.md` |
| GOVERN 6 | Policies for third-party / supply-chain AI risk | Art 25 (value chain) | `vendor-governance-framework.md`, `ai-tool-evaluation-rubric.md` |

### MAP

| NIST Category | NIST Subcategory (paraphrased) | EU AI Act link | Repo artefact |
|---------------|-------------------------------|----------------|---------------|
| MAP 1 | Context is established and understood | Art 6, 9.2 | `intake-form.md` (business context, classification) |
| MAP 2 | Categorisation of the AI system | Art 6, Annex III | `intake-form.md` (risk classification) |
| MAP 3 | AI capabilities, goals, and value are understood | Art 11 (intended purpose) | `intake-form.md`, `model-card-template.md` |
| MAP 4 | Risks and benefits mapped across the lifecycle | Art 9.2 | `risk-register.md` (identification), `data-governance-dependency-map.md` |
| MAP 5 | Impacts to individuals, groups, society characterised | Art 9.2(a), 27 (FRIA) | `risk-register.md`, `intake-form.md` |

### MEASURE

| NIST Category | NIST Subcategory (paraphrased) | EU AI Act link | Repo artefact |
|---------------|-------------------------------|----------------|---------------|
| MEASURE 1 | Appropriate methods and metrics are identified | Art 9.4, 15 | `model-card-template.md` (metrics), `risk-register.md` (scoring) |
| MEASURE 2 | Systems are evaluated for trustworthy characteristics | Art 10, 13, 14, 15 | `model-card-template.md`, `system-card-template.md`, `ai-audit-checklist.md` |
| MEASURE 2.11 | Fairness and bias are evaluated | Art 10.2(f) | `risk-register.md`, `model-card-template.md` (fairness metrics) |
| MEASURE 3 | Mechanisms for tracking risks over time | Art 72 (post-market monitoring) | `ai-monitoring-playbook.md`, `maturity-model.md` |
| MEASURE 4 | Feedback on efficacy of measurement is gathered | Art 61 (post-market), Art 9.2(c) | `ai-monitoring-playbook.md`, `governance-cadence.md` |

### MANAGE

| NIST Category | NIST Subcategory (paraphrased) | EU AI Act link | Repo artefact |
|---------------|-------------------------------|----------------|---------------|
| MANAGE 1 | Risks are prioritised and acted upon | Art 9.3 (treatment hierarchy) | `risk-register.md` (treatment) |
| MANAGE 2 | Strategies to maximise benefit and minimise harm | Art 9.3, 14 (oversight) | `risk-register.md`, `operating-model.md` |
| MANAGE 3 | Third-party risks are managed | Art 25 | `vendor-governance-framework.md`, `poc-plan-template.md` |
| MANAGE 4 | Risk treatments are documented and monitored; incidents handled | Art 73 (serious incidents) | `ai-incident-response-playbook.md`, `ai-audit-checklist.md` |

---

## How to Read This Crosswalk

**If you're NIST-first (US or transatlantic org):** You already organise AI risk around Govern/Map/Measure/Manage. This crosswalk shows which EU AI Act obligations attach to each function, so extending your NIST practice to EU compliance is a matter of adding obligations to functions you already run — not building a parallel programme.

**If you're EU-first:** You're driven by the AI Act's obligations. NIST's four functions give you a clean way to *organise* that work into a coherent risk lifecycle, and a shared vocabulary for talking to US stakeholders, investors, or auditors who think in NIST terms.

**The practical payoff:** one set of artefacts satisfies both. The risk register is simultaneously an AI Act Article 9 risk management system AND a NIST Map/Measure/Manage instrument. The monitoring playbook is both Article 72 post-market monitoring AND NIST Measure 3. You build once and speak two languages.

---

## What This Crosswalk Is Not

- It is not a claim that following this repo makes you NIST-conformant or AI-Act-compliant automatically — both require organisational implementation, not just artefacts.
- It is not an official NIST mapping — NIST publishes its own crosswalks; this is a practitioner alignment.
- It does not replace reading the primary sources. It's a bridge between them.

See `genai-profile-addendum.md` for the NIST Generative AI Profile overlay, which adds GenAI-specific risk actions on top of this base crosswalk.

