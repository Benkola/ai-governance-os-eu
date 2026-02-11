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

| Article | Obligation | Control | Evidence | Owner | Cadence | Data Governance Dependency |
|---|---|---|---|---|---|---|
| Art 10.2(a) | Training, validation, and testing data must be subject to appropriate data governance and management practices — including design choices for data collection | Document design choices for data collection: what data is collected, from which sources, why those sources were chosen, and what alternatives were considered. Record sampling strategy and any exclusion criteria. | Data collection design document specifying sources, rationale, sampling approach, and exclusion criteria | Data Owner + Technical Lead | Per use case at data collection stage. Update when data sources change. | Data catalogued (all data sources registered and discoverable). Data lineage documented (provenance of each dataset recorded). |
| Art 10.2(b), 10.2(c) | Data preparation and processing must be documented, including annotation, labelling, cleaning, and enrichment | Define and document all data preparation steps: cleaning rules, labelling methodology (including annotator guidelines and qualifications), enrichment processes, and transformation logic. Make the pipeline reproducible. | Data preparation log documenting each processing step, tools used, transformation rules applied, and labelling methodology. Annotator guidelines if human labelling is involved. | Data Owner + Technical Lead | Per use case at data preparation stage. Update when pipeline changes. | Data quality measurement (quality checks at each preparation step). Data lineage documented (full transformation chain from raw to processed). |
| Art 10.2(f) | Examine training data for possible biases that may affect health, safety, or lead to discrimination | Conduct a bias assessment on training data before model training. Assess representation across protected characteristics (age, gender, ethnicity, disability) relevant to the system's domain. Document findings and any corrective actions. | Bias assessment report documenting: characteristics assessed, methodology used, findings (including under/over-representation), and corrective actions taken (resampling, augmentation, exclusion). | Data Owner + AI Governance Lead | Per use case before initial training. Repeat before any retraining with new data. | Training data profiled (demographic and characteristic distributions analysed). Data quality measurement (completeness and accuracy of demographic attributes). |
| Art 10.2(g) | Identify relevant data gaps or shortcomings and how to address them | Assess whether training data adequately covers the intended operating conditions and population. Identify gaps in coverage, edge cases, or underrepresented scenarios. Document how gaps are addressed (additional data collection, synthetic augmentation, or acknowledged as a limitation). | Data gap analysis report documenting: coverage assessment against intended use, identified gaps, actions taken to address gaps, and residual gaps communicated as system limitations. | Data Owner + Technical Lead | Per use case before initial training. Reassess when intended use scope changes. | Data catalogued (to identify what data is available vs. what is needed). Training data profiled (to identify distributional gaps). |
| Art 10.3 | Training, validation, and testing datasets must be relevant, sufficiently representative, and to the best extent possible free of errors and complete | Define data quality criteria for each dataset: relevance to intended purpose, representativeness of the target population, error rate thresholds, and completeness targets. Measure datasets against these criteria before use. | Data quality assessment report documenting: defined quality criteria, measurement results for each criterion, pass/fail determination, and remediation actions for any criterion that failed. | Data Owner | Per use case before training. Repeat before retraining. Continuous monitoring of live data quality post-deployment. | Data quality measurement (defined metrics for accuracy, completeness, consistency, timeliness, validity, uniqueness). Data catalogued (datasets registered with quality metadata). |
| Art 10.5 | Where strictly necessary for bias monitoring, detection, and correction, providers may process special categories of personal data subject to safeguards | If bias detection requires processing of special category data (ethnicity, health, religion, etc.), document the legal basis, necessity assessment, and safeguards applied. Ensure GDPR Article 9 conditions are met. Limit processing to what is strictly necessary. | Necessity assessment for special category data processing. GDPR Article 9 legal basis documentation. Safeguards register (pseudonymisation, access controls, retention limits, purpose limitation). | Data Owner + DPO/Legal | Per use case where special category data is processed. Review annually. | Data classification (special category data identified and tagged). Data catalogued (processing purposes and legal basis recorded per dataset). |

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
