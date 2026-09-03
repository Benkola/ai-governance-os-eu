# AI Audit Checklist

> **Purpose:** A structured checklist for auditing an AI system — whether an internal governance review, a readiness check before a regulatory inspection, or an external audit. It answers the question a regulator or auditor actually asks: "Show me the evidence." Each item maps to a specific EU AI Act obligation and, where relevant, a NIST AI RMF function, and specifies what evidence demonstrates compliance.
>
> **When to use:** Internal audits (quarterly/annual per the governance cadence), pre-inspection readiness checks, external audits, and due diligence (e.g., during acquisition or vendor assessment).
>
> **How to use:** For each item, record the status (Met / Partial / Not Met / N/A) and the evidence reference. Gaps become remediation actions. A high-risk system should be able to answer every applicable item with evidence.
>
> **Owner:** AI Governance Lead conducts internal audits; supports external auditors.

---

## How to Score

| Status | Meaning |
|--------|---------|
| **Met** | Requirement satisfied with evidence on file |
| **Partial** | Partially satisfied; gaps documented |
| **Not Met** | Requirement not satisfied — remediation required |
| **N/A** | Not applicable to this system (state why) |

**Audit readiness standard:** For a high-risk system, every applicable item should be "Met" with a named evidence artefact. "We intend to" is not evidence. "It's documented somewhere" is not evidence. A specific, dated, attributed artefact is evidence.

---

## Section 1 — Governance and Accountability

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 1.1 | The system is registered in the AI inventory with risk classification | Art 6, 49 | Govern | AI inventory entry; classification record | | |
| 1.2 | An accountable owner is assigned | Art 16, 22 | Govern | RACI; named AI System Owner | | |
| 1.3 | Applicable regulations are mapped (AI Act + GDPR + sector) | Art 2 | Govern | Regulatory applicability record | | |
| 1.4 | Governance bodies reviewed this system on cadence | Art 9 | Govern | Committee minutes; review log | | |
| 1.5 | AI literacy training completed for relevant staff | Art 4 | Govern | Training completion records | | |

---

## Section 2 — Risk Management (Article 9)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 2.1 | A risk management system exists and is continuous | Art 9.1 | Map, Manage | Risk register; review cadence |  | |
| 2.2 | Known and foreseeable risks are identified | Art 9.2(a) | Map | Risk register entries with root causes | | |
| 2.3 | Risks from foreseeable misuse are assessed | Art 9.2(b) | Map | Misuse analysis | | |
| 2.4 | Post-deployment risks are evaluated | Art 9.2(c) | Measure | Monitoring records; updated register | | |
| 2.5 | Risk treatment follows the elimination/mitigation hierarchy | Art 9.3 | Manage | Treatment decisions with rationale | | |
| 2.6 | Residual risks are documented and accepted at the right level | Art 9.3 | Manage | Signed risk acceptance | | |
| 2.7 | Pre-market testing was conducted against defined metrics | Art 9.4 | Measure | Test results; thresholds | | |

---

## Section 3 — Data Governance (Article 10)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 3.1 | Training/validation/test data governance practices are documented | Art 10.2 | Map, Measure | Data governance records | | |
| 3.2 | Data is relevant, representative, and appropriately complete | Art 10.3 | Measure | Data profiling; quality metrics | | |
| 3.3 | Data quality is measured against defined criteria | Art 10.3 | Measure | Quality dashboards; thresholds | | |
| 3.4 | Datasets examined for bias | Art 10.2(f) | Measure | Bias assessment | | |
| 3.5 | Data gaps identified relative to deployment context | Art 10.2(g) | Map | Gap analysis | | |
| 3.6 | Data lineage is documented (source to model input) | Art 10, 11 | Map | Lineage documentation | | |
| 3.7 | Special category data processing has lawful basis and safeguards | Art 10.5 | Govern | DPIA; lawful basis record | | |

---

## Section 4 — Technical Documentation (Article 11 / Annex IV)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 4.1 | Annex IV technical documentation exists and is current | Art 11 | Govern | Technical documentation | | |
| 4.2 | A model card documents the model | Art 11, 13 | Measure | Model card | | |
| 4.3 | A system card documents compound systems | Art 11 | Map | System card | | |
| 4.4 | The intended purpose is clearly specified | Art 11 | Govern | Documentation; intended-use statement | | |
| 4.5 | Documentation is version-controlled, dated, attributed | Art 11 | Govern | Version history | | |

---

## Section 5 — Record-Keeping and Logging (Article 12)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 5.1 | The system automatically logs its operation | Art 12.1 | Measure | Log samples; logging design | | |
| 5.2 | Logs enable traceability of decisions | Art 12.2 | Measure | Decision reconstruction example | | |
| 5.3 | Logs are retained for the required period | Art 12 | Govern | Retention policy | | |
| 5.4 | Logs are immutable / tamper-evident | Art 12 | Manage | Log integrity controls | | |

---

## Section 6 — Transparency (Articles 13 and 50)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 6.1 | Deployer instructions provided (accuracy, robustness, limitations) | Art 13 | Govern | Instructions for use | | |
| 6.2 | Users informed when interacting with AI (if applicable) | Art 50.1 | Govern | Disclosure implementation | | |
| 6.3 | AI-generated content is marked/disclosed (if applicable) | Art 50.2/4 | Govern | Marking implementation | | |
| 6.4 | Emotion recognition / biometric categorisation disclosed (if applicable) | Art 50.3 | Govern | Disclosure | | |

---

## Section 7 — Human Oversight (Article 14)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 7.1 | Human oversight measures are designed and documented | Art 14.1 | Govern, Manage | Oversight protocol | | |
| 7.2 | Overseers can understand the system's capabilities and limits | Art 14.4(a) | Govern | Training materials | | |
| 7.3 | Overseers can detect anomalies and automation bias | Art 14.4(b,c) | Manage | Oversight metrics | | |
| 7.4 | Overseers can override or halt the system | Art 14.4(d,e) | Manage | Override mechanism; stop control | | |
| 7.5 | Oversight effectiveness is monitored (not just present) | Art 14 | Measure | Override rate, review-time metrics | | |

---

## Section 8 — Accuracy, Robustness, Cybersecurity (Article 15)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 8.1 | Accuracy levels are declared and appropriate | Art 15.1 | Measure | Declared metrics | | |
| 8.2 | Accuracy is monitored throughout the lifecycle | Art 15 | Measure | Monitoring dashboard | | |
| 8.3 | The system is robust to errors and edge cases | Art 15.4 | Measure | Robustness testing | | |
| 8.4 | Cybersecurity measures address AI-specific threats | Art 15.5 | Manage | Security assessment (poisoning, adversarial) | | |
| 8.5 | Feedback loops don't cause harmful drift | Art 15.4 | Measure | Drift monitoring | | |

---

## Section 9 — Post-Market Monitoring and Incident Response

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 9.1 | A monitoring plan is in place and operating | Art 72 | Measure | Monitoring playbook; live dashboards | | |
| 9.2 | An incident response process exists | Art 73 | Manage | Incident response playbook | | |
| 9.3 | Serious incident reporting process is understood | Art 73 | Manage | Notification procedure; Legal alignment | | |
| 9.4 | Past incidents were handled and documented | Art 73 | Manage | Incident log; post-mortems | | |

---

## Section 10 — Conformity and Registration (High-Risk)

| # | Audit item | EU AI Act | NIST RMF | Evidence to collect | Status | Reference |
|---|-----------|-----------|----------|---------------------|--------|-----------|
| 10.1 | Conformity assessment completed | Art 43 | Govern | Conformity assessment record | | |
| 10.2 | EU declaration of conformity drawn up | Art 47 | Govern | Declaration | | |
| 10.3 | System registered in the EU database (where required) | Art 49, 71 | Govern | Registration reference | | |
| 10.4 | CE marking affixed (where applicable) | Art 48 | Govern | Marking evidence | | |

> **Timeline note:** For Annex III high-risk systems, conformity and registration obligations apply from 2 December 2027 (Digital Omnibus, Reg (EU) 2026/1744). Classification and preparation should be complete before then.

---

## Audit Summary

| Section | Items | Met | Partial | Not Met | N/A |
|---------|-------|-----|---------|---------|-----|
| 1. Governance | 5 | | | | |
| 2. Risk Management | 7 | | | | |
| 3. Data Governance | 7 | | | | |
| 4. Technical Documentation | 5 | | | | |
| 5. Record-Keeping | 4 | | | | |
| 6. Transparency | 4 | | | | |
| 7. Human Oversight | 5 | | | | |
| 8. Accuracy/Robustness | 5 | | | | |
| 9. Monitoring/Incident | 4 | | | | |
| 10. Conformity | 4 | | | | |
| **Total** | **50** | | | | |

**Overall audit result:** ☐ Audit-ready ☐ Minor gaps (remediate) ☐ Material gaps (do not deploy / escalate)

**Top remediation priorities:**

1.
2.
3.

**Auditor:** _______________ **Date:** _______________ **Next audit:** _______________

---

## Evidence Collection Guide

The recurring theme of this checklist is *evidence*. For each item, acceptable evidence is:

- **A specific artefact** — a named, dated, version-controlled document, not "it's on the wiki somewhere."
- **Attributable** — it shows who produced it and who reviewed it.
- **Current** — it reflects the system as it operates now, not as it was designed two years ago.
- **Traceable** — it links to related evidence (a model card links to its risk register, its data records, its monitoring).

If you cannot point to a specific artefact for an item, that item is Not Met — regardless of whether the underlying work was done. In a documentation-based regulation, undocumented compliance is indistinguishable from non-compliance.
