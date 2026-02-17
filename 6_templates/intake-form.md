# AI Use Case Intake Form

**Purpose:** Standardised entry point for any AI system (ML, GenAI, vendor-provided, or hybrid) before it enters the governance lifecycle. Every use case must complete this form before classification, risk assessment, or approval.

**Owner:** AI Governance Lead (or Product Owner if no dedicated governance function exists)

**When to use:** Before any AI system is procured, developed, piloted, or deployed.

---

## 1. Use Case Identification

| Field | Response |
|-------|----------|
| **Use case name** | |
| **Submitting team / department** | |
| **Business sponsor (name, role)** | |
| **Technical lead (name, role)** | |
| **Submission date** | |
| **Target go-live date** | |
| **Use case ID** (assigned by governance) | |

---

## 2. Business Context

### 2.1 Problem Statement

*What business problem does this AI system solve? Be specific about the current process, its limitations, and the expected improvement.*

| Field | Response |
|-------|----------|
| **Current process (without AI)** | |
| **Specific limitation / pain point** | |
| **Proposed AI solution (1–2 sentences)** | |
| **Expected business outcome** | |
| **How will success be measured?** | |
| **Estimated users / affected persons** | |

### 2.2 AI System Type

| Type | Yes / No | Details |
|------|----------|---------|
| Internally developed ML model | | |
| Vendor-provided AI product | | Vendor name: |
| GenAI / LLM-based system | | Model(s) used: |
| Rule-based system with ML component | | |
| AI-as-a-Service (API) | | Provider: |
| Other | | Describe: |

### 2.3 Deployment Context

| Field | Response |
|-------|----------|
| **Who interacts with the system?** (employees, customers, both) | |
| **Is the output used to make decisions about natural persons?** | Yes / No |
| **If yes, what decisions?** | |
| **Can a natural person override the AI output?** | Yes / No |
| **Is the system customer-facing?** | Yes / No |
| **Geographies where the system will operate** | |

---

## 3. Preliminary Risk Classification

*This section determines the initial risk tier under the EU AI Act. Final classification is confirmed during the risk assessment stage.*

### 3.1 Prohibited Practices Check (Article 5)

| Question | Yes / No |
|----------|----------|
| Does the system use subliminal, manipulative, or deceptive techniques to distort behaviour? | |
| Does the system exploit vulnerabilities (age, disability, social/economic situation)? | |
| Does the system perform social scoring by or on behalf of public authorities? | |
| Does the system perform real-time remote biometric identification in public spaces for law enforcement? | |
| Does the system infer emotions in workplaces or educational institutions (except medical/safety)? | |
| Does the system create or expand facial recognition databases through untargeted scraping? | |

> **If any answer is YES:** Stop. This use case may involve a prohibited AI practice. Escalate immediately to Legal and the AI Governance Lead. Do not proceed.

### 3.2 High-Risk Indicators (Annex III)

| Annex III Category | Applicable? | Details |
|-------------------|-------------|---------|
| Biometric identification and categorisation | Yes / No | |
| Critical infrastructure management (transport, energy, water, digital) | Yes / No | |
| Education and vocational training (access, assessment, behaviour monitoring) | Yes / No | |
| Employment and workers management (recruitment, evaluation, task allocation) | Yes / No | |
| Access to essential services (credit scoring, insurance pricing, emergency dispatch) | Yes / No | |
| Law enforcement (risk assessment, polygraph, evidence evaluation) | Yes / No | |
| Migration, asylum, and border control | Yes / No | |
| Administration of justice and democratic processes | Yes / No | |

> **If any answer is YES:** This use case is likely **high-risk** under the AI Act. Full risk assessment, technical documentation (Annex IV), conformity assessment, and ongoing monitoring are required before deployment.

### 3.3 Transparency Obligations Check (Article 50)

| Question | Yes / No |
|----------|----------|
| Does the system interact directly with natural persons (chatbot, virtual assistant)? | |
| Does the system generate synthetic content (text, image, audio, video)? | |
| Does the system generate deep fakes? | |
| Does the system perform emotion recognition or biometric categorisation? | |

> **If any answer is YES:** Transparency obligations apply. Users must be informed they are interacting with AI, and synthetic content must be machine-readable as AI-generated.

### 3.4 Initial Risk Tier Assignment

| Risk Tier | Criteria | Assigned? |
|-----------|----------|-----------|
| **Prohibited** | Any Article 5 practice confirmed | ☐ |
| **High-Risk** | Any Annex III category confirmed, OR safety component of regulated product (Annex I) | ☐ |
| **Limited Risk** | Transparency obligations only (Article 50) | ☐ |
| **Minimal Risk** | No prohibited, high-risk, or transparency triggers | ☐ |

**Assigned risk tier:** _______________

**Classification rationale (1–2 sentences):**

---

## 4. Data Governance Readiness

> **Purpose:** Assess whether the data governance foundations required for responsible AI deployment are in place. These questions map directly to EU AI Act Article 10 (Data Governance) requirements and the data governance dependencies identified in the controls map.

### 4.1 Data Ownership

| Question | Yes / No / Partial | Details |
|----------|--------------------|---------|
| Does this use case have a designated data owner? | | Name / role: |
| Is the data owner accountable for data quality decisions? | | |
| Is there a documented data ownership policy that covers AI training / inference data? | | |

### 4.2 Data Cataloguing

| Question | Yes / No / Partial | Details |
|----------|--------------------|---------|
| Are the datasets used by this AI system catalogued (registered in a data catalogue or inventory)? | | Catalogue tool / location: |
| Does the catalogue entry include: data source, schema, refresh frequency, and sensitivity classification? | | |
| Is the catalogue accessible to the governance team for audit purposes? | | |

### 4.3 Data Quality Measurement

| Question | Yes / No / Partial | Details |
|----------|--------------------|---------|
| Is data quality measured for the datasets used by this system? | | |
| Which quality dimensions are measured? (completeness, accuracy, timeliness, consistency, uniqueness) | | List dimensions: |
| Are quality thresholds defined (e.g., minimum completeness > 95%)? | | |
| Is there a process to remediate data quality issues before they reach the AI system? | | |
| Are data quality metrics reported and reviewed on a regular cadence? | | Cadence: |

### 4.4 Data Lineage

| Question | Yes / No / Partial | Details |
|----------|--------------------|---------|
| Is data lineage documented for the datasets used by this system? | | |
| Can you trace data from source to the AI system's input (including transformations, joins, and enrichments)? | | |
| Is lineage documentation sufficient to satisfy AI Act Article 10 requirements (design choices, collection, preparation, labelling, relevance)? | | |
| If the AI system's output is used downstream, is that lineage also documented? | | |

### 4.5 Readiness Summary

| Capability | Status | Gap / Action Required |
|------------|--------|-----------------------|
| Data owner assigned | ☐ Ready ☐ Partial ☐ Not in place | |
| Data catalogued | ☐ Ready ☐ Partial ☐ Not in place | |
| Data quality measured | ☐ Ready ☐ Partial ☐ Not in place | |
| Data lineage documented | ☐ Ready ☐ Partial ☐ Not in place | |

**Overall data governance readiness:** ☐ Ready to proceed ☐ Gaps identified — remediation required before risk assessment

> **If gaps are identified:** Document remediation actions, assign owners, and set target dates. The use case cannot proceed to full risk assessment until critical data governance gaps (especially data quality measurement and lineage) are addressed, because risk assessments for AI systems are unreliable without understanding the data.

---

## 5. Regulatory and Legal Landscape

| Question | Yes / No | Details |
|----------|----------|---------|
| Does this system process personal data (GDPR applies)? | | |
| Is a DPIA required or already completed? | | DPIA reference: |
| Does automated decision-making under GDPR Article 22 apply? | | |
| Does DORA apply? (financial entity using AI in ICT risk management) | | |
| Does MiFID II apply? (algorithmic trading, investment advice) | | |
| Does PSD2 apply? (payment services, transaction monitoring) | | |
| Does Solvency II apply? (insurance pricing, risk models) | | |
| Does SOx apply? (AI influencing financial reporting for US-listed entities) | | |
| Any sector-specific regulation? | | Specify: |

---

## 6. Vendor Assessment (if applicable)

*Complete only if the AI system involves a third-party vendor.*

| Field | Response |
|-------|----------|
| **Vendor name** | |
| **Contract in place?** | Yes / No / In negotiation |
| **Has vendor provided AI Act compliance documentation?** | Yes / No |
| **Has vendor provided model cards / system documentation?** | Yes / No |
| **Does the contract include audit rights?** | Yes / No |
| **Does the contract specify data processing, retention, and deletion terms?** | Yes / No |
| **Is the vendor's data processing compliant with GDPR?** | Yes / No / Unknown |
| **Has a vendor risk assessment been completed?** | Yes / No |

---

## 7. Stakeholder Sign-Off

| Role | Name | Approval | Date |
|------|------|----------|------|
| Business Sponsor | | ☐ Approved ☐ Rejected ☐ Conditional | |
| Technical Lead | | ☐ Approved ☐ Rejected ☐ Conditional | |
| Data Owner | | ☐ Approved ☐ Rejected ☐ Conditional | |
| AI Governance Lead | | ☐ Approved ☐ Rejected ☐ Conditional | |
| DPO / Privacy Lead | | ☐ Approved ☐ Rejected ☐ Conditional | |
| Legal (if high-risk) | | ☐ Approved ☐ Rejected ☐ Conditional | |

**Conditions (if any):**

---

## 8. Next Steps

| If risk tier is... | Next step |
|--------------------|-----------|
| **Prohibited** | Escalate to Legal. Do not proceed. |
| **High-Risk** | Proceed to full risk assessment (`risk-register.md`). Produce Annex IV documentation. Complete conformity self-assessment. |
| **Limited Risk** | Implement transparency requirements. Document in evidence pack. Proceed to deployment with monitoring. |
| **Minimal Risk** | Proceed to deployment. Implement voluntary code of conduct measures. Log in AI system inventory. |

**Intake form completed by:** _______________
**Date:** _______________
**Governance review scheduled for:** _______________
