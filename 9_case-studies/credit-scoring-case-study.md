# Case Study: Governing a Credit Scoring Model End-to-End

> **Purpose:** This case study runs a single high-risk AI system — a credit scoring model at a mid-market lender — through every stage of the governance framework in this repo. It shows how the framework, controls map, templates, operating model, and documentation standard actually connect in practice. Where the other artefacts are the machinery, this is the machine running.
>
> **How to read it:** Follow the system from intake to monitoring. Each stage links to the artefact that governs it. This is both a worked example and a demonstration that the framework is operational, not theoretical.
>
> **Note on the scenario:** "NorthBank" is a fictional mid-market lender (900 employees, regulated by a national competent authority and, for its AI, by the EU AI Act). Any resemblance to a real institution is coincidental. The governance approach is real; the company is illustrative.
>
> **Regulatory timeline note (post-Omnibus):** Credit scoring is an Annex III high-risk use case. Under the Digital Omnibus (Regulation (EU) 2026/1744, in force 27 July 2026), high-risk obligations for stand-alone Annex III systems apply from **2 December 2027**. The deadline moved; the classification analysis did not. NorthBank classifies and prepares now, using the runway.

---

## The System

NorthBank uses a machine-learning credit scoring model to support consumer lending decisions. The model takes an applicant's financial history, employment data, existing obligations, and bureau data, and outputs a probability of default. A credit officer uses that score, alongside policy rules, to approve, decline, or refer an application.

| Attribute | Detail |
|-----------|--------|
| **System name** | NorthBank Consumer Credit Scoring Model v2.3 |
| **Business purpose** | Support consumer lending decisions (approve/decline/refer) |
| **Users** | Credit officers (internal); outcomes affect loan applicants (natural persons) |
| **AI type** | Gradient-boosted decision tree model, internally developed |
| **Volume** | ~4,000 applications/month |

---

## Stage 1 — Intake and Classification

*Artefact used: [`intake-form.md`](../6_templates/intake-form.md)*

The lending product team submits the intake form. Three findings emerge:

**Prohibited practices check (Article 5):** No prohibited practices. The model does not use subliminal techniques, social scoring, or any of the (now expanded) Article 5 prohibitions including the new NCII/CSAM categories added by the Omnibus.

**High-risk classification (Annex III):** The model falls squarely under Annex III — "access to essential private services," specifically creditworthiness assessment. This is textbook high-risk. Classification: **High-Risk**.

**Data governance readiness (intake Section 4):** This is where the first problem surfaces. The readiness check reveals:
- Data owner: assigned (Head of Credit Risk). ✓
- Data catalogued: partially — bureau data is catalogued, but internally derived features are not. ✗
- Data quality measured: no formal measurement on model input features. ✗
- Data lineage documented: no. ✗

**Intake outcome:** The system is high-risk, but it cannot proceed straight to a full risk assessment because three of four data governance foundations are missing. Per the framework, the data governance gaps are logged as remediation actions before the risk assessment can be relied upon. This is the [`data-governance-dependency-map.md`](../2_risk-and-controls/data-governance-dependency-map.md) principle in action: you cannot credibly assess a model's risks without understanding its data.

---

## Stage 2 — Data Governance Remediation

*Artefacts used: [`data-governance-baseline.md`](../3_scorecards/data-governance-baseline.md), [`data-governance-dependency-map.md`](../2_risk-and-controls/data-governance-dependency-map.md)*

NorthBank runs the 10-question data governance baseline. Score: **14/30 — Developing.** The lowest-scoring areas are exactly the ones flagged at intake: data quality measurement (Q2), data lineage (Q5), and cataloguing of derived features (Q3).

Remediation, sequenced per the baseline's recommended order:
- The Data Steward catalogues all derived features used by the model, with metadata (source, transformation, refresh).
- Data quality measurement is stood up on the model's input features: completeness, distribution stability, and freshness, with thresholds.
- Lineage is documented from bureau feed and core banking system through to the model's input vector.

This remediation is not bureaucratic overhead — it is the precondition for everything downstream. The bias assessment in Stage 3 is only possible because the data is now profiled.

---

## Stage 3 — Risk Assessment

*Artefact used: [`risk-register.md`](../6_templates/risk-register.md)*

With data foundations in place, the risk assessment proceeds. Four material risks are registered:

| Risk ID | Risk | Score | Rating | Treatment |
|---------|------|-------|--------|-----------|
| CS-01 | Proxy discrimination — postal code acting as a proxy for protected characteristics | 20 | Critical | Mitigate: bias audit, fairness constraints, ongoing monitoring |
| CS-02 | Data quality drift — model input features degrade as economic conditions shift | 16 | Critical | Mitigate: continuous quality monitoring, retraining triggers |
| CS-03 | Automation bias — credit officers rubber-stamp model scores without review | 12 | High | Mitigate: oversight metrics, minimum review standards |
| CS-04 | Regulatory non-compliance — incomplete Annex IV documentation before Dec 2027 | 9 | Medium | Mitigate: evidence pack production on the runway |

The bias risk (CS-01) is the headline. NorthBank runs a bias audit across the population and finds a demographic parity ratio of 0.74 — below the 0.80 threshold the risk committee sets. The model is scoring some groups systematically lower in a way not fully explained by underlying risk. This is a Critical finding, and it triggers the treatment described in Stage 4.

---

## Stage 4 — Controls and Human Oversight Design

*Artefacts used: [`eu-ai-act-controls-map.md`](../4_eu-ai-act/eu-ai-act-controls-map.md), operating model Article 14 design*

The controls map translates the risk findings into specific obligations:

**Article 9 (risk management):** The four risks are managed on the register with defined treatment and cadence. Risk management is continuous, not one-off.

**Article 10 (data governance):** The remediation from Stage 2 is the evidence. Bias assessment documented; data quality measured; lineage traceable.

**Article 14 (human oversight):** The credit officer is the human in the loop. But CS-03 (automation bias) shows that "a human reviews it" is not enough. NorthBank designs oversight that is *effective*: officers see the top factors driving each score, borderline cases are flagged for deeper review, and reviewer behaviour (override rate, review time) is monitored to detect rubber-stamping.

**Article 15 (accuracy, robustness):** Accuracy metrics are declared and monitored. The bias mitigation (fairness constraints applied in retraining) brings the demographic parity ratio to 0.86 — above threshold — while holding predictive accuracy within acceptable bounds.

---

## Stage 5 — Documentation

*Artefacts used: [`model-card-template.md`](../6_templates/model-card-template.md), [`system-card-template.md`](../6_templates/system-card-template.md), [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md)*

NorthBank produces:

**A model card** for the credit scoring model. Section 4 (metrics) records precision, recall, AUC, and the fairness metrics. Section 6 (training data) documents the remediated data governance. Section 9 cross-references each part to the AI Act article it satisfies — so the model card doubles as evidence.

**A system card** for the scoring *pipeline*, because the deployed system is compound: preprocessing → the ML model → policy rules engine → officer review queue. The system card documents the data flows, the oversight point (the review queue), and one emergent risk no model card captures: a policy rule interacting with a borderline model score to produce a decline the model alone would not have made. That interaction is registered and monitored.

**Documentation follows the standard:** every document is versioned, attributed, dated, and stored in the governed repository, per the [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md).

---

## Stage 6 — Evidence Pack and Deployment Decision

*Artefacts used: framework evidence pack concept, [`raci.md`](../1_framework/raci.md), [`governance-cadence.md`](../1_framework/governance-cadence.md)*

The AI Governance Lead assembles the evidence pack: intake form, risk register, data governance records, model card, system card, Annex IV documentation, conformity self-assessment, and human oversight protocol.

Because this is a high-risk system, the deployment decision sits with the **Tier 1 Committee** (per the RACI and operating model). The committee reviews the evidence pack, notes that the Critical bias risk has been mitigated to Medium residual, confirms the data governance remediation is complete, and approves deployment with two conditions: monthly bias monitoring for the first six months, and a review if the override rate exceeds a set threshold.

The decision, its rationale, and the conditions are logged. This is the audit trail.

---

## Stage 7 — Monitoring and Ongoing Governance

*Artefact used: [`governance-cadence.md`](../1_framework/governance-cadence.md)*

Post-deployment, the system enters the governance cadence:

- **Continuous:** data quality monitoring on input features (Data Steward), model accuracy monitoring (ML Engineering).
- **Monthly:** bias monitoring (the Tier 1 condition), reviewer behaviour metrics.
- **Quarterly:** risk register review — the four risks re-scored, treatment effectiveness assessed.
- **Triggered:** if the demographic parity ratio drops below 0.80, or the override rate breaches its threshold, an escalation fires to the Tier 2 Working Group.

Three months in, data quality monitoring detects distribution drift in an income-related feature (a data provider changed its schema). Because lineage was documented in Stage 2, the issue is traced to the source within hours, not weeks. The model is protected before its accuracy degrades. This is the payoff of the whole framework: a data problem is caught and diagnosed because the data governance foundations were built first.

---

## What This Case Study Demonstrates

1. **The framework is operational.** Every stage used a specific artefact from this repo. They connect. The intake form feeds the risk register; the dependency map gates the assessment; the model card becomes evidence; the cadence catches drift.

2. **Data governance is the foundation.** The single most consequential moment was Stage 2 — remediating data governance before assessing risk. Without it, the bias audit would have been impossible, and the drift would have gone undetected. This is the repo's central thesis, proven end-to-end.

3. **Governance enabled deployment; it didn't block it.** The model shipped. The framework did not stop the business — it made the business defensible. The bias was found and fixed *before* it harmed anyone or triggered a regulator. That is what good governance does.

4. **The runway was used well.** With the high-risk deadline at December 2027, NorthBank had time to do this properly rather than scrambling. The Omnibus delay was runway, not reprieve — and this is what using it looks like.

---

## Try It Yourself

To run your own AI system through this framework:
1. Start with the [`intake-form.md`](../6_templates/intake-form.md).
2. If data governance gaps surface, run the [`data-governance-baseline.md`](../3_scorecards/data-governance-baseline.md) and remediate before proceeding.
3. Work through risk assessment, controls, documentation, evidence, and monitoring using the linked artefacts.
4. The [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md) tells you what to produce at each stage and who owns it.
