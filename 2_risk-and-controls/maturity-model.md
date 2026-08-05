# AI Governance Maturity Model

> **Purpose:** A structured way to assess how mature an organisation's AI governance is today, and to plan the path to where it needs to be. Maturity models turn "are we doing governance well?" into a measurable, defensible answer.
>
> **How to use:** Score each domain against the level descriptors. The lowest-scoring domains are your priorities. Re-assess quarterly to track progress.
>
> **Scoring:** Each domain is scored 0–4. Overall maturity is the *lowest* domain score, not the average — because governance is only as strong as its weakest link. A programme with brilliant risk assessment but no data governance is not "mostly mature." It's immature, because the data gap undermines everything.

---

## The Five Maturity Levels

| Level | Name | Defining Characteristic |
|-------|------|------------------------|
| **0** | **Ad Hoc** | Nothing systematic. Governance happens by accident or not at all. |
| **1** | **Initial** | Some activity exists but it's inconsistent, undocumented, and person-dependent. |
| **2** | **Defined** | Governance is documented, repeatable, and consistently applied. **This is the minimum for EU AI Act compliance.** |
| **3** | **Managed** | Governance is measured. KPIs tracked, monitoring continuous, decisions data-driven. |
| **4** | **Optimised** | Governance is embedded and self-improving. Automated, predictive, integrated into delivery pipelines. |

---

## Domains Overview

The maturity model covers two pillars and ten domains:

**Pillar A — AI Governance**
1. Governance Structure and Accountability
2. Risk Management
3. Regulatory Compliance
4. Documentation and Evidence
5. Monitoring and Operations
6. Human Oversight and AI Literacy

**Pillar B — Data Governance** (foundational to Pillar A)
7. Data Ownership and Accountability
8. Metadata Management
9. Data Quality Measurement
10. Data Cataloguing Adoption

> **Why data governance is in the maturity model:** You cannot achieve AI governance maturity above the level of your data governance maturity. The dependency map demonstrates that 10 of 14 AI Act governance activities require data quality measurement and 9 require data lineage. If your data governance is at Level 1, your AI governance is capped at Level 1 regardless of how sophisticated your risk frameworks are. The data governance domains are therefore not optional add-ons — they are gating domains.

---

## Pillar A: AI Governance Domains

### Domain 1: Governance Structure and Accountability

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No defined governance roles. No accountability for AI outcomes. AI deployed by whoever builds it. |
| **1 — Initial** | Some roles informally recognised. No formal committee. Accountability unclear when issues arise. |
| **2 — Defined** | Three-tier structure established (strategic, tactical, operational). RACI documented. AI System Owners assigned. Tier 2 meets regularly. |
| **3 — Managed** | Governance bodies meet on cadence with documented decisions. Accountability tracked via KPIs. Escalation triggers operational. |
| **4 — Optimised** | Governance embedded in delivery. Decisions data-driven. Continuous improvement of the operating model itself. |

### Domain 2: Risk Management

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No AI risk assessment. Risks discovered only when they materialise. |
| **1 — Initial** | Ad hoc risk identification for some systems. No scoring methodology. No register. |
| **2 — Defined** | Risk register maintained. Scoring matrix applied consistently. Risk treatment follows Article 9.3 hierarchy. All high-risk systems assessed. |
| **3 — Managed** | Risks reviewed on cadence. Risk scores trended. Treatment effectiveness measured. Risk register integrated with monitoring. |
| **4 — Optimised** | Predictive risk analytics. Emerging risks identified before materialisation. Risk appetite quantified and monitored continuously. |

### Domain 3: Regulatory Compliance

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No awareness of applicable regulations. Compliance reactive. |
| **1 — Initial** | AI Act awareness exists. Compliance handled per-system, inconsistently. No cross-regulatory mapping. |
| **2 — Defined** | Applicable regulations mapped per system (AI Act + GDPR + DORA + sector). Compliance Officer maintains obligation register. Deadlines tracked. |
| **3 — Managed** | Cross-regulatory evidence packs produced. Regulatory horizon scanning operational. Proactive engagement with supervisors (DNB/AFM). |
| **4 — Optimised** | Compliance automated where possible. Regulatory change automatically assessed for impact. Evidence generated continuously. |

### Domain 4: Documentation and Evidence

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No documentation. Cannot demonstrate compliance. |
| **1 — Initial** | Some documentation exists but incomplete and inconsistent. No standard templates. |
| **2 — Defined** | Annex IV documentation produced for high-risk systems. Evidence packs follow standard templates. Sign-off process in place. |
| **3 — Managed** | Evidence pack completeness tracked. Audit trail immutable. Regulator-ready exports available on demand. |
| **4 — Optimised** | Evidence generated automatically from system metadata. Documentation always current. One-click regulatory submission. |

### Domain 5: Monitoring and Operations

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No monitoring after deployment. Systems run unsupervised. |
| **1 — Initial** | Some performance monitoring exists, mostly reactive. No defined thresholds. |
| **2 — Defined** | Accuracy, robustness, and data quality monitored against defined thresholds. Alerts configured. Quarterly reviews held. |
| **3 — Managed** | Continuous monitoring with automated alerting. Drift detection operational. Monitoring integrated with risk register. |
| **4 — Optimised** | Predictive monitoring. Automated remediation for known issues. Self-healing pipelines with governance guardrails. |

### Domain 6: Human Oversight and AI Literacy

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No human oversight design. No AI literacy training. |
| **1 — Initial** | Human-in-the-loop exists for some systems but effectiveness not measured. Ad hoc training. |
| **2 — Defined** | Human oversight designed per Article 14. Oversight personnel trained. AI literacy training delivered (Article 4). Completion tracked. |
| **3 — Managed** | Oversight effectiveness measured (reviewer behaviour metrics). Training refreshed on cadence. Competency assessed. |
| **4 — Optimised** | Oversight continuously optimised based on outcome data. Adaptive training. Oversight quality is a tracked KPI. |

---

## Pillar B: Data Governance Domains

> These domains are foundational. AI governance maturity cannot exceed data governance maturity. Assess these honestly — they are usually where the real gaps are.

### Domain 7: Data Ownership and Accountability

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No data owners. Nobody accountable for data quality or appropriate use. Data is "IT's problem." |
| **1 — Initial** | Some data owners informally recognised for critical datasets. Ownership not documented. Accountability unclear. |
| **2 — Defined** | Data owners formally assigned for all AI-related datasets. Ownership documented. Data owners accountable for quality thresholds and use approval. Data Stewards assigned for execution. |
| **3 — Managed** | Data ownership responsibilities measured and reported. Owners actively manage their domains. Stewardship integrated into AI governance workflows (intake sign-off, evidence support). |
| **4 — Optimised** | Data ownership drives continuous improvement. Owners proactively identify and close governance gaps. Ownership accountability embedded in performance objectives. |

### Domain 8: Metadata Management

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No metadata captured. Nobody knows what data exists, where it came from, or how it's transformed. |
| **1 — Initial** | Some metadata documented manually for select datasets. No lineage. Inconsistent and quickly outdated. |
| **2 — Defined** | Metadata captured for AI datasets (source, schema, refresh, sensitivity, ownership). Data lineage documented for AI training pipelines. Sufficient to support Annex IV documentation. |
| **3 — Managed** | Metadata maintained as datasets evolve. Lineage captured end-to-end. Lineage used for impact analysis and incident root-cause investigation. |
| **4 — Optimised** | Automated metadata capture and lineage. Active metadata drives governance actions (automated impact alerts on lineage changes). Business glossary integrated. |

### Domain 9: Data Quality Measurement

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | Data quality not measured. Problems discovered only when they cause visible failures. |
| **1 — Initial** | Quality checked manually before major releases. No defined dimensions or thresholds. Reactive. |
| **2 — Defined** | Quality dimensions defined (completeness, accuracy, timeliness, consistency, uniqueness). Thresholds set for AI datasets. Quality measured before data reaches model training. |
| **3 — Managed** | Continuous automated quality monitoring. Quality metrics tied to model performance. Breaches trigger alerts and remediation. Quality SLAs between data producers and AI consumers. |
| **4 — Optimised** | Quality measured continuously with automated remediation. Quality trends predict model degradation. Data quality is a tracked governance KPI feeding the risk register. |

### Domain 10: Data Cataloguing Adoption

| Level | Descriptor |
|-------|-----------|
| **0 — Ad Hoc** | No data catalogue. Data discovery is tribal knowledge. Finding data means asking around. |
| **1 — Initial** | Spreadsheet-based or partial catalogue. Incomplete coverage. Not maintained. Low adoption. |
| **2 — Defined** | Catalogue tool deployed (e.g., Collibra, Alation, Purview, Atlan). AI datasets registered with metadata standards. Catalogue accessible to governance team for audit. |
| **3 — Managed** | Catalogue actively used across teams. AI-specific metadata captured (intended use, training splits, labelling methodology, known limitations). Adoption measured. |
| **4 — Optimised** | Automated catalogue discovery and population. Catalogue integrated into AI workflows and CI/CD. High adoption across the enterprise. Catalogue is the single source of truth. |

---

## Scoring Worksheet

| # | Domain | Pillar | Current Level (0–4) | Target Level | Gap | Priority |
|---|--------|--------|--------------------|--------------| ----|----------|
| 1 | Governance Structure and Accountability | AI | | | | |
| 2 | Risk Management | AI | | | | |
| 3 | Regulatory Compliance | AI | | | | |
| 4 | Documentation and Evidence | AI | | | | |
| 5 | Monitoring and Operations | AI | | | | |
| 6 | Human Oversight and AI Literacy | AI | | | | |
| 7 | Data Ownership and Accountability | Data | | | | |
| 8 | Metadata Management | Data | | | | |
| 9 | Data Quality Measurement | Data | | | | |
| 10 | Data Cataloguing Adoption | Data | | | | |

**Overall maturity score (lowest domain): _____**

**Three priority domains (largest gaps): _______________**

---

## Interpreting Your Score

| Overall Score | What It Means | What To Do |
|--------------|---------------|------------|
| **0–1** | Not ready for EU AI Act compliance. Significant exposure. | Focus first on the gating data governance domains (7–10) and governance structure (1). You cannot do credible risk assessment without data foundations. |
| **2** | Minimum viable compliance. Defensible but not efficient. | Sustainable for a small AI portfolio. To scale, move documentation, monitoring, and data quality to Level 3. |
| **3** | Strong, managed governance. Audit-ready. | Maintain cadence. Selectively optimise high-volume processes. This is the realistic target for most regulated organisations. |
| **4** | Best-in-class. Governance as competitive advantage. | Rare and expensive to maintain. Justified only for organisations with large, high-risk AI portfolios. |

---

## The Gating Principle Illustrated

Consider two organisations:

**Organisation A:** Brilliant AI governance (Domains 1–6 all at Level 3), but data governance at Level 1 (Domains 7–10). They have a beautiful risk framework, detailed RACI, sophisticated monitoring dashboards. But their training data isn't catalogued, quality isn't measured, and lineage isn't documented.

**Organisation B:** Modest AI governance (Domains 1–6 at Level 2), with solid data governance (Domains 7–10 at Level 2).

**Organisation B is more mature.** Why? Because Organisation A's monitoring dashboards are measuring model outputs without understanding the data feeding them. Their risk assessments are built on data nobody has profiled. When a regulator asks "show me the lineage for this model's training data," Organisation A cannot answer — and all the governance sophistication collapses. Their overall maturity score is 1 (the data governance floor), not 3.

This is why the overall score is the lowest domain, not the average. Governance maturity is gated by its weakest foundation, and the foundation is data.

---

## Re-Assessment Cadence

| Activity | Frequency |
|----------|-----------|
| Full maturity assessment | Quarterly |
| Domain spot-checks (priority domains) | Monthly |
| Target level review | Annually |
| Benchmark against peers (if data available) | Annually |

Report maturity scores to the Tier 1 Committee quarterly. Track the trend. The goal is steady upward movement in the priority domains, not perfection everywhere.
