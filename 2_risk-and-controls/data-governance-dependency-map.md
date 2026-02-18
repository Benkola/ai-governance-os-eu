# Data Governance Dependency Map

**Purpose:** Shows which AI governance activities depend on which data governance capabilities. This is the bridge between AI governance and data governance. You cannot do the left column without the right column being in place.

**Why this matters:** Most AI governance failures are actually data governance failures. The EU AI Act's heaviest obligations (Articles 9, 10, 15) assume functioning data governance. If your data isn't catalogued, quality isn't measured, and lineage isn't documented, you cannot produce the evidence the Act requires.

**How to use:** Before starting any AI governance activity in the left column, verify that the required data governance capabilities in the right column are in place. If they're not, fix the data governance gap first.

---

## The Dependency Map

| AI Governance Activity | EU AI Act Reference | Required Data Governance Capability | DAMA DMBOK Knowledge Area | If Capability Is Missing |
|------------------------|--------------------|------------------------------------|--------------------------|--------------------------|
| **Risk identification** — Identify known and foreseeable risks to health, safety, and fundamental rights | Art 9.2(a) | **Data profiling** — Training data must be profiled (schema, distributions, completeness, class balance) to identify data-related risks (bias, gaps, representativeness) | Data Quality Management | Cannot identify data-related risks. Risk assessment will have blind spots. |
| **Risk identification** — Assess risks from foreseeable misuse | Art 9.2(b) | **Data classification** — Data sensitivity levels must be known to assess misuse risks (e.g., personal data exposure, re-identification) | Data Security, Data Governance | Cannot assess whether misuse could expose sensitive data or violate privacy. |
| **Post-deployment risk evaluation** — Evaluate risks emerging from live operation | Art 9.2(c) | **Data quality measurement** — Operational data quality must be continuously measured to detect drift, degradation, or contamination. **Data lineage** — Issues must be traceable from model output back to data source. | Data Quality Management, Metadata Management | Cannot distinguish model failure from data failure. Cannot trace root cause of performance issues. |
| **Pre-market testing** — Test with predefined metrics and probabilistic thresholds | Art 9.4 | **Data profiling** — Test data must be profiled to confirm representativeness. **Data quality measurement** — Test data quality must be verified (garbage in → garbage out applies to testing too). | Data Quality Management | Test results are unreliable. Passing a test on poor-quality data proves nothing. |
| **Data collection design** — Design choices for training, validation, and testing datasets | Art 10.2 | **Data cataloguing** — All datasets must be registered (source, schema, refresh, sensitivity). **Data lineage** — Collection provenance must be documented. | Data Governance, Metadata Management | Cannot demonstrate to regulators how data was selected, sourced, or prepared. Annex IV documentation incomplete. |
| **Data preparation and processing** — Annotation, labelling, cleaning, enrichment | Art 10.2 | **Data quality measurement** — Quality before and after processing must be measured. **Data lineage** — Every transformation must be traceable. | Data Quality Management, Data Integration & Interoperability | Cannot demonstrate data preparation was appropriate. Cannot reproduce or audit processing steps. |
| **Bias assessment** — Examine datasets for possible biases, especially regarding protected groups | Art 10.2(f) | **Data profiling** — Distributions across protected characteristics must be analysed. **Data quality measurement** — Completeness and accuracy of demographic data must be verified. | Data Quality Management, Reference & Master Data | Bias assessment is superficial or impossible. Cannot quantify representativeness. |
| **Data gap identification** — Identify gaps in training data relative to intended deployment context | Art 10.2(g) | **Data cataloguing** — Must know what data exists to identify what's missing. **Data profiling** — Must understand existing distributions to identify underrepresented segments. | Data Quality Management, Data Governance | Cannot identify what you don't know. Gaps in training data become undetected failure modes. |
| **Special category data processing** — Processing of personal data revealing racial or ethnic origin, genetic/biometric data, health, sexual orientation | Art 10.5 | **Data classification** — Special category data must be identified and tagged. **Data cataloguing** — Processing activities for special category data must be registered. | Data Security, Data Governance | Illegal processing of special category data without appropriate safeguards. GDPR Article 9 violation. |
| **Technical documentation** — Produce Annex IV documentation before market placement | Art 11 | **Data lineage** — Annex IV requires description of training methodologies and data provenance. **Data profiling** — Annex IV requires description of training data characteristics. | Metadata Management, Data Governance | Cannot complete Annex IV documentation. System cannot be placed on market. |
| **Record-keeping and logging** — Automatic logging throughout AI system lifecycle | Art 12 | **Data quality measurement** — Log data reliability must be assured. **Data lineage** — Decision reconstruction requires tracing from log entry back through data pipeline. | Data Quality Management, Metadata Management | Logs exist but are unreliable. Cannot reconstruct decisions for regulatory enquiry. |
| **Transparency documentation** — Declare accuracy, robustness, and cybersecurity in deployer instructions | Art 13, Art 15 | **Data profiling** — Accuracy declarations depend on understanding test data characteristics. **Data quality measurement** — Accuracy metrics are meaningless without data quality context. | Data Quality Management | Accuracy declarations are misleading. Deployers cannot interpret or trust performance claims. |
| **Accuracy and robustness monitoring** — Measure and maintain appropriate accuracy levels throughout lifecycle | Art 15 | **Data quality measurement** — Ongoing accuracy monitoring requires continuous data quality measurement (drift detection). **Data lineage** — Performance degradation must be traceable to data changes vs model changes. | Data Quality Management, Metadata Management | Cannot detect accuracy degradation until it causes harm. Cannot diagnose root cause. |
| **Cybersecurity** — Protect against data poisoning, model manipulation, and adversarial inputs | Art 15 | **Data lineage** — Unauthorised data changes must be detectable. **Data quality measurement** — Data poisoning detection requires baseline quality metrics. | Data Security, Data Quality Management | Cannot detect data poisoning or tampering. Security monitoring has blind spots. |

---

## Reading This Map: The Pattern

Three data governance capabilities appear repeatedly because they are foundational:

1. **Data quality measurement** — appears in 10 of 14 rows. Without measuring data quality, you cannot assess risks, test models, monitor accuracy, detect drift, or produce credible evidence packs.

2. **Data lineage** — appears in 9 of 14 rows. Without traceability from source to model output, you cannot debug failures, produce Annex IV documentation, detect security issues, or reconstruct decisions for regulators.

3. **Data cataloguing / profiling** — appears in 8 of 14 rows. Without knowing what data you have and its characteristics, you cannot identify bias, assess representativeness, find gaps, or classify sensitive data.

**The implication is clear:** If your organisation cannot answer "where does this data come from, how good is it, and what's in it?" then you cannot comply with the EU AI Act for high-risk systems. AI governance without data governance is theatre.

---

## Maturity Quick Assessment

Use this to quickly assess your organisation's readiness:

| Data Governance Capability | Level 0: Not in place | Level 1: Ad hoc | Level 2: Defined | Level 3: Managed | Level 4: Optimised |
|---------------------------|----------------------|-----------------|-----------------|------------------|-------------------|
| **Data ownership** | No data owners assigned | Some owners for critical datasets | Data owners defined for all AI-related datasets | Owners accountable with defined responsibilities | Owners driving continuous improvement |
| **Data cataloguing** | No catalogue exists | Spreadsheet-based, incomplete | Catalogue tool deployed, AI datasets registered | All AI datasets catalogued with metadata standards | Automated discovery and cataloguing |
| **Data quality measurement** | No quality measurement | Quality checked manually before major releases | Quality dimensions defined, thresholds set | Continuous automated quality monitoring | Quality SLAs with automated remediation |
| **Data lineage** | No lineage documentation | Manual documentation for some datasets | Lineage documented for AI training pipelines | Automated lineage capture end-to-end | Impact analysis and automated alerts on lineage changes |
| **Data classification** | No classification scheme | Basic sensitivity labels (public/internal/confidential) | Classification applied to AI datasets including PII and special category | Automated classification with policy enforcement | Classification integrated into AI governance workflows |
| **Data profiling** | No profiling | Manual profiling for some datasets | Profiling integrated into data pipeline | Automated profiling with distribution monitoring | Profiling triggers governance actions (bias alerts, gap detection) |

**Minimum viable level for EU AI Act compliance for high-risk systems: Level 2 across all capabilities.**

---
