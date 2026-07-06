# AI Governance Operating Model

> **Purpose:** Defines how AI governance actually runs in an organisation — who does what, how decisions are made, how work flows between teams, and how governance connects to existing structures (data governance, risk, compliance, IT).
>
> **Audience:** Senior leadership, governance committees, data teams, ML teams, compliance officers.
>
> **When to use:** When establishing a governance function, onboarding new governance participants, or explaining the operating model to regulators or auditors.

---

## 1. Operating Model Overview

AI governance is not a standalone function. It is a coordination layer that connects existing organisational capabilities — data governance, risk management, compliance, ML engineering, product, legal — around the shared objective of responsible, compliant AI deployment.

The operating model has five components:

1. **Governance Structure** — who has authority to make decisions
2. **Roles and Responsibilities** — who does what (detailed in `raci.md`)
3. **Decision Rights** — what decisions are made and at what level
4. **Governance Cadence** — when governance activities happen (detailed in `governance-cadence.md`)
5. **Information Flows** — how information moves between teams and up to leadership

---

## 2. Governance Structure

### Three-Tier Model

```
┌─────────────────────────────────────────────────────┐
│                  TIER 1: STRATEGIC                    │
│              AI Governance Committee                  │
│    (C-suite / Board-level, quarterly + triggered)     │
│                                                       │
│  Approves: AI strategy, risk appetite, policies,      │
│  high-risk system deployments, incident escalations   │
└────────────────────────┬──────────────────────────────┘
                         │
┌────────────────────────▼──────────────────────────────┐
│                  TIER 2: TACTICAL                      │
│            AI Governance Working Group                 │
│     (Cross-functional, monthly + as needed)            │
│                                                        │
│  Manages: Risk assessments, classification decisions,  │
│  evidence pack reviews, monitoring exceptions,         │
│  regulatory updates, vendor assessments                │
└────────────────────────┬───────────────────────────────┘
                         │
┌────────────────────────▼───────────────────────────────┐
│                  TIER 3: OPERATIONAL                    │
│           AI System Owners + Project Teams              │
│           (Continuous, daily operations)                 │
│                                                         │
│  Executes: Intake forms, documentation, monitoring,     │
│  incident response, evidence production, training       │
└─────────────────────────────────────────────────────────┘
```

### Tier 1: AI Governance Committee (Strategic)

| Element | Detail |
|---------|--------|
| **Composition** | CEO/COO (chair), CTO/CDO, CISO, DPO, Head of Risk, Head of Compliance, General Counsel |
| **Frequency** | Quarterly + triggered (critical risk escalation, major incident, new regulation) |
| **Quorum** | Chair + 3 members (must include DPO or Head of Risk) |
| **Authority** | Approve/reject high-risk AI deployments. Set organisational AI risk appetite. Approve AI governance policies. Approve budget for governance programme. Escalation point for unresolved Tier 2 decisions. |
| **Inputs** | Tier 2 risk dashboard, incident reports, regulatory horizon scan, maturity assessment |
| **Outputs** | Strategic decisions (documented), policy approvals, budget allocations, escalation resolutions |

### Tier 2: AI Governance Working Group (Tactical)

| Element | Detail |
|---------|--------|
| **Composition** | AI Governance Lead (chair), Data Governance Lead, ML Engineering Lead, Product Lead, Compliance Officer, DPO representative, Security representative |
| **Frequency** | Monthly + as needed (new high-risk intake, incident triage, regulatory update) |
| **Authority** | Classify AI systems by risk tier. Approve/reject risk assessments. Review evidence packs for completeness. Approve limited-risk and minimal-risk deployments. Escalate high-risk decisions to Tier 1. Assign risk treatment owners. |
| **Inputs** | Intake forms, risk assessments, evidence packs, monitoring reports, incident reports, regulatory updates |
| **Outputs** | Classification decisions, risk treatment plans, evidence pack sign-offs, monitoring exceptions, escalation recommendations |

### Tier 3: Operational (System-Level)

| Element | Detail |
|---------|--------|
| **Composition** | AI System Owner, Data Steward(s), ML Engineer(s), Product Owner, Data Owner |
| **Frequency** | Continuous (integrated into delivery workflow) |
| **Authority** | Complete intake forms. Produce documentation and evidence. Execute monitoring. Report incidents. Implement risk treatments. Maintain records. |
| **Inputs** | Tier 2 decisions, controls requirements, evidence templates, monitoring thresholds |
| **Outputs** | Completed intake forms, risk assessments, evidence packs, monitoring data, incident reports |

---

## 3. Role Definitions

### AI Governance Lead

| Element | Detail |
|---------|--------|
| **Reports to** | CDO, CTO, or Head of Risk (depending on org structure) |
| **Accountability** | Overall effectiveness of the AI governance programme |
| **Responsibilities** | Design and maintain governance framework. Chair Tier 2 working group. Prepare Tier 1 committee materials. Manage AI system inventory. Coordinate risk assessments. Ensure evidence packs are complete. Track regulatory developments. Report on governance KPIs. |
| **Skills required** | Regulatory knowledge (AI Act, GDPR, DORA), risk management, stakeholder management, cross-functional coordination |
| **Interacts with** | Every role below, plus regulators during supervisory engagement |

### AI System Owner

| Element | Detail |
|---------|--------|
| **Reports to** | Business unit / product leadership |
| **Accountability** | Compliance of their specific AI system(s) throughout the lifecycle |
| **Responsibilities** | Submit intake forms. Own the risk assessment for their system. Ensure evidence pack is produced and maintained. Implement risk treatments assigned by Tier 2. Ensure human oversight is functioning. Report incidents. |
| **Key principle** | The AI System Owner is accountable end-to-end. They cannot delegate accountability to the data team or ML team — they coordinate across both. |

### Data Owner

| Element | Detail |
|---------|--------|
| **Reports to** | Business unit leadership (data ownership is a business function, not IT) |
| **Accountability** | Quality, integrity, and appropriate use of specific datasets |
| **Responsibilities** | Approve data access for AI use cases. Define data quality thresholds. Ensure data classification is accurate. Approve data retention and deletion policies. Authorise dataset use in training, validation, and testing. Sign off on data governance readiness in the intake form (Section 4). |
| **Key principle** | Data ownership is a decision-making authority, not a technical role. The Data Owner decides what constitutes acceptable quality and who can use the data. |
| **Interacts with** | Data Steward (execution partner), AI System Owner (use case approval), AI Governance Lead (evidence requirements) |

### Data Steward

> **Why this role matters for AI governance:** The EU AI Act Article 10 requires data governance practices for training, validation, and testing datasets — but the Act doesn't specify who implements those practices operationally. The Data Steward is that person. They are the bridge between data governance policy (set by the Data Owner) and data governance execution (performed in data pipelines and AI workflows). Without Data Stewards, Article 10 obligations exist on paper but not in practice.

| Element | Detail |
|---------|--------|
| **Reports to** | Data Governance Lead or Data Owner (dual reporting is common) |
| **Accountability** | Day-to-day data quality, lineage documentation, and standards compliance for assigned data domains |
| **Responsibilities** | |

**Data quality execution:**
- Monitor data quality metrics (completeness, accuracy, timeliness, consistency, uniqueness) for datasets used by AI systems.
- Investigate and remediate data quality issues before they reach AI model training or inference.
- Maintain data quality dashboards and report to Data Owner on quality trends.
- Define and enforce data quality SLAs between data producers and AI consumers.

**Data cataloguing and metadata:**
- Ensure datasets are registered in the data catalogue with complete metadata (source, schema, refresh frequency, sensitivity classification, ownership).
- Maintain catalogue entries as datasets evolve (schema changes, new sources, deprecation).
- Ensure AI-specific metadata is captured: intended use, training/validation/testing split, labelling methodology, known limitations.

**Data lineage:**
- Document data lineage from source to AI system input, including all transformations, joins, enrichments, and sampling steps.
- Maintain lineage documentation when pipelines change.
- Support AI governance team in producing Article 10 evidence by providing lineage information for Annex IV documentation.

**Data classification and access:**
- Apply data classification labels (public, internal, confidential, restricted, special category).
- Ensure access controls align with classification — particularly for special category data (GDPR Article 9) used in AI systems.
- Support DPO in data mapping for DPIAs involving AI systems.

**Standards compliance:**
- Ensure data handling complies with organisational data governance policies.
- Implement data retention and deletion rules for AI training datasets.
- Participate in data governance audits and provide evidence of compliance.

| Element | Detail |
|---------|--------|
| **Key principle** | The Data Steward is an execution role, not a decision role. They implement the standards and policies set by the Data Owner. They escalate to the Data Owner when decisions are required (e.g., acceptable quality threshold for a new AI use case). |
| **How they interact with AI governance** | The Data Steward is the AI governance team's primary interface for data-related evidence. When the AI Governance Lead needs to verify data governance readiness (intake form Section 4), needs lineage for Annex IV documentation, or needs quality metrics for ongoing monitoring — the Data Steward provides it. They attend Tier 2 Working Group meetings when data-related risks are on the agenda. |
| **Skills required** | Data quality tools (Great Expectations, dbt tests, Soda, Collibra DQ), SQL, metadata management, data cataloguing tools, understanding of data modelling, GDPR awareness, communication with both technical and business stakeholders |
| **DAMA DMBOK mapping** | Primarily: Data Quality Management, Metadata Management. Secondary: Data Governance, Data Security. |

### ML Engineering Lead

| Element | Detail |
|---------|--------|
| **Accountability** | Technical implementation of AI systems and compliance with Articles 12, 15 |
| **Responsibilities** | Implement logging and record-keeping (Article 12). Measure and report accuracy, robustness, cybersecurity (Article 15). Implement fairness constraints and bias testing. Provide model performance data for evidence packs. Support risk assessments with technical input. Implement monitoring and alerting. |

### DPO / Privacy Lead

| Element | Detail |
|---------|--------|
| **Accountability** | GDPR compliance for AI systems processing personal data |
| **Responsibilities** | Conduct or oversee DPIAs for AI systems. Assess Article 22 automated decision-making applicability. Review transparency documentation. Advise on special category data processing (Article 10.5 of AI Act intersects GDPR Article 9). |

### Compliance Officer

| Element | Detail |
|---------|--------|
| **Accountability** | Regulatory compliance across all applicable frameworks (not just AI Act) |
| **Responsibilities** | Maintain cross-regulatory obligation mapping. Track regulatory developments (AI Act, GDPR, DORA, DMA, sector-specific). Coordinate with regulators (DNB, AFM, BaFin). Prepare regulatory submissions and responses. Ensure AI literacy training compliance (Article 4). |

---

## 4. Decision Rights

| Decision | Who Decides | Who Advises | Who Is Informed | Escalation |
|----------|-------------|-------------|-----------------|------------|
| AI risk appetite (org-level) | Tier 1 Committee | Head of Risk, DPO | All governance participants | Board |
| AI system risk classification | Tier 2 Working Group | AI Governance Lead, Compliance Officer | AI System Owner, Data Owner | Tier 1 if disagreement |
| High-risk system deployment approval | Tier 1 Committee | Tier 2 Working Group | Business unit, ML team | Board if novel/precedent-setting |
| Limited/minimal-risk deployment | Tier 2 Working Group | AI Governance Lead | Tier 1 (dashboard) | Tier 1 if reclassified |
| Risk treatment selection | Tier 2 Working Group | Risk Owner, ML Engineering | AI System Owner | Tier 1 if residual risk is Critical |
| Data quality threshold for AI dataset | Data Owner | Data Steward, ML Engineering | AI Governance Lead | Tier 2 if dispute |
| Evidence pack sign-off | Tier 2 Working Group | AI Governance Lead, DPO | AI System Owner | Tier 1 if incomplete and timeline-critical |
| Incident classification (severity) | AI Governance Lead | Compliance Officer, ML Engineering | Tier 2 (immediately), Tier 1 (within 24h if major) | Tier 1 + regulator if serious |
| Vendor AI system procurement | Procurement + Tier 2 | AI Governance Lead, DPO, Security | Tier 1 (dashboard) | Tier 1 if high-risk vendor |
| Model retraining trigger | ML Engineering Lead + Data Steward | AI System Owner | Tier 2 (next meeting) | Tier 2 if performance below threshold |

---

## 5. Information Flows

### Upward (Operational → Strategic)

```
System Teams → Tier 2 Working Group → Tier 1 Committee → Board
              (monthly report)        (quarterly report)   (annual)
```

- **Monthly to Tier 2:** AI system inventory status, open risks, monitoring alerts, evidence pack completion rates, incidents.
- **Quarterly to Tier 1:** Risk dashboard (all systems), governance maturity assessment, regulatory horizon scan, resource requests, strategic recommendations.
- **Annually to Board:** AI governance programme effectiveness report, regulatory compliance status, risk trends, investment recommendations.

### Downward (Strategic → Operational)

- **From Tier 1:** Policy updates, risk appetite changes, deployment approvals/rejections, budget allocations.
- **From Tier 2:** Classification decisions, risk treatment assignments, evidence requirements, monitoring threshold changes, regulatory guidance.

### Lateral (Across Functions)

| From | To | Information | Frequency |
|------|----|-------------|-----------|
| ML Engineering | AI Governance Lead | Model performance metrics, monitoring alerts | Continuous |
| Data Steward | AI Governance Lead | Data quality metrics, lineage updates | Monthly + triggered |
| DPO | AI Governance Lead | DPIA findings, Article 22 assessments | Per intake |
| Compliance | AI Governance Lead | Regulatory updates, enforcement actions | As published |
| AI Governance Lead | All system teams | Updated templates, new guidance, control changes | As published |

---

## 6. Integration with Existing Structures

### Data Governance Integration

AI governance does not replace data governance. It extends data governance into the AI domain. The integration points are:

| Data Governance Function | AI Governance Dependency | Integration Mechanism |
|-------------------------|-------------------------|----------------------|
| Data ownership | AI systems need data owners for every dataset | Intake form Section 4 requires data owner identification |
| Data quality | AI systems require measured, monitored data quality | Data Steward provides quality metrics for evidence packs |
| Data cataloguing | AI systems require catalogued, discoverable datasets | Catalogue entries include AI-specific metadata |
| Data lineage | AI evidence requires source-to-model traceability | Data Steward maintains lineage for AI training pipelines |
| Data classification | AI systems require classified datasets (PII, special category) | Classification feeds risk assessment and DPIA |

See `data-governance-dependency-map.md` for the full mapping.

### Risk Management Integration

AI risk management is part of enterprise risk management, not parallel to it. AI risks should be registered in the enterprise risk register with AI-specific scoring criteria (see `risk-register.md`). The Tier 2 Working Group reports into existing risk governance structures.

### Compliance Integration

AI Act compliance sits alongside GDPR, DORA, MiFID II, PSD2, Solvency II compliance. The Compliance Officer ensures cross-regulatory obligation mapping. Evidence packs are designed to satisfy multiple regulations simultaneously.

---

## 7. Operating Model Maturity

| Level | Description | Characteristics |
|-------|-------------|-----------------|
| **Level 0: Ad Hoc** | No formal governance | AI deployed without oversight. No inventory. No risk assessment. Compliance reactive. |
| **Level 1: Initial** | Governance exists but inconsistent | Some policies written. Intake process exists but not enforced. Risk assessments done for some systems. No monitoring. |
| **Level 2: Defined** | Governance formalised | All three tiers established. Roles defined. RACI in place. Intake mandatory. Risk assessments completed for all high-risk systems. Evidence packs produced. |
| **Level 3: Managed** | Governance measured | KPIs tracked. Continuous monitoring operational. Governance cadence enforced. Maturity regularly assessed. Regulatory engagement proactive. |
| **Level 4: Optimised** | Governance embedded | Governance integrated into CI/CD pipelines. Automated evidence generation. Predictive risk analytics. Continuous improvement driven by data. |

**Target for EU AI Act compliance: Level 2 minimum. Level 3 for organisations with significant high-risk AI portfolios.**
