# Data Governance Baseline Assessment

> **Purpose:** A fast, 10-question assessment to establish whether the data governance foundations required for AI governance are in place. Designed to be completed in 15 minutes by a data leader, compliance officer, or AI governance lead.
>
> **Why this exists:** Before investing in AI governance tooling and processes, you need to know if the data foundations can support them. This scorecard surfaces the gaps that will block EU AI Act Article 10 compliance. It's the pre-flight check before the AI governance programme takes off.
>
> **How to use:** Answer each question honestly. Score as indicated. Total your score and read the interpretation. Use the gap actions to build your remediation plan.

---

## How to Score

Each question is scored 0, 1, 2, or 3:

- **0 — Not in place:** This capability does not exist.
- **1 — Ad hoc:** Exists informally or for some data, but inconsistent and undocumented.
- **2 — Defined:** Exists consistently, documented, applied to AI-relevant data.
- **3 — Managed:** Exists, measured, monitored, and continuously maintained.

**Maximum score: 30.**

---

## The 10 Questions

### Q1. Data Ownership

**Do you have designated data owners with decision-making authority over your AI-relevant datasets?**

| Score | Criteria |
|-------|----------|
| 0 | No data owners. Nobody is accountable for data quality or use decisions. |
| 1 | Some owners informally recognised for critical datasets, not documented. |
| 2 | Data owners formally assigned and documented for all AI-relevant datasets. |
| 3 | Data owners actively manage their domains; accountability tracked and reported. |

**Your score: _____**

*Why it matters:* AI Act Article 10 and intake form Section 4 require a data owner per dataset. Without ownership, there's no accountability for data quality decisions, and risk assessments have no authority to rely on.

---

### Q2. Data Quality Measurement

**Do you measure data quality for the datasets used by your AI systems?**

| Score | Criteria |
|-------|----------|
| 0 | Data quality is not measured. |
| 1 | Quality checked manually before major releases, no defined dimensions. |
| 2 | Quality dimensions and thresholds defined; measured before data reaches models. |
| 3 | Continuous automated quality monitoring tied to model performance. |

**Your score: _____**

*Why it matters:* This is the single most important data governance capability for AI. The dependency map shows 10 of 14 AI Act governance activities depend on it. You cannot assess, test, or monitor AI systems credibly without it.

---

### Q3. Data Catalogue

**Do you have a data catalogue where your AI-relevant datasets are registered and discoverable?**

| Score | Criteria |
|-------|----------|
| 0 | No catalogue. Data discovery relies on tribal knowledge. |
| 1 | Spreadsheet-based or partial catalogue, incomplete, not maintained. |
| 2 | Catalogue tool deployed; AI datasets registered with metadata standards. |
| 3 | Catalogue actively used enterprise-wide with AI-specific metadata. |

**Your score: _____**

*Why it matters:* You cannot govern what you cannot find. The catalogue is the inventory that makes everything else possible — risk assessment, lineage, quality monitoring, and regulatory evidence.

---

### Q4. Data Classification

**Is your data classified by sensitivity, including identification of personal and special category data?**

| Score | Criteria |
|-------|----------|
| 0 | No classification scheme. |
| 1 | Basic labels (public/internal/confidential) applied inconsistently. |
| 2 | Classification applied to AI datasets, including PII and special category (GDPR Art 9). |
| 3 | Automated classification with policy enforcement integrated into workflows. |

**Your score: _____**

*Why it matters:* AI Act Article 10.5 and GDPR Article 9 impose specific requirements on special category data. You cannot comply if you don't know which datasets contain it.

---

### Q5. Data Lineage

**Can you trace data from its source to your AI system's input, including all transformations?**

| Score | Criteria |
|-------|----------|
| 0 | No lineage documentation. |
| 1 | Manual lineage docs for some datasets, quickly outdated. |
| 2 | Lineage documented for AI training pipelines, sufficient for Annex IV. |
| 3 | Automated end-to-end lineage used for impact analysis and incident investigation. |

**Your score: _____**

*Why it matters:* Lineage appears in 9 of 14 AI governance activities. It's required for Annex IV documentation, incident root-cause analysis, and detecting data poisoning. Without it, you can't diagnose why a model degraded.

---

### Q6. Data Stewardship

**Do you have data stewards responsible for day-to-day data quality, lineage, and standards compliance?**

| Score | Criteria |
|-------|----------|
| 0 | No stewardship function. |
| 1 | Some individuals informally do stewardship work, not a defined role. |
| 2 | Data Stewards assigned for AI-relevant data domains with documented responsibilities. |
| 3 | Stewardship integrated into AI governance workflows (intake, evidence, monitoring). |

**Your score: _____**

*Why it matters:* The Data Owner sets policy; the Data Steward executes it. Without stewards, data governance is policy on paper. Stewards are the operational interface between data governance and AI governance.

---

### Q7. Data Quality Remediation

**When data quality issues are found, is there a defined process to remediate them before they affect AI systems?**

| Score | Criteria |
|-------|----------|
| 0 | No remediation process; issues reach models unaddressed. |
| 1 | Issues fixed reactively when someone notices a problem. |
| 2 | Defined remediation process triggered by quality threshold breaches. |
| 3 | Automated remediation for known issues; remediation effectiveness tracked. |

**Your score: _____**

*Why it matters:* Measuring quality is necessary but insufficient. If you detect a quality issue but have no process to fix it before model training, the measurement is just documentation of a problem you're about to ship.

---

### Q8. Metadata Standards

**Do you have defined metadata standards that your AI datasets conform to?**

| Score | Criteria |
|-------|----------|
| 0 | No metadata standards. |
| 1 | Inconsistent metadata captured ad hoc. |
| 2 | Metadata standards defined; AI datasets conform (source, schema, refresh, sensitivity, ownership). |
| 3 | Standards enforced and maintained; AI-specific metadata (intended use, training splits, limitations) captured. |

**Your score: _____**

*Why it matters:* Consistent metadata is what makes a catalogue useful and lineage traceable. Without standards, every dataset is documented differently and automation becomes impossible.

---

### Q9. Data Access Governance

**Is access to AI-relevant data governed, with access aligned to data classification?**

| Score | Criteria |
|-------|----------|
| 0 | No access governance; data access is uncontrolled or IT-managed without policy. |
| 1 | Some access controls exist but not aligned to classification or use case. |
| 2 | Access governed and aligned to classification; access to special category data restricted. |
| 3 | Access continuously monitored; least-privilege enforced; access reviewed on cadence. |

**Your score: _____**

*Why it matters:* AI training often requires broad data access, which creates risk. Governed access aligned to classification is required for GDPR compliance and reduces the attack surface for data poisoning.

---

### Q10. Data Governance Integration with AI Governance

**Is your data governance connected to your AI governance — do they reference each other operationally?**

| Score | Criteria |
|-------|----------|
| 0 | Data governance and AI governance operate in complete isolation (or AI governance doesn't exist). |
| 1 | Some informal coordination but no defined integration points. |
| 2 | Defined integration: intake form checks data readiness, stewards support evidence packs. |
| 3 | Fully integrated: data governance feeds AI risk register, monitoring, and evidence continuously. |

**Your score: _____**

*Why it matters:* This is the capstone question. The other nine can all be strong, but if data governance and AI governance don't talk to each other, the AI Act's data requirements still won't be met. Integration is what turns two disciplines into one operating system.

---

## Your Total Score

**Total: _____ / 30**

---

## Interpretation

| Score | Rating | What It Means | Priority Action |
|-------|--------|---------------|-----------------|
| **0–9** | **Critical Gap** | Data foundations cannot support AI governance. EU AI Act Article 10 compliance is not achievable in current state. | Stop AI governance tooling investment. Build data governance basics first: assign owners (Q1), start measuring quality (Q2), deploy a catalogue (Q3). |
| **10–17** | **Developing** | Some foundations exist but significant gaps remain. AI governance possible for a small portfolio with heavy manual effort. | Prioritise the lowest-scoring of Q2 (quality), Q5 (lineage), Q6 (stewardship). These gate the most AI governance activities. |
| **18–24** | **Defined** | Solid data governance foundations. AI Act Article 10 compliance is achievable. | Move toward measurement and monitoring. Strengthen integration (Q10). Automate where high-volume. |
| **25–30** | **Managed** | Strong data governance. AI governance can scale on this foundation. | Focus on optimisation and the AI governance pillars. Your data foundation is an asset, not a constraint. |

---

## Gap Action Planner

For each question scored 0 or 1, record the action:

| Question | Current Score | Target Score | Action Required | Owner | Target Date |
|----------|--------------|--------------|-----------------|-------|-------------|
| Q1 — Data Ownership | | | | | |
| Q2 — Data Quality Measurement | | | | | |
| Q3 — Data Catalogue | | | | | |
| Q4 — Data Classification | | | | | |
| Q5 — Data Lineage | | | | | |
| Q6 — Data Stewardship | | | | | |
| Q7 — Quality Remediation | | | | | |
| Q8 — Metadata Standards | | | | | |
| Q9 — Access Governance | | | | | |
| Q10 — Integration | | | | | |

---

## Recommended Sequence for Closing Gaps

If you're starting low, don't try to fix everything at once. This sequence reflects dependencies:

1. **First: Q1 (Ownership) + Q3 (Catalogue).** You need to know what data you have and who's accountable for it before anything else works.
2. **Second: Q2 (Quality) + Q8 (Metadata Standards).** Once you know what you have, start measuring its quality and standardising how you describe it.
3. **Third: Q5 (Lineage) + Q4 (Classification).** With catalogue and standards in place, document where data flows and how sensitive it is.
4. **Fourth: Q6 (Stewardship) + Q7 (Remediation).** Assign the people and processes to maintain quality continuously.
5. **Fifth: Q9 (Access) + Q10 (Integration).** Govern access and connect data governance to AI governance as an operating system.

This sequence builds foundations before structures. Trying to do lineage (Q5) before cataloguing (Q3) is like mapping roads before you know which towns exist.
