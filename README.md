# AI Governance OS (EU)

**Repo:** `ai-governance-os-eu`  
**Focus:** EU-first AI governance for SMEs (ML + GenAI + vendor AI), translated into implementable controls, templates, and evidence packs.

This is a public, operational portfolio repo — not an academic syllabus. It exists to show:
- **EU AI Act → controls → evidence** translation
- **Decision rights + operating model** (how governance actually runs)
- **Minimum viable documentation** (model/system cards, risk register, monitoring, incident response)
- **Two end-to-end case studies** (GenAI + HR/People Analytics)

---

## What you can do with this repo

If you’re an SME adopting AI (or buying AI-enabled tools), this repo helps you:
- Run **intake → classification → risk assessment → approval → monitoring → incident response → retirement**
- Produce an evidence pack before deployment (traceability, accountability, monitoring readiness)
- Implement EU-first controls with minimal overhead
- Evaluate vendors with governance-grade due diligence

---

## Authority spine (source of truth)

This repo is built from primary governance sources and implementation-grade frameworks:
- **EU AI Act (Regulation (EU) 2024/1689)** — obligations + risk tiering (primary text)
- **AI Act Service Desk** — implementation-style summaries (non-binding)
- **NIST AI RMF 1.0** — Govern/Map/Measure/Manage structure
- **NIST GenAI Profile** — GenAI-specific risk actions
- **ISO/IEC 42001** — conceptual management system alignment (no certification claims)

---

## Data governance foundation
AI governance does not operate in isolation. Every AI system depends on underlying data governance capabilities. This repo addresses both:

- **Data stewardship** — ownership structures, accountability, and steward onboarding
- **Data quality** — accuracy, completeness, consistency, timeliness, validity, and uniqueness
- **Metadata management** — cataloguing, classification, and discoverability of data assets
- **Data lineage** — tracing data from source to model to decision
- **Data classification** — sensitivity labelling and access control alignment
- **Regulatory data obligations** — GDPR data processing requirements, DMA data access obligations, SOx data integrity controls

The governance framework in this repo treats data governance as a prerequisite layer: if your data governance is immature, your AI governance will be brittle. The maturity model, readiness scorecards, and intake forms all include data governance readiness checks.

Conceptual backbone: DAMA DMBOK2 (Data Management Body of Knowledge).

---

## Start here (recommended reading order)

1) `0_start-here/scope.md` — boundaries, SME assumptions  
2) `1_framework/ai-governance-framework.md` — the system (lifecycle + evidence)  
3) `4_eu-ai-act/eu-ai-act-controls-map.md` — controls mapping (Week 2)  

---

## Repo map

### `0_start-here/`
- `scope.md` — what’s in/out, SME assumptions, definitions  
- `how-to-use-this-repo.md` — three adoption routes  
- `glossary.md` — consistent terminology

### `1_framework/`
- `ai-governance-framework.md` — lifecycle + evidence pack + decision rights  
- `operating-model.md` — governance forums + cadence (Week 4)  
- `raci.md` — accountability by stage (Week 4)

### `12_platform-blueprint/`
- `product-brief.md` — Evidence Pack Generator wedge (public concept, not implementation)  
- `mvp-workflows.md` — workflow specs (inputs/steps/outputs)  
- `moat-boundary.md` — what stays public vs private (defensibility)

(Additional folders are added week-by-week as artefacts ship.)

---

## Platform roadmap (separate from this repo)

This repo contains governance artefacts and reference implementations.  

A separate commercial platform (automation, exports, integrations, benchmarking) is being developed privately.  

This public repo intentionally excludes proprietary scoring weights, benchmark data, and production automation logic.

---

## How to use this repo (3 routes)

### Route A — Approve a use case
1) Fill the intake form  
2) Identify obligations + controls  
3) Require evidence pack  
4) Define monitoring + incident response  
5) Approve, log, and review

### Route B — Build governance from scratch
1) Adopt the framework + operating model  
2) Establish decision rights + cadence  
3) Baseline maturity and readiness  
4) Improve via evidence and reviews

### Route C — Evaluate a vendor
1) Run vendor due diligence  
2) Run a PoC with success + risk gates  
3) Require evidence and monitoring commitments

---

## Want help implementing this?
If you want to implement this in your SME (EU-first, evidence-based), I can support with rollout planning, workshops, and tailoring the artefacts to your org.

---

## License
MIT
