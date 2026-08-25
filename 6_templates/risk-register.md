# AI Risk Register

> **Purpose:** Living document to identify, assess, treat, and monitor risks for each AI system throughout its lifecycle. One risk register per AI system (or shared across a programme with system-level tagging).
>
> **Owner:** AI Governance Lead
>
> **Review cadence:** Quarterly (minimum), plus triggered reviews after incidents, material changes, or regulatory updates.
>
> **Regulatory basis:** EU AI Act Article 9 (Risk Management System), Article 15 (Accuracy, Robustness, Cybersecurity).

---

## How to Use This Register

1. **Identify** risks during intake and risk assessment (use the intake form to surface initial risks).
2. **Assess** each risk for likelihood and impact using the scoring matrix below.
3. **Treat** each risk using the Article 9.3 hierarchy: eliminate by design → mitigate → accept and document residual risk → inform deployers.
4. **Monitor** each risk on the defined cadence. Update status at every quarterly review.
5. **Escalate** any risk that moves to Critical or any new risk identified post-deployment.

---

## Risk Scoring Matrix

### Likelihood

| Score | Level | Description |
|-------|-------|-------------|
| 1 | Rare | Could occur in exceptional circumstances only |
| 2 | Unlikely | Could occur but not expected |
| 3 | Possible | Might occur at some point |
| 4 | Likely | Will probably occur in most circumstances |
| 5 | Almost Certain | Expected to occur frequently |

### Impact

| Score | Level | Description |
|-------|-------|-------------|
| 1 | Negligible | Minimal operational or compliance impact |
| 2 | Minor | Limited operational disruption, low financial impact |
| 3 | Moderate | Noticeable operational disruption, moderate financial or reputational impact |
| 4 | Major | Significant operational, financial, or legal impact; potential regulatory action |
| 5 | Severe | Fundamental rights violation, major regulatory penalty, existential business impact |

### Risk Rating

| Rating | Score Range | Action Required |
|--------|------------|-----------------|
| **Critical** | 15–25 | Immediate escalation. Stop deployment until mitigated. Board / exec awareness required. |
| **High** | 10–14 | Mitigation plan required before deployment. Senior management review. Monthly monitoring. |
| **Medium** | 5–9 | Mitigation plan required. Quarterly monitoring. Documented acceptance if residual risk. |
| **Low** | 1–4 | Accept and monitor. Annual review sufficient. |

---

## Risk Register

### Risk Entry Template

For each identified risk, complete the following fields:

| Field | Description |
|-------|-------------|
| **Risk ID** | Unique identifier (e.g., R-001) |
| **AI System** | Name / ID of the AI system this risk applies to |
| **Risk Category** | See categories below |
| **Risk Description** | Clear description of what could go wrong |
| **Affected Stakeholders** | Who is impacted (customers, employees, regulators, business) |
| **Root Cause** | What causes or contributes to this risk |
| **Likelihood** (1–5) | How likely is this risk to materialise |
| **Impact** (1–5) | How severe would the consequences be |
| **Risk Score** | Likelihood × Impact |
| **Risk Rating** | Critical / High / Medium / Low |
| **Treatment** | Eliminate / Mitigate / Accept / Transfer |
| **Treatment Description** | Specific actions to address the risk |
| **Control(s)** | Reference to controls from the EU AI Act controls map |
| **Residual Risk** | Risk level after treatment (re-score) |
| **Owner** | Person accountable for managing this risk |
| **Review Cadence** | How often this risk is reviewed |
| **Status** | Open / In Treatment / Accepted / Closed |
| **Last Reviewed** | Date of most recent review |
| **Next Review** | Date of next scheduled review |

---

## Risk Categories

| Category | Description | EU AI Act Reference |
|----------|-------------|---------------------|
| **Algorithmic Bias** | Discriminatory outputs affecting protected groups | Art 9.2(a), Art 10 |
| **Data Quality** | Training, validation, or operational data that is incomplete, inaccurate, outdated, or unrepresentative | Art 10, Art 15 |
| **Data Governance** | Inadequate data ownership, cataloguing, lineage, or quality measurement undermining AI system reliability | Art 10 |
| **Model Performance** | Accuracy, precision, recall, or robustness degradation over time | Art 9.4, Art 15 |
| **Transparency** | Insufficient explainability or disclosure to affected persons or deployers | Art 13, Art 50 |
| **Human Oversight Failure** | Oversight mechanisms insufficient, overridden, or ignored | Art 14 |
| **Security / Adversarial** | Data poisoning, model extraction, adversarial inputs, cybersecurity vulnerabilities | Art 15 |
| **Regulatory Non-Compliance** | Failure to meet requirements under EU AI Act, GDPR, DORA, DMA, SOx, MiFID II, or other applicable regulations | Art 9–15, plus cross-regulatory |
| **Fundamental Rights** | Infringement of rights to privacy, non-discrimination, dignity, or effective remedy | Art 9.2(a), Recitals |
| **Operational** | System availability, latency, integration failures, dependency risks | Art 12, Art 15 |
| **Reputational** | Public trust damage from AI incidents, media exposure, or perceived harm | — |
| **Third-Party / Vendor** | Risks introduced by vendor-provided AI components, APIs, or models | Art 25, Art 28 |
| **Misuse** | Use of the AI system in ways not intended by the provider (foreseeable misuse) | Art 9.2(b) |

---

## Example Risk Entries

The following examples demonstrate how to populate the register for common financial services AI risks. These are starting points — adapt to your specific systems.

---

### R-001: Algorithmic Bias in Credit Scoring

| Field | Value |
|-------|-------|
| **Risk ID** | R-001 |
| **AI System** | Credit Scoring Model v2.3 |
| **Risk Category** | Algorithmic Bias |
| **Risk Description** | Credit scoring model produces systematically lower scores for applicants from specific postal codes, acting as a proxy for ethnicity or socioeconomic status, resulting in discriminatory lending decisions. |
| **Affected Stakeholders** | Loan applicants (natural persons), business (regulatory exposure), regulators |
| **Root Cause** | Historical lending data reflects past discriminatory practices; model learns and amplifies existing patterns. Insufficient bias testing during validation. |
| **Likelihood** | 4 (Likely) |
| **Impact** | 5 (Severe — fundamental rights violation, regulatory penalty) |
| **Risk Score** | 20 |
| **Risk Rating** | **Critical** |
| **Treatment** | Mitigate |
| **Treatment Description** | (1) Conduct bias audit across protected characteristics before deployment. (2) Implement fairness constraints in model training. (3) Establish ongoing bias monitoring with quarterly reporting. (4) Define acceptable fairness thresholds (e.g., demographic parity ratio > 0.8). (5) Create escalation path if thresholds breached. |
| **Control(s)** | Art 9.2(a) risk identification, Art 10 bias assessment, Art 9.4 pre-market testing |
| **Residual Risk** | 8 (Medium) — bias reduced but not eliminated; ongoing monitoring required |
| **Owner** | Head of Risk / Model Risk Manager |
| **Review Cadence** | Monthly |
| **Status** | In Treatment |
| **Last Reviewed** | |
| **Next Review** | |

---

### R-002: Data Quality Degradation in Fraud Detection

| Field | Value |
|-------|-------|
| **Risk ID** | R-002 |
| **AI System** | Transaction Fraud Detection Engine |
| **Risk Category** | Data Quality |
| **Risk Description** | Training data quality degrades over time as transaction patterns evolve (concept drift). Stale training data leads to increasing false positive rates, blocking legitimate transactions and degrading customer experience, while simultaneously increasing false negatives (missed fraud). |
| **Affected Stakeholders** | Customers (blocked transactions), business (fraud losses, customer churn), operations (manual review burden) |
| **Root Cause** | No automated data quality monitoring on model input data. Training data not refreshed on a defined cadence. No data quality thresholds triggering retraining. Data quality measurement not connected to model performance monitoring. |
| **Likelihood** | 4 (Likely — concept drift is inevitable in fraud detection) |
| **Impact** | 4 (Major — financial losses + customer impact + potential regulatory scrutiny) |
| **Risk Score** | 16 |
| **Risk Rating** | **Critical** |
| **Treatment** | Mitigate |
| **Treatment Description** | (1) Implement continuous data quality monitoring on model input features (completeness, freshness, distribution shift). (2) Define data quality thresholds that trigger automatic alerts and model retraining. (3) Establish quarterly data quality reviews tied to model performance metrics (precision, recall, FPR). (4) Document data quality metrics in evidence pack for AI Act Article 10 compliance. (5) Create data quality SLA between data engineering and model team. |
| **Control(s)** | Art 10 data quality criteria, Art 15 accuracy measurement, Art 9.2(c) post-deployment risk evaluation |
| **Residual Risk** | 8 (Medium) — drift still occurs but detected and managed within defined thresholds |
| **Owner** | Data Governance Lead / ML Engineering Lead |
| **Review Cadence** | Monthly (continuous monitoring with monthly review) |
| **Status** | Open |
| **Last Reviewed** | |
| **Next Review** | |

---

### R-003: Regulatory Non-Compliance (Multi-Regulatory)

| Field | Value |
|-------|-------|
| **Risk ID** | R-003 |
| **AI System** | Customer Churn Prediction (all AI systems — cross-cutting risk) |
| **Risk Category** | Regulatory Non-Compliance |
| **Risk Description** | Failure to comply with overlapping regulatory obligations across EU AI Act, GDPR, DORA, DMA, and/or SOx, leading to enforcement action, fines, or operational restrictions. Specific sub-risks: (a) AI Act: incomplete Annex IV documentation or missing conformity assessment for high-risk systems. (b) GDPR: DPIA not completed for AI processing personal data; Article 22 automated decision-making rights not implemented. (c) DORA: AI vendor not assessed as critical ICT third-party provider; no operational resilience testing. (d) DMA: training data sourced from gatekeeper platform without compliance with data access obligations. (e) SOx: AI system influencing financial reporting without ITGC-compliant data governance controls. |
| **Affected Stakeholders** | Business (fines up to €35M or 7% global turnover under AI Act; €20M or 4% under GDPR), regulators, customers, shareholders |
| **Root Cause** | No centralised regulatory obligation tracking. Compliance managed in silos (privacy team handles GDPR, IT handles DORA, legal handles AI Act). No cross-regulatory mapping of AI systems to applicable obligations. Insufficient governance capacity. |
| **Likelihood** | 3 (Possible — enforcement ramping up but phased timeline provides buffer) |
| **Impact** | 5 (Severe — cumulative fines across regulations, reputational damage, potential market withdrawal orders) |
| **Risk Score** | 15 |
| **Risk Rating** | **Critical** |
| **Treatment** | Mitigate |
| **Treatment Description** | (1) Create centralised AI system inventory mapping each system to all applicable regulations. (2) Implement cross-regulatory obligation engine (see regulatory landscape overview). (3) Assign single compliance owner per AI system responsible for all regulatory requirements. (4) Conduct quarterly regulatory horizon scanning. (5) Produce combined evidence packs that satisfy multiple regulations simultaneously. (6) Engage external legal review annually. |
| **Control(s)** | Art 9.1 risk management system, Art 11 technical documentation, regulatory landscape cross-mapping |
| **Residual Risk** | 6 (Medium) — compliance gaps reduced but multi-regulatory complexity remains |
| **Owner** | Chief Compliance Officer / AI Governance Lead |
| **Review Cadence** | Quarterly + triggered by regulatory updates |
| **Status** | Open |
| **Last Reviewed** | |
| **Next Review** | |

---

### R-004: Human Oversight Circumvention

| Field | Value |
|-------|-------|
| **Risk ID** | R-004 |
| **AI System** | AML Transaction Monitoring |
| **Risk Category** | Human Oversight Failure |
| **Risk Description** | Human reviewers auto-approve AI-flagged alerts without meaningful review due to alert fatigue (high volume of false positives) or time pressure, effectively removing the human-in-the-loop safeguard required by Article 14. |
| **Affected Stakeholders** | Regulators (AML compliance failure), customers (false accusations), business (regulatory penalty, criminal liability) |
| **Root Cause** | Alert volume exceeds human review capacity. No monitoring of reviewer behaviour (e.g., time-per-review, override rate). Training insufficient. Performance incentives reward throughput over quality. |
| **Likelihood** | 4 (Likely) |
| **Impact** | 4 (Major — AML compliance failure has criminal liability implications) |
| **Risk Score** | 16 |
| **Risk Rating** | **Critical** |
| **Treatment** | Mitigate |
| **Treatment Description** | (1) Monitor reviewer behaviour metrics (time-per-alert, approval rate, override frequency). (2) Set minimum review time thresholds. (3) Implement random audit of approved alerts. (4) Reduce alert volume by improving model precision. (5) Annual human oversight training with competency assessment. (6) Document oversight effectiveness metrics in evidence pack. |
| **Control(s)** | Art 14 human oversight design, Art 14 oversight personnel training, Art 9.2(c) post-deployment risk evaluation |
| **Residual Risk** | 8 (Medium) |
| **Owner** | Head of Financial Crime / AML Compliance |
| **Review Cadence** | Monthly |
| **Status** | Open |
| **Last Reviewed** | |
| **Next Review** | |

---

### R-005: Vendor Model Opacity

| Field | Value |
|-------|-------|
| **Risk ID** | R-005 |
| **AI System** | Vendor-provided Insurance Pricing Engine |
| **Risk Category** | Third-Party / Vendor |
| **Risk Description** | Vendor refuses to provide sufficient technical documentation, model cards, or training data information to satisfy Annex IV requirements. Deployer cannot demonstrate compliance because the information is claimed as proprietary by the vendor. |
| **Affected Stakeholders** | Business (compliance gap), regulators (incomplete documentation), customers (inability to exercise Article 22 rights) |
| **Root Cause** | Vendor contract does not include AI Act compliance obligations. Vendor headquartered outside EU. No audit rights negotiated. |
| **Likelihood** | 3 (Possible) |
| **Impact** | 4 (Major — cannot demonstrate compliance for a high-risk system) |
| **Risk Score** | 12 |
| **Risk Rating** | **High** |
| **Treatment** | Mitigate |
| **Treatment Description** | (1) Renegotiate contract to include AI Act compliance clauses (transparency, audit rights, documentation obligations). (2) If vendor refuses, conduct vendor risk assessment and document inability to verify compliance. (3) Evaluate alternative vendors with EU AI Act compliance capability. (4) Implement compensating controls where possible (own testing, monitoring, documentation of known limitations). (5) Inform regulator of vendor limitation if required during supervisory engagement. |
| **Control(s)** | Art 11 technical documentation, Art 13 transparency, Art 25/28 provider-deployer obligations |
| **Residual Risk** | 8 (Medium) — depends on vendor cooperation |
| **Owner** | Procurement / Vendor Management + Legal |
| **Review Cadence** | Quarterly |
| **Status** | Open |
| **Last Reviewed** | |
| **Next Review** | |

---

## Register Summary View

*Use this summary table for governance committee reporting. Full detail in entries above.*

| Risk ID | AI System | Category | Description (short) | Score | Rating | Treatment | Owner | Status |
|---------|-----------|----------|---------------------|-------|--------|-----------|-------|--------|
| R-001 | Credit Scoring | Algorithmic Bias | Proxy discrimination via postal code | 20 | Critical | Mitigate | Head of Risk | In Treatment |
| R-002 | Fraud Detection | Data Quality | Concept drift degrading model performance | 16 | Critical | Mitigate | Data Gov Lead | Open |
| R-003 | All Systems | Regulatory Non-Compliance | Multi-regulatory gaps (AI Act + GDPR + DORA + DMA + SOx) | 15 | Critical | Mitigate | CCO | Open |
| R-004 | AML Monitoring | Human Oversight | Alert fatigue circumventing human review | 16 | Critical | Mitigate | Head of FinCrime | Open |
| R-005 | Insurance Pricing | Vendor Risk | Vendor opacity blocking Annex IV compliance | 12 | High | Mitigate | Procurement | Open |
| | | | | | | | | |
| | | | | | | | | |

---

## Review Log

| Review Date | Reviewer | Risks Reviewed | Changes Made | Next Review Date |
|-------------|----------|----------------|--------------|------------------|
| | | | | |
| | | | | |
| | | | | |

---

## Appendix: Risk Register Governance

| Element | Requirement |
|---------|-------------|
| **New risk identification** | Any team member can submit a risk. Governance Lead triages within 5 business days. |
| **Escalation** | Any Critical risk escalated to senior management within 24 hours. |
| **Quarterly review** | All open risks reviewed. Scores updated. Treatment progress assessed. |
| **Post-incident review** | After any AI incident, check risk register for related risks. Add new risks if identified. Update scores. |
| **Regulatory trigger** | When new regulation, guidance, or enforcement action is published, review all risks for impact. |
| **Annual full review** | Complete re-assessment of all risks, treatment effectiveness, and register completeness. |
