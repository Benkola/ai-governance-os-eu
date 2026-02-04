# AI Governance OS (EU)

**Repo:** `ai-governance-os-eu`  
**Goal:** A practical, EU-first AI governance operating system for SMEs — built as shipped artefacts (frameworks, templates, controls maps, scorecards, crosswalks, and case studies).

This repo is intentionally **not academic**. It is:
- **Operational** (usable by a real team next month)
- **Evidence-based** (mapped to primary sources)
- **Interview-defensible** (clear decisions, artifacts, rationale)
- **SME-scoped** (lightweight, implementable, minimum viable governance)

---

## What you can do with this repo (in plain English)

If you’re an SME adopting ML/GenAI (or buying AI vendors), you can use this repo to:
- Classify use cases by **risk and obligations** (EU AI Act)
- Stand up a **minimum viable governance operating model** (roles, forums, RACI)
- Run **intake → risk assessment → approval → monitoring → incident response**
- Produce governance **evidence packs** (model/system cards, risk register, monitoring plan)
- Choose vendors with a **tool evaluation rubric + PoC plan**
- Implement once, and speak both **EU AI Act** and **NIST AI RMF** languages

---

## Authority spine (the “source of truth”)

This repo translates major governance sources into implementable controls and artifacts:

- **EU AI Act (Regulation (EU) 2024/1689)** — primary legal text  
- **AI Act Service Desk** — implementation-oriented article summaries (non-binding)  
- **NIST AI RMF 1.0 (NIST AI 100-1)** — risk management functions/categorization  
- **NIST GenAI Profile (NIST AI 600-1)** — GenAI-specific risk controls & actions  
- **ISO/IEC 42001 (conceptual alignment)** — AI management system structure (no certification claims)

---

## Repo map (start here)

### 0) Start here
- `0_start-here/scope.md` — SME assumptions, what’s included/excluded, risk boundaries  
- `0_start-here/how-to-use-this-repo.md` — how to adopt this as an operating system  
- `0_start-here/glossary.md` — consistent terms (provider/deployer, model/system, etc.)

### 1) Framework + operating model
- `1_framework/ai-governance-framework.md` — governance principles + lifecycle + evidence
- `1_framework/operating-model.md` — forums, decision rights, cadence, escalation paths  
- `1_framework/raci.md` — accountability by lifecycle stage

### 2) Maturity model
- `2_maturity-model/maturity-model.md` — 5-level maturity model with observable evidence

### 3) Scorecards
- `3_scorecards/readiness-scorecard.md` — go/no-go readiness scoring with evidence demands  
- `3_scorecards/supplier-due-diligence-checklist.md` — vendor governance requirements

### 4) EU AI Act implementation layer
- `4_eu-ai-act/eu-ai-act-controls-map.md` — EU AI Act → implementable controls  
- `4_eu-ai-act/high-risk-requirements-checklist.md` — high-risk obligations + evidence pack

### 5) Crosswalks (global credibility)
- `5_nist-crosswalk/nist-ai-rmf-crosswalk.md` — EU AI Act ↔ NIST AI RMF mapping  
- `5_nist-crosswalk/genai-profile-addendum.md` — GenAI overlay actions

### 6) Templates (the evidence pack)
- `6_templates/intake-form.md`
- `6_templates/risk-register.md`
- `6_templates/model-card.md`
- `6_templates/system-card.md`
- `6_templates/data-sheet.md`
- `6_templates/dpia-lite.md`

### 7) Monitoring + incident response
- `7_monitoring-incident/monitoring-plan.md`
- `7_monitoring-incident/evals-playbook.md`
- `7_monitoring-incident/incident-response-playbook.md`
- `7_monitoring-incident/post-market-monitoring.md`

### 8) Tooling + PoC
- `8_tooling/tool-eval-rubric.md`
- `8_tooling/poc-plan.md`

### 9) Case studies (end-to-end proof)
- `9_case-studies/case-study-01-genai-customer-support.md`
- `9_case-studies/case-study-02-hr-people-analytics.md`

### 11) Hiring kit (optional)
- `11_hiring-kit/cv-bullets.md`
- `11_hiring-kit/linkedin-headline-about.md`
- `11_hiring-kit/ats-keywords.md`
- `11_hiring-kit/interview-stories.md`

---

## How to use this repo (3 routes)

### Route A — “I have a use case to approve”
1. Fill `6_templates/intake-form.md`  
2. Add risks to `6_templates/risk-register.md`  
3. Determine risk tier and obligations using `4_eu-ai-act/*`  
4. Require evidence pack (model/system card)  
5. Define monitoring + incident response (`7_monitoring-incident/*`)

### Route B — “I’m building governance from scratch”
1. Adopt the framework (`1_framework/ai-governance-framework.md`)  
2. Stand up the operating model + RACI (`1_framework/*`)  
3. Baseline maturity and readiness (`2_maturity-model/*`, `3_scorecards/*`)

### Route C — “I’m evaluating vendors”
1. Run `8_tooling/tool-eval-rubric.md`  
2. Execute `8_tooling/poc-plan.md`  
3. Require supplier evidence (`3_scorecards/supplier-due-diligence-checklist.md`)

---

## Design principles (SME reality)
- Governance must be **lightweight** and **documented**
- Controls must produce **evidence**, not bureaucracy
- Risk decisions must have **owners**, **thresholds**, and **review cadence**
- Vendor AI is still **your responsibility** (due diligence + monitoring)

---

## Status
This is a living repo. Each artefact is versioned and improved weekly.

---

## License
MIT

---

## Contact/collaboration
Open an issue or connect via LinkedIn (link in repo description/profile).
