# SOx and Data Governance Alignment

> **Purpose:** Shows how data governance practices support Sarbanes-Oxley (SOx) IT General Controls (ITGCs), and how AI systems that influence financial reporting inherit SOx obligations. This is a one-page bridge document demonstrating enterprise governance awareness — the recognition that AI governance, data governance, and financial controls are not separate worlds.
>
> **Who needs this:** Any organisation that is US-listed (or a subsidiary of a US-listed parent) and uses AI systems that influence financial reporting — revenue forecasting, provisioning, valuation, expense classification, or any model whose output flows into the financial statements.

---

## Why SOx Matters for AI and Data Governance

The Sarbanes-Oxley Act of 2002 requires US-listed companies to maintain effective internal control over financial reporting (ICFR). Section 404 requires management to assess, and auditors to attest to, the effectiveness of those controls.

When an AI system influences financial reporting, it becomes part of the ICFR scope. The data feeding that AI system, and the controls governing that data, fall under SOx IT General Controls. This means data governance is not just an AI Act concern — it's a financial controls concern with auditor scrutiny and personal liability for executives who certify the financials.

**The key insight:** The same data governance capabilities that satisfy EU AI Act Article 10 also satisfy SOx ITGC requirements. Build them once, satisfy both.

---

## IT General Controls (ITGCs) and Data Governance

SOx ITGCs cover four domains. Data governance directly supports three of them.

| ITGC Domain | What SOx Requires | Data Governance Capability That Supports It |
|-------------|-------------------|--------------------------------------------|
| **Access to Programs and Data** | Logical access to financially-relevant systems and data is restricted to authorised users; access aligned to roles; access reviewed periodically | Data classification (identifying financially-relevant data), data access governance (least-privilege aligned to classification), access reviews on cadence |
| **Program Changes** | Changes to systems affecting financial reporting are authorised, tested, and documented | Data lineage (tracing how changes to data pipelines affect financial outputs), metadata management (documenting what changed and when) |
| **Program Development** | New systems affecting financial reporting are developed under control, tested, and approved | Data quality measurement (validating data before it feeds financial models), data cataloguing (registering new financially-relevant datasets), AI intake and risk assessment |
| **Computer Operations** | Systems run reliably; jobs complete; failures are detected and resolved; data backups exist | Data quality monitoring (detecting data pipeline failures), monitoring and alerting (supported by data governance metrics) |

---

## How AI Systems Inherit SOx Obligations

When an AI system's output influences the financial statements, the following SOx considerations apply:

| AI / Data Governance Activity | SOx Relevance |
|-------------------------------|---------------|
| AI system inventory and classification | Identifies which AI systems are in SOx scope (those influencing financial reporting) |
| Data quality measurement | SOx requires that data underpinning financial reporting is complete and accurate — exactly what data quality measurement provides |
| Data lineage | SOx auditors must trace financial figures to their source; lineage from source data through the AI model to the financial output is the audit trail |
| Access governance | SOx requires restricted, reviewed access to financially-relevant data and the models that process it |
| Change management | Changes to the AI model or its training data must be authorised, tested, and documented — a SOx program-change control |
| Human oversight | SOx requires that automated outputs influencing financials are subject to management review — the AI Act's Article 14 human oversight serves this purpose |
| Audit trail and record-keeping | SOx requires evidence of control operation; the AI Act's Article 12 logging provides it |

---

## The Convergence: One Control Set, Three Regulations

A single AI system influencing financial reporting at a US-listed Dutch financial institution sits under three overlapping control regimes:

| Requirement | EU AI Act | GDPR | SOx |
|-------------|-----------|------|-----|
| Data quality assured | Article 10 | Accuracy principle (Art 5.1.d) | ITGC — data accuracy for ICFR |
| Data access restricted | Article 15 (cybersecurity) | Security principle (Art 5.1.f) | ITGC — access controls |
| Changes controlled and documented | Article 9 (risk mgmt), Art 11 (documentation) | — | ITGC — program change controls |
| Lineage / traceability | Article 10, Art 11 (Annex IV) | Accountability (Art 5.2) | ITGC — audit trail |
| Human oversight of automated output | Article 14 | Art 22 (automated decisions) | ICFR — management review controls |
| Logging and record-keeping | Article 12 | — | ITGC — evidence of control operation |

**The strategic implication:** An organisation that builds robust data governance is simultaneously building AI Act compliance, GDPR compliance, and SOx ITGC compliance. These are not three separate programmes competing for budget. They are one data governance investment satisfying three regulatory masters. This is the argument that unlocks data governance funding — it's not an AI cost, it's an enterprise control that pays for itself across the compliance portfolio.

---

## Practical Checklist: Is Your AI System in SOx Scope?

Answer these to determine SOx applicability:

1. Is your organisation US-listed, or a subsidiary of a US-listed parent? ☐ Yes ☐ No
2. Does the AI system's output influence a financial reporting figure (revenue, provisions, valuation, expense classification, impairment)? ☐ Yes ☐ No
3. Is the influence material (could it affect the accuracy of the financial statements)? ☐ Yes ☐ No

**If all three are Yes:** The AI system is in SOx scope. Its data governance, access controls, change management, and human oversight must satisfy ITGC requirements and will be subject to auditor testing. Document the controls accordingly and coordinate with the SOx compliance function.

**If any is No:** SOx ITGC requirements likely do not apply to this system — but EU AI Act and GDPR obligations still do. Reassess if the system's use changes.

---

## One-Sentence Summary for Executives

*"The data governance we're building for the EU AI Act is the same data governance our auditors need for SOx — measured data quality, documented lineage, controlled access, and change management — so this is one enterprise control investment satisfying multiple regulators, not a series of separate compliance costs."*
