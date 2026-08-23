# AI Documentation Standard

> **Purpose:** A policy document specifying what documentation is required at each stage of the AI lifecycle, who is responsible for producing it, who reviews it, and how often it is reviewed. This is the standard that makes documentation consistent, auditable, and complete across every AI system in the organisation.
>
> **Why this exists:** Documentation is not paperwork — it is the mechanism by which AI systems become accountable. The EU AI Act's entire enforcement model rests on documentation: you demonstrate compliance by producing evidence, and evidence is documentation. An organisation without a documentation standard produces inconsistent, incomplete records that fail under regulatory scrutiny. This standard turns documentation from an afterthought into a governed process.
>
> **Scope:** Applies to all AI systems (internally developed, vendor-provided, or hybrid) classified as high-risk or limited-risk under the EU AI Act. Minimal-risk systems follow a lightweight subset (see Section 5).
>
> **Owner:** AI Governance Lead owns this standard. Reviewed annually.

---

## 1. Documentation Principles

The organisation's AI documentation follows five principles:

1. **Documentation is evidence.** Every document produced under this standard is potential regulatory evidence. It must be accurate, dated, attributed, and version-controlled.

2. **Documentation is produced during work, not after.** Documentation created retrospectively is unreliable and often inaccurate. Documentation is a deliverable of each lifecycle stage, not a separate exercise at the end.

3. **Documentation has a single accountable owner.** Every document has one person accountable for its accuracy and currency, even if multiple people contribute.

4. **Documentation is proportionate to risk.** High-risk systems require comprehensive documentation. Minimal-risk systems require a lightweight record. The standard scales with the risk tier.

5. **Documentation is living.** Documents are reviewed and updated on a defined cadence and whenever the system materially changes. Stale documentation is a compliance risk, not an asset.

---

## 2. Required Documentation by Lifecycle Stage

The AI lifecycle has seven stages. Each stage produces specific documentation.

### Stage 1: Intake and Classification

| Document | Purpose | Responsible (produces) | Accountable (owns) | Reviewer |
|----------|---------|------------------------|--------------------|----------|
| **Intake form** | Capture use case, initial risk classification, data governance readiness | AI System Owner | AI System Owner | AI Governance Lead + Tier 2 |
| **Risk classification record** | Document the assigned risk tier and rationale | AI Governance Lead | Tier 2 Working Group | Tier 2 |
| **Regulatory applicability record** | Map applicable regulations (AI Act + GDPR + DORA + sector) | Compliance Officer | Compliance Officer | AI Governance Lead |

### Stage 2: Risk Assessment

| Document | Purpose | Responsible | Accountable | Reviewer |
|----------|---------|-------------|-------------|----------|
| **Risk register entries** | Identify, score, and plan treatment for risks | AI Governance Lead | AI System Owner | Tier 2 |
| **DPIA** (if personal data) | Assess data protection impact | DPO | DPO | AI Governance Lead |
| **FRIA** (if required) | Assess fundamental rights impact | AI Governance Lead | AI System Owner | Tier 2 |
| **Data profiling report** | Document training/validation/test data characteristics | Data Steward | Data Owner | ML Engineering Lead |

### Stage 3: Development and Documentation

| Document | Purpose | Responsible | Accountable | Reviewer |
|----------|---------|-------------|-------------|----------|
| **Model card** (per model) | Document each model's details, performance, limitations | ML Engineering Lead | AI System Owner | AI Governance Lead |
| **System card** (per system) | Document compound system architecture, flows, oversight | AI System Owner | AI System Owner | AI Governance Lead |
| **Annex IV technical documentation** | Full technical documentation for high-risk systems | ML Engineering Lead | AI System Owner | AI Governance Lead |
| **Data governance records** | Document data quality, lineage, labelling (Article 10) | Data Steward | Data Owner | AI Governance Lead |

### Stage 4: Deployment Approval

| Document | Purpose | Responsible | Accountable | Reviewer |
|----------|---------|-------------|-------------|----------|
| **Evidence pack** | Compile all evidence for the deployment decision | AI Governance Lead | AI System Owner | Tier 2 (limited) / Tier 1 (high-risk) |
| **Conformity self-assessment** | Declare conformity with AI Act requirements | AI Governance Lead | AI System Owner | Tier 2 |
| **Deployment decision record** | Document the approval decision and rationale | AI Governance Lead | Tier 1 / Tier 2 | — |
| **Human oversight protocol** | Document how oversight will operate (Article 14) | AI System Owner | AI System Owner | AI Governance Lead |

### Stage 5: Monitoring and Operations

| Document | Purpose | Responsible | Accountable | Reviewer |
|----------|---------|-------------|-------------|----------|
| **Monitoring reports** | Record ongoing performance, data quality, oversight metrics | ML Engineering Lead + Data Steward | AI System Owner | Tier 2 |
| **Automatic logs** (Article 12) | Immutable record of system operation | ML Engineering Lead | AI System Owner | AI Governance Lead |
| **AI literacy training records** | Evidence of Article 4 training completion | AI Governance Lead | AI Governance Lead | Tier 2 |
| **Quarterly review records** | Document risk register and performance reviews | AI Governance Lead | AI System Owner | Tier 2 |

### Stage 6: Incident Response

| Document | Purpose | Responsible | Accountable | Reviewer |
|----------|---------|-------------|-------------|----------|
| **Incident report** | Record the incident, severity, response | AI Governance Lead | AI System Owner | Tier 1 (serious) / Tier 2 |
| **Root cause analysis** | Document investigation findings | Data Steward / ML Eng (per cause) | AI System Owner | AI Governance Lead |
| **Regulatory notification** (if serious) | Record notification to authority | Compliance Officer | Compliance Officer | AI Governance Lead + Legal |
| **Post-incident review** | Document lessons and corrective actions | AI Governance Lead | AI System Owner | Tier 2 |

### Stage 7: Change and Retirement

| Document | Purpose | Responsible | Accountable | Reviewer |
|----------|---------|-------------|-------------|----------|
| **Change impact assessment** | Assess whether a change requires re-assessment | AI Governance Lead | AI System Owner | Tier 2 |
| **Updated model/system cards** | Reflect material changes | ML Engineering Lead | AI System Owner | AI Governance Lead |
| **Retirement record** | Document decommissioning and data disposition | AI System Owner | AI System Owner | AI Governance Lead |
| **Evidence archive** | Preserve all documentation post-retirement | AI Governance Lead | AI Governance Lead | — |

---

## 3. Documentation Standards (Quality Requirements)

Every document produced under this standard must meet these requirements:

| Requirement | Standard |
|-------------|----------|
| **Version control** | Every document is version-controlled with a version number and date. Changes are tracked. |
| **Attribution** | Every document states who authored it and who reviewed it. |
| **Dating** | Every document is dated at creation and at each revision. |
| **Completeness** | No required section is left blank. If a section does not apply, it states "Not applicable" with a reason. |
| **Plain language** | Documents intended for non-technical stakeholders (compliance, business, regulators) are written in plain language. |
| **Traceability** | Documents cross-reference related documents (a model card links to its risk register entries, its data governance records, its system card). |
| **Accessibility** | Documents are stored in a governed repository accessible to the governance team for audit. |
| **Immutability where required** | Logs and decision records are immutable — they can be appended to but not altered retrospectively. |

---

## 4. Review Cadence

| Document type | Review cadence | Triggered review |
|---------------|----------------|------------------|
| Model cards | Annually | Retraining, performance change, intended use change |
| System cards | Annually | Architecture change, component change, new oversight point |
| Risk register | Quarterly | Incident, material change, new regulation |
| Evidence packs | Annually per system | Material change, re-assessment, regulatory query |
| Data governance records | Monthly (quality metrics) | Data source change, pipeline change, quality breach |
| Annex IV documentation | Annually | Any material change to the system |
| Monitoring reports | Continuous production, monthly review | Threshold breach |
| This documentation standard | Annually | Regulatory change, programme maturity change |

---

## 5. Proportionality: Documentation by Risk Tier

Not every system needs every document. The standard scales with risk.

| Document | High-Risk | Limited-Risk | Minimal-Risk |
|----------|-----------|--------------|--------------|
| Intake form | Required | Required | Required (lightweight) |
| Risk classification record | Required | Required | Required |
| Full risk register | Required | Required | Optional |
| DPIA | If personal data | If personal data | If personal data |
| FRIA | If required | Not required | Not required |
| Model card | Required | Required | Recommended |
| System card | Required (if compound) | Recommended | Optional |
| Annex IV documentation | Required | Not required | Not required |
| Data governance records | Required | Required | Recommended |
| Evidence pack | Required | Required (lightweight) | Not required |
| Conformity self-assessment | Required | Not required | Not required |
| Human oversight protocol | Required | If applicable | Not required |
| Monitoring reports | Required | Required | Optional |
| Automatic logs | Required | Recommended | Optional |

---

## 6. Documentation Governance

| Element | Requirement |
|---------|-------------|
| **Repository** | All AI documentation is stored in a single governed repository (or catalogue) accessible to the AI Governance Lead and auditable. |
| **Templates** | All documentation uses the organisation's standard templates (model card, system card, intake form, risk register). Deviations require AI Governance Lead approval. |
| **Completeness tracking** | The AI Governance Lead tracks documentation completeness per system as a governance KPI (see governance cadence). |
| **Audit readiness** | At any time, the organisation must be able to produce a complete, current evidence pack for any high-risk system within 5 business days. |
| **Retention** | Documentation is retained per regulatory requirements (AI Act requires technical documentation to be kept for 10 years after the system is placed on the market). |

---

## 7. Roles Summary

| Role | Documentation responsibility |
|------|------------------------------|
| **AI System Owner** | Accountable for all documentation for their system being complete and current |
| **AI Governance Lead** | Owns this standard; reviews documents for completeness; tracks completeness KPI; compiles evidence packs |
| **ML Engineering Lead** | Produces model cards, Annex IV technical documentation, monitoring reports, logs |
| **Data Steward** | Produces data governance records, data profiling reports, lineage documentation |
| **Data Owner** | Accountable for data governance records being accurate |
| **DPO** | Produces DPIAs; reviews documents involving personal data |
| **Compliance Officer** | Produces regulatory applicability records and regulatory notifications |
| **Tier 2 Working Group** | Reviews and signs off risk assessments, evidence packs, classification records |
| **Tier 1 Committee** | Reviews and approves high-risk deployment decision records |

---

## 8. The Principle Behind the Standard

Documentation is often treated as bureaucratic overhead — something you do to satisfy auditors, separate from the "real work" of building AI. This standard rejects that framing.

Documentation is the accountability mechanism of AI governance. A model card is not paperwork; it is the artefact that makes a model's limitations knowable to the people who deploy it. A system card is not a formality; it is the record that lets an incident be traced to its cause. An evidence pack is not a compliance chore; it is the difference between demonstrating control and hoping the regulator doesn't ask.

The EU AI Act made this explicit: it is a documentation-based regulation. You do not comply by intending to be responsible. You comply by producing evidence — dated, attributed, version-controlled evidence — that you identified the risks, assessed the data, tested the system, designed the oversight, and monitored the outcome. This standard is how that evidence gets produced consistently, by the right people, at the right time.

Documentation, done properly, is governance made visible.
