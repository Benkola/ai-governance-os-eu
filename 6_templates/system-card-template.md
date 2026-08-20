# System Card Template

> **Purpose:** Where a model card documents a single model, a system card documents a *compound AI system* — a pipeline or product made of multiple models, data flows, business logic, and human decision points. Most real-world AI is a system, not a model. Meta popularised the system card as a way to describe how components interact to produce a user-facing outcome.
>
> **When to use:** Produce a system card for any AI system composed of more than one model, or any single model embedded in a larger decision pipeline with pre-processing, business rules, or human review. If a model card answers "what is this model?", a system card answers "what is this thing the user actually interacts with, and how does it work end to end?"
>
> **Owner:** AI System Owner is accountable; ML Engineering Lead and Data Steward contribute; AI Governance Lead reviews.
>
> **Relationship to model cards:** A system card references one or more model cards. Each component model has its own model card; the system card ties them together and documents the connective tissue (data flows, oversight, orchestration) that no individual model card covers.

---

## 1. System Overview

| Field | Detail |
|-------|--------|
| **System name** | _Name and internal identifier_ |
| **System version** | _Version and release date_ |
| **System owner** | _AI System Owner — name and role_ |
| **Business purpose** | _What business outcome this system delivers_ |
| **Primary users** | _Who interacts with the system_ |
| **Go-live date** | _When deployed / planned_ |
| **Related documentation** | _Links to component model cards, risk register, evidence pack, DPIA_ |

**System description (3–4 sentences):**

_Plain-language description of the whole system end to end. What goes in, what comes out, what happens to a user or affected person. Written for a compliance officer, not an engineer._

**Regulatory classification:**

| Field | Detail |
|-------|--------|
| **EU AI Act risk tier** | _Of the system as a whole (the highest tier of any component usually governs)_ |
| **Annex III category** (if high-risk) | _Which category_ |
| **Operator role** | _Provider / Deployer / Both_ |
| **Applicable regulations beyond AI Act** | _GDPR, DORA, DSA, MiFID II, PSD2, SOx — as applicable_ |

---

## 2. System Architecture

**Architecture description:**

_Describe the flow from input to output. A simple text diagram helps. Example:_

```
User request
    │
    ▼
[Input validation & preprocessing]
    │
    ▼
[Model A: risk scoring] ──► [Business rules engine]
    │                              │
    ▼                              ▼
[Model B: fraud check]      [Threshold logic]
    │                              │
    └──────────►[Decision aggregation]
                         │
                         ▼
              [Human review queue]  ◄── oversight point
                         │
                         ▼
                  Final decision to user
```

**Component inventory:**

| Component | Type | Purpose | Model card reference |
|-----------|------|---------|----------------------|
| _Model A_ | _ML model_ | _What it does in the pipeline_ | _Link to its model card_ |
| _Model B_ | _ML model_ | _What it does_ | _Link to its model card_ |
| _Business rules engine_ | _Deterministic logic_ | _What rules it applies_ | _N/A — document rules separately_ |
| _Preprocessing_ | _Data transformation_ | _What it transforms_ | _N/A_ |

---

## 3. Data Flows

_Documenting how data moves through the system is required for both AI Act Article 10 and GDPR data mapping. This is where the Data Steward's lineage work becomes visible at the system level._

| Data flow | Source | Destination | Data type | Sensitivity | Lineage reference |
|-----------|--------|-------------|-----------|-------------|-------------------|
| _Input data_ | _Where it comes from_ | _First component_ | _e.g., transaction records_ | _Personal / special category / non-personal_ | _Link_ |
| _Intermediate outputs_ | _Model A_ | _Model B / rules engine_ | _e.g., risk scores_ | _Derived personal data_ | _Link_ |
| _Final output_ | _Decision aggregation_ | _User / downstream system_ | _e.g., decision + reason_ | _Personal_ | _Link_ |

**Data governance summary:**

| Question | Answer |
|----------|--------|
| Is all data in the system catalogued? | _Yes / No — reference catalogue_ |
| Is data quality measured at ingestion? | _Yes / No — reference Data Steward metrics_ |
| Is end-to-end lineage documented? | _Yes / No — reference lineage docs_ |
| Is personal data minimised across the pipeline? | _Yes / No — describe_ |

---

## 4. Human Oversight Points

_EU AI Act Article 14 requires effective human oversight. In a compound system, oversight can occur at multiple points. Document each one._

| Oversight point | Where in the pipeline | Who performs it | What they can do | Effectiveness measure |
|-----------------|----------------------|-----------------|------------------|----------------------|
| _e.g., Manual review queue_ | _Before final decision_ | _Fraud analyst_ | _Approve, reject, escalate, override_ | _Time-per-review, override rate_ |
| _e.g., Threshold exception_ | _When score is borderline_ | _Senior officer_ | _Apply judgement_ | _Exception approval rate_ |

**Oversight design principles:**

| Principle (Article 14) | How the system meets it |
|------------------------|-------------------------|
| Humans can understand the system's capabilities and limitations | _How operators are informed_ |
| Humans can detect and address anomalies | _What signals alert them_ |
| Humans can avoid over-reliance ("automation bias") | _What prevents rubber-stamping_ |
| Humans can override or reverse the output | _The override mechanism_ |
| Humans can intervene or halt the system | _The stop mechanism_ |

---

## 5. Risk Assessment

_Summarise the system-level risks. Full detail lives in the risk register; this is the system card's view._

| Risk | Category | Rating | Treatment | Risk register reference |
|------|----------|--------|-----------|-------------------------|
| _e.g., Cascading error (Model A error amplified by Model B)_ | _Model performance_ | _High_ | _Mitigate_ | _R-0XX_ |
| _e.g., Data quality degradation_ | _Data quality_ | _Critical_ | _Mitigate_ | _R-0XX_ |
| _e.g., Oversight circumvention_ | _Human oversight_ | _High_ | _Mitigate_ | _R-0XX_ |

**System-specific risks (compound-system risks that no single model card captures):**

_Compound systems have emergent risks. Examples: errors in one model propagate to another; a business rule interacts unexpectedly with a model output; the aggregation logic produces an outcome no component intended. Document these here — they are the reason system cards exist._

---

## 6. Monitoring Plan

_How the system is monitored in production. References the governance cadence for review rhythms._

| What is monitored | Metric | Threshold | Frequency | Owner | Alert action |
|-------------------|--------|-----------|-----------|-------|--------------|
| _System-level accuracy_ | _e.g., end-to-end decision accuracy_ | _> X%_ | _Continuous_ | _ML Eng Lead_ | _Alert + review_ |
| _Component model performance_ | _Per model-card metrics_ | _Per card_ | _Continuous_ | _ML Eng Lead_ | _Alert + retrain assessment_ |
| _Data quality (inputs)_ | _Completeness, drift_ | _Per threshold_ | _Continuous_ | _Data Steward_ | _Alert + investigate_ |
| _Human oversight effectiveness_ | _Override rate, review time_ | _Per threshold_ | _Monthly_ | _AI System Owner_ | _Review + retrain reviewers_ |
| _Fairness_ | _Per-group outcome parity_ | _Per threshold_ | _Quarterly_ | _AI System Owner_ | _Bias review_ |

**Incident response:**

_Reference the governance cadence escalation triggers. State the severity classification for this system and who is notified._

---

## 7. EU AI Act Compliance Notes

| AI Act Requirement | Where addressed | Evidence reference |
|--------------------|-----------------|--------------------|
| **Art 11 / Annex IV — Technical documentation** | Sections 1, 2, 3 + component model cards | _Link_ |
| **Art 10 — Data governance** | Section 3 | _Link_ |
| **Art 12 — Record-keeping / logging** | Section 6 | _Link to logging design_ |
| **Art 13 — Transparency** | Sections 1, 4 | _Link to deployer/user instructions_ |
| **Art 14 — Human oversight** | Section 4 | _This section_ |
| **Art 15 — Accuracy, robustness, cybersecurity** | Section 6 | _Link to monitoring + security assessment_ |

**Conformity status:**

| Field | Detail |
|-------|--------|
| **Conformity assessment completed?** | _Yes / No / In progress_ |
| **EU database registration** (if high-risk) | _Reference or "pending"_ |
| **Last governance review** | _Date and reviewer_ |
| **Next scheduled review** | _Date_ |

---

## System Card Metadata

| Field | Detail |
|-------|--------|
| **Card version** | _Version_ |
| **Card author** | _Who wrote it_ |
| **Card date** | _When_ |
| **Component model cards referenced** | _List with links_ |
| **Reviewed by** | _AI Governance Lead sign-off_ |
| **Review date** | _Date_ |
