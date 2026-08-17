# Model Card Template

> **Purpose:** A model card is the "nutrition label" of an AI model — a standardised document that discloses what a model is, what it's for, how it performs, and where it should not be used. This template is aligned to the Mitchell et al. (2019) model card framework and extended to satisfy EU AI Act transparency (Article 13) and technical documentation (Article 11, Annex IV) requirements.
>
> **When to use:** Produce a model card for every AI model before deployment. Update it whenever the model is retrained, its intended use changes, or its performance is re-evaluated.
>
> **Owner:** ML Engineering Lead produces it; AI System Owner is accountable; AI Governance Lead reviews for completeness.
>
> **How to fill it in:** Replace every _italic prompt_ with real content. If a section genuinely does not apply, write "Not applicable" and say why — never leave it blank, because a blank section reads as an omission to an auditor.

---

## 1. Model Details

| Field | Detail |
|-------|--------|
| **Model name** | _Name and internal identifier_ |
| **Model version** | _Semantic version (e.g., 2.3.1) and release date_ |
| **Model type** | _e.g., gradient-boosted trees, logistic regression, transformer, CNN_ |
| **Model owner** | _AI System Owner — name and role_ |
| **Developed by** | _Internal team or external vendor_ |
| **Model date** | _Date this version was trained_ |
| **License** | _If applicable (internal, open-source model base, vendor license)_ |
| **Contact** | _Who to contact with questions about this model_ |
| **Related documentation** | _Links to system card, risk register entry, evidence pack, DPIA_ |

**Model description (2–3 sentences):**

_Plain-language description of what the model does. Written so a non-technical stakeholder (compliance officer, business sponsor) can understand it._

**Regulatory classification:**

| Field | Detail |
|-------|--------|
| **EU AI Act risk tier** | _Prohibited / High-risk / Limited / Minimal_ |
| **Annex III category** (if high-risk) | _Which category, e.g., "access to essential services — credit scoring"_ |
| **Operator role** | _Provider / Deployer / Both_ |

---

## 2. Intended Use

| Field | Detail |
|-------|--------|
| **Primary intended use** | _The specific task this model is designed for_ |
| **Primary intended users** | _Who uses the model's output (e.g., credit officers, fraud analysts, end customers)_ |
| **Out-of-scope uses** | _Uses this model is NOT designed for and must not be used for. Be explicit — this is where liability is managed._ |

**Decision context:**

| Question | Answer |
|----------|--------|
| Does the output inform decisions about natural persons? | _Yes / No — if yes, what decisions_ |
| Is the output a recommendation or an automated decision? | _Recommendation (human decides) / Automated (system decides)_ |
| Can a human override the output? | _Yes / No — describe the override mechanism_ |
| What is the consequence of an incorrect output? | _Describe the harm from false positives and false negatives separately_ |

---

## 3. Factors

_Factors are the variables that influence model performance. Documenting them is required to understand where the model works well and where it may fail._

| Factor type | Description |
|-------------|-------------|
| **Relevant groups** | _Demographic or population groups the model's performance may vary across (e.g., age bands, regions). For high-risk systems, this must include protected characteristics where lawful and relevant to bias assessment._ |
| **Instrumentation** | _Data collection conditions that affect performance (e.g., data source, sensor type, time period)_ |
| **Environment** | _Deployment conditions that affect performance (e.g., real-time vs batch, data freshness, geography)_ |
| **Evaluation factors** | _Which of the above were actually tested during evaluation (and which were not — state the gap)_ |

---

## 4. Metrics

_The measures used to evaluate the model, and why they were chosen. Metric choice is a governance decision, not just a technical one — the metric encodes what "good" means._

| Metric | Value | Why this metric | Threshold / target |
|--------|-------|-----------------|--------------------|
| _e.g., Precision_ | _0.92_ | _False positives are costly (block legitimate customers)_ | _> 0.90_ |
| _e.g., Recall_ | _0.87_ | _False negatives let fraud through_ | _> 0.85_ |
| _e.g., F1 score_ | _0.89_ | _Balances precision and recall_ | _> 0.85_ |
| _e.g., AUC-ROC_ | _0.94_ | _Overall discrimination ability_ | _> 0.90_ |

**Decision threshold:**

_The threshold at which the model's score converts to a decision, and the rationale. E.g., "A fraud probability above 0.7 triggers a manual review; this threshold was chosen to keep the manual review queue manageable while catching 87% of fraud."_

**Fairness metrics (required for high-risk systems):**

| Fairness metric | Value | Acceptable range |
|-----------------|-------|------------------|
| _e.g., Demographic parity ratio_ | _0.91_ | _> 0.80_ |
| _e.g., Equal opportunity difference_ | _0.03_ | _< 0.10_ |

**Variation across factors:**

_How performance varies across the relevant groups identified in Section 3. This is where bias becomes visible. Present per-group metrics, not just aggregate. If performance is materially worse for any group, document it and reference the mitigation in the risk register._

---

## 5. Evaluation Data

| Field | Detail |
|-------|--------|
| **Datasets used for evaluation** | _Name and source of the test/validation data_ |
| **Why this data** | _Why this evaluation data is representative of the deployment context_ |
| **Preprocessing** | _How evaluation data was prepared_ |
| **Evaluation data size** | _Number of records; class balance if classification_ |
| **Data lineage reference** | _Link to lineage documentation (maintained by Data Steward)_ |
| **Known gaps** | _Ways the evaluation data does NOT represent the deployment context (e.g., "test data is from 2024; deployment population may have shifted")_ |

---

## 6. Training Data

_EU AI Act Article 10 requires documentation of training data governance. This section satisfies part of that obligation._

| Field | Detail |
|-------|--------|
| **Training datasets** | _Name and source_ |
| **Data collection period** | _Time range the training data covers_ |
| **Data owner** | _Who is accountable for this data (from intake form Section 4)_ |
| **Data quality assessment** | _Quality dimensions measured and results (completeness, accuracy, timeliness). Reference Data Steward's quality metrics._ |
| **Data lineage** | _Reference to lineage documentation from source to training set_ |
| **Labelling methodology** | _How labels/targets were created; inter-annotator agreement if human-labelled_ |
| **Known biases in training data** | _Documented biases and their potential impact (Article 10.2f bias examination)_ |
| **Special category data** | _Whether the training data includes special category data (GDPR Art 9); if so, the lawful basis and safeguards_ |
| **Data gaps** | _Underrepresented segments identified (Article 10.2g)_ |

---

## 7. Ethical Considerations

_Required for EU AI Act high-risk systems and good practice for all._

| Consideration | Detail |
|---------------|--------|
| **Affected fundamental rights** | _Which rights could be affected (privacy, non-discrimination, dignity, effective remedy)_ |
| **Potential harms** | _Realistic harms from model use or misuse, per affected group_ |
| **Sensitive use** | _Whether the model is used in a sensitive domain (finance, health, employment, justice)_ |
| **Human oversight** | _How humans oversee the model (reference Article 14 design in the system card)_ |
| **Mitigations** | _What has been done to reduce identified harms; reference risk register entries_ |

---

## 8. Caveats and Recommendations

| Field | Detail |
|-------|--------|
| **Known limitations** | _What the model cannot do well; failure modes_ |
| **Conditions for reliable use** | _The conditions under which the model performs as documented (e.g., "requires data quality above threshold X")_ |
| **When to retrain** | _Triggers for retraining (performance below threshold, data drift, population change)_ |
| **When NOT to use** | _Conditions under which the model output should not be trusted or used_ |
| **Recommendations for deployers** | _Guidance for anyone deploying this model (satisfies Article 13 deployer instructions)_ |

---

## 9. EU AI Act Compliance Notes

_This section cross-references the model card to specific AI Act obligations, making it directly usable as evidence pack material._

| AI Act Requirement | Where addressed in this card | Evidence reference |
|--------------------|------------------------------|--------------------|
| **Art 11 / Annex IV — Technical documentation** | Sections 1, 5, 6 | _Link to full Annex IV doc_ |
| **Art 10 — Data governance** | Section 6 | _Link to data governance records_ |
| **Art 13 — Transparency to deployers** | Sections 2, 8 | _Link to deployer instructions_ |
| **Art 15 — Accuracy, robustness** | Section 4 | _Link to monitoring dashboard_ |
| **Art 9 — Risk management** | Sections 7, 8 | _Link to risk register entries_ |
| **Art 14 — Human oversight** | Sections 2, 7 | _Link to system card oversight design_ |

**Conformity status:**

| Field | Detail |
|-------|--------|
| **Conformity assessment completed?** | _Yes / No / In progress_ |
| **EU database registration** (if high-risk) | _Registration reference or "pending"_ |
| **Last governance review** | _Date and reviewer_ |
| **Next scheduled review** | _Date_ |

---

## Model Card Metadata

| Field | Detail |
|-------|--------|
| **Card version** | _Version of this card_ |
| **Card author** | _Who wrote it_ |
| **Card date** | _When written/updated_ |
| **Reviewed by** | _AI Governance Lead sign-off_ |
| **Review date** | _Date_ |
