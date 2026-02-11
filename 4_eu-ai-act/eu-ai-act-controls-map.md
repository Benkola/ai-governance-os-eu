# EU AI Act Controls Map (High-Risk AI Systems)

> Translates EU AI Act obligations (Articles 9–15) into implementable controls for SMEs.
> Each row maps: obligation → control → evidence → owner → cadence → data governance dependency.

## How to use this controls map

1. Determine whether your AI system is classified as high-risk (see the high-risk requirements checklist).
2. For each applicable obligation below, implement the control described.
3. Produce the evidence listed and store it in the system's evidence pack.
4. Assign the owner within your organisation (adapt generic roles to your team structure).
5. Set the review cadence in your governance calendar and ensure reviews are completed on schedule.

This controls map covers provider and deployer obligations for high-risk AI systems under the EU AI Act. It does not cover general-purpose AI models (Article 53+) or prohibited practices (Article 5).

---

## Article 9 — Risk Management System

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| Art 9.1 | Establish a risk management system that operates continuously throughout the AI system's entire lifecycle | Define and document a risk management process covering identification, assessment, mitigation, monitoring, and review. Assign process ownership and integrate into the organisation's broader risk framework. | Risk management policy document specifying process steps, roles, escalation paths, and lifecycle integration points | AI Governance Lead | Annually (policy review) + at each lifecycle stage transition | None |
| Art 9.2(a), 9.2(b) | Identify and analyse known and reasonably foreseeable risks to health, safety, and fundamental rights — from both intended use and reasonably foreseeable misuse | Conduct a structured risk assessment for each AI use case at intake. Document identified risks with likelihood, severity, and affected population. Assess risks arising from intended use and from plausible misuse scenarios. | Completed risk assessment form with risk register entries. Each entry includes: risk description, likelihood rating, severity rating, affected rights/safety areas, and whether the risk arises from intended use or foreseeable misuse. | AI Governance Lead + System Owner | Per use case at intake. Reassess annually or when the system is materially changed. | Training data profiled (to identify data-related risks such as bias, gaps in representativeness, or poor quality inputs) |
| Art 9.2(c) | Evaluate risks that emerge after deployment based on post-market monitoring data | Establish a post-deployment risk review process. Analyse monitoring data, incident reports, user feedback, and performance drift to identify new or evolving risks not captured at intake. Update the risk register accordingly. | Updated risk register entries with post-deployment findings. Post-market monitoring review report documenting data sources analysed, new risks identified, and actions taken. | AI Governance Lead + Monitoring Lead | Quarterly post-deployment (minimum). Triggered additionally by incidents or significant performance changes. | Data quality measurement (monitoring data must be reliable). Data lineage documented (to trace issues back to root cause). |
| Art 9.2(d), 9.3 | Adopt appropriate risk management measures — prioritising elimination by design, then mitigation, then informing deployers of residual risk | For each identified risk, select and implement a risk management measure. Prioritise: (1) eliminate the risk through system redesign, (2) mitigate through technical or procedural controls, (3) accept the residual risk and document rationale. Test measures to confirm effectiveness. | Risk treatment plan documenting: each risk, the selected measure, rationale for the approach chosen (eliminate/mitigate/accept), and test results confirming effectiveness. Sign-off from risk owner. | AI Governance Lead + Technical Lead | Per use case (at risk assessment stage). Review when risk register is updated. | None |
| Art 9.4 | Test the AI system before placing on market or putting into service, using predefined metrics and probabilistic thresholds | Define testing criteria (accuracy, fairness, robustness metrics) with quantitative thresholds before testing begins. Execute tests against these criteria. Document pass/fail results. Do not deploy systems that fail defined thresholds without documented exception and additional mitigation. | Test plan with predefined metrics and thresholds. Test execution report with results. Pass/fail determination. Exception documentation if deployed despite a threshold breach (including additional mitigations applied). | Technical Lead + AI Governance Lead | Per use case before initial deployment. Repeat before any major system update or retraining. | Training data profiled (test validity depends on understanding data distribution). Data quality measurement (unreliable test data produces unreliable results). |
| Art 9.5 | Communicate residual risks to deployers with clear information on remaining limitations and risks | Produce a residual risk summary for each high-risk AI system. Include: risks that remain after mitigation, conditions under which residual risks may materialise, and recommended actions for the deployer. Deliver to deployer before or at deployment. | Residual risk communication document provided to deployer. Delivery confirmation (email, signed receipt, or equivalent). | AI Governance Lead | Per use case at deployment. Update when the risk register changes materially. | None |

---

## Article 10 — Data and Data Governance

> *To be completed*

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## Article 11 — Technical Documentation

> *To be completed*

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## Article 12 — Record-Keeping

> *To be completed*

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## Article 13 — Transparency and Provision of Information to Deployers

> *To be completed*

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## Article 14 — Human Oversight

> *To be completed*

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## Article 15 — Accuracy, Robustness and Cybersecurity

> *To be completed*

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| | | | | | | |

---

## Limitations

This controls map is designed for SMEs deploying or procuring high-risk AI systems. It does not cover:

- Provider-side conformity assessment procedures (Annex VI / VII)
- General-purpose AI model obligations (Article 53+)
- Prohibited AI practices (Article 5)
- Sector-specific obligations (e.g. medical device regulation, financial services prudential requirements)

Controls should be adapted to the organisation's size, risk appetite, and regulatory context. This map provides a starting structure, not a definitive compliance programme.
