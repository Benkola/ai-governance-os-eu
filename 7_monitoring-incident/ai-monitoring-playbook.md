# AI Monitoring Playbook

> **Purpose:** Defines how a deployed AI system is monitored in production — what to track, how often, what thresholds trigger action, and who responds. Monitoring is not an afterthought to governance; it is continuous compliance. The EU AI Act Article 15 requires that high-risk systems maintain appropriate accuracy, robustness, and cybersecurity *throughout their lifecycle*, and Article 72 requires post-market monitoring. This playbook operationalises both.
>
> **When to use:** For any AI system in production. Scale the intensity to the risk tier — high-risk systems need the full playbook; limited-risk systems need a proportionate subset.
>
> **Owner:** ML Engineering Lead runs technical monitoring; Data Steward runs data monitoring; AI System Owner is accountable; AI Governance Lead reviews.
>
> **Relationship to other artefacts:** This playbook consumes thresholds from the model card (Section 4 metrics), feeds alerts into the incident response playbook, and reports into the governance cadence.

---

## 1. Why Monitoring Is Continuous Compliance

An AI system that passed its pre-deployment assessment is not permanently compliant. Models degrade. Data drifts. The world the model was trained on stops matching the world it operates in. A credit model trained before an interest-rate shock, a fraud model trained before a new fraud pattern emerged, a demand model trained before a supply shock — all were compliant at deployment and none are compliant now, because their accuracy has silently decayed.

The regulatory point: under Article 15, a high-risk system that no longer meets its declared accuracy is no longer compliant, regardless of how rigorous its launch was. Monitoring is how you know. Without it, you are not "probably fine" — you are non-compliant and unaware.

---

## 2. What to Monitor: The Four Signal Categories

### Category A — Model Performance

| Signal | What it measures | Example metrics |
|--------|------------------|-----------------|
| **Accuracy** | Is the model still correct? | Precision, recall, F1, AUC, MAE/RMSE (regression) |
| **Calibration** | Do predicted probabilities match reality? | Calibration curve, Brier score |
| **Stability** | Is performance consistent over time? | Rolling accuracy, variance across time windows |

### Category B — Data Quality and Drift

| Signal | What it measures | Example metrics |
|--------|------------------|-----------------|
| **Input data quality** | Is incoming data complete and valid? | Completeness %, null rate, schema conformance |
| **Data drift** | Has the input distribution shifted? | Population Stability Index (PSI), KL divergence, KS test |
| **Concept drift** | Has the relationship between inputs and target changed? | Performance decay on recent labelled data |

### Category C — Fairness and Bias

| Signal | What it measures | Example metrics |
|--------|------------------|-----------------|
| **Group fairness** | Are outcomes equitable across groups? | Demographic parity ratio, equal opportunity difference |
| **Drift in fairness** | Is the model becoming less fair over time? | Fairness metrics tracked over rolling windows |

### Category D — Operational and Oversight

| Signal | What it measures | Example metrics |
|--------|------------------|-----------------|
| **System health** | Is the system available and responsive? | Uptime, latency, error rate |
| **Human oversight effectiveness** | Is oversight functioning, not rubber-stamping? | Override rate, review time, escalation rate |
| **Volume and usage** | Is the system used as intended? | Prediction volume, usage pattern anomalies |

---

## 3. Understanding Drift (The Core Monitoring Concept)

Three distinct failures degrade a model. Monitoring must distinguish them, because each has a different fix.

| Type | What happens | Example | Detection | Fix |
|------|--------------|---------|-----------|-----|
| **Data drift** | Input distribution shifts; the model sees inputs unlike its training data | Average transaction size rises after a pricing change | Compare live input distributions to training baseline (PSI, KS test) | Retrain on recent data, or investigate the data source |
| **Concept drift** | The relationship between inputs and outcome changes | A new fraud technique makes previously-safe patterns risky | Performance decay on recently labelled data | Retrain with new labels; may need new features |
| **Performance degradation** | Accuracy drops for any reason | Model precision falls from 92% to 78% | Direct accuracy monitoring against threshold | Diagnose (data? concept? pipeline?) then remediate |

**The diagnostic value of monitoring both data and performance:** if performance drops but input data looks stable, it's concept drift (the world changed). If input data shifts, it's data drift (your pipeline or population changed). This distinction — impossible without monitoring both signals — is why the data governance dependency map lists both data quality measurement AND performance monitoring as prerequisites.

---

## 4. Monitoring Frequency

| Signal category | Frequency | Rationale |
|-----------------|-----------|-----------|
| System health (uptime, latency, errors) | Real-time / continuous | Operational failures need immediate response |
| Input data quality | Continuous (per batch or per prediction) | Bad data must be caught before it reaches the model |
| Data drift | Daily or weekly | Distributions shift gradually; daily catches it early enough |
| Model performance | Continuous where labels are immediate; otherwise as labels arrive | Fraud labels lag; credit default labels lag months |
| Fairness metrics | Monthly minimum (weekly for high-sensitivity) | Fairness drift is slower but consequential |
| Human oversight metrics | Monthly | Behavioural patterns need a window to be meaningful |

---

## 5. Alerting Thresholds

Every monitored signal needs a threshold that converts a number into an action. Thresholds come from the model card's declared metrics.

| Threshold type | Definition | Example | Action on breach |
|----------------|-----------|---------|------------------|
| **Warning** | Signal is degrading but within acceptable bounds | Precision drops from 92% to 88% (threshold 85%) | Log, monitor closely, no escalation |
| **Action** | Signal breaches the declared threshold | Precision drops below 85% | Alert owner, investigate within 48h |
| **Critical** | Signal breaches by a wide margin or a fairness/safety threshold is crossed | Demographic parity ratio drops below 0.80 | Immediate escalation, consider pausing the system |

**Threshold design principles:**
- Set the Warning band above the Action threshold so you get early notice, not surprise failure.
- Fairness and safety thresholds are Critical by default — a fairness breach is never "monitor and see."
- Thresholds are governance decisions, documented and signed off, not arbitrary engineering choices. They belong in the model card and the risk register.

---

## 6. Escalation Paths

When a threshold breaches, the response follows the governance cadence escalation triggers:

```
Signal breaches Action threshold
    │
    ▼
Alert to AI System Owner + ML Engineering Lead
    │
    ├─► Investigate root cause (data / concept / pipeline)
    │
    ▼
Is it a Critical breach (fairness, safety, wide margin)?
    │
    ├─ No ──► Remediate within defined SLA; log in risk register; report at next Tier 2
    │
    └─ Yes ─► Escalate to Tier 2 immediately
                    │
                    ▼
              Consider: pause system? notify regulator? (→ incident response playbook)
                    │
                    ▼
              Tier 1 informed within 48h if system paused or serious incident
```

---

## 7. Dashboard Requirements

A monitoring dashboard makes the signals visible and actionable. Minimum requirements:

| Requirement | Detail |
|-------------|--------|
| **Single view per system** | One dashboard per AI system showing all four signal categories |
| **Traffic-light status** | Green / amber / red against thresholds, at a glance |
| **Trend, not just snapshot** | Rolling time-series so degradation is visible before breach |
| **Per-group fairness view** | Fairness metrics broken down by relevant groups, not just aggregate |
| **Alert history** | Log of threshold breaches, when, and how resolved |
| **Drill-down** | From an alert to the underlying data (supported by lineage) |
| **Owner visibility** | Accessible to AI System Owner, ML Eng, Data Steward, and AI Governance Lead |

The dashboard is not the governance — it is the instrument panel. The governance is the cadence of people looking at it and acting.

---

## 8. Monitoring by Risk Tier (Proportionality)

| Signal | High-Risk | Limited-Risk | Minimal-Risk |
|--------|-----------|--------------|--------------|
| System health | Required | Required | Recommended |
| Input data quality | Required (continuous) | Required (periodic) | Optional |
| Data drift | Required | Recommended | Optional |
| Model performance | Required (continuous) | Required (periodic) | Optional |
| Fairness metrics | Required (monthly+) | If affects persons | Not required |
| Human oversight metrics | Required | If oversight is a control | Not required |
| Dashboard | Required | Recommended | Optional |

---

## 9. Monitoring Setup Checklist

For each AI system entering production:

- [ ] Thresholds defined for every monitored signal (from model card)
- [ ] Baseline established (training-time distributions for drift comparison)
- [ ] Data quality monitoring on input features (Data Steward)
- [ ] Performance monitoring configured (ML Engineering)
- [ ] Fairness monitoring configured if system affects persons
- [ ] Human oversight metrics instrumented if oversight is a control
- [ ] Dashboard built with traffic-light status and trends
- [ ] Alert routing configured (who gets notified on each threshold)
- [ ] Escalation path documented and agreed
- [ ] Monitoring cadence added to the governance calendar
- [ ] Link established from alerts to the incident response playbook
