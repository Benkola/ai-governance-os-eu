# AI Governance Framework (SME, EU-first) — v1

This framework exists to help teams ship AI safely without slowing delivery.
It is designed to integrate into real release processes (UAT, CAB, weekly delivery forums) and scale governance effort by risk, not bureaucracy.

## 1) Purpose
Create a repeatable, lightweight governance system that enables SMEs to adopt AI safely and credibly under EU expectations:
- clear decision rights
- evidence-based approvals
- monitoring + incident readiness
- vendor accountability

## 2) Principles (non-negotiables)
1) **No deployment without evidence.**
2) **Risk decisions must have owners and a review cadence.**
3) **Governance must be lightweight and operational, not committee theatre.**
4) **Vendor AI still requires oversight (due diligence + monitoring).**
5) **Measure what matters (performance, safety, abuse, privacy).**
6) **Document intent, limits, and failure modes.**
7) **Governance artefacts must be reviewed at UAT sign-off and referenced in CAB approval; unused documentation does not count.**
8) **No vendor AI is deployed without explicit internal ownership and minimum evidence; vendor assurances never replace accountability.**
9) **Governance is risk-tiered (Low / Medium / High); low-risk ≤30 mins, higher risk = deeper evidence + cadence.**

## 3) Scope (systems this applies to)
- Internal ML systems used in business processes
- GenAI features (assistants, summarisation, search augmentation)
- Vendor AI tools used in customer, HR, finance, compliance, or operations

## 4) The governance lifecycle (end-to-end)

### Intake
**Objective:** capture business purpose + context + constraints  
**Output:** Intake record (use case, data, vendor, deployment context)

### Risk assessment
**Objective:** identify harms, stakeholders, misuse/abuse, and operational risks  
**Output:** risk register entries mapped to controls + evidence

### Build/buy decision
**Objective:** determine whether to build internally or use a vendor; clarify responsibilities  
**Output:** vendor due diligence/tool evaluation (if vendor)

### Pre-deploy checks (evidence gate)
**Objective:** confirm documentation + controls exist and are operating  
**Output:** evidence pack + go/no-go decision

### Deploy + change control
**Objective:** deploy with clear ownership, rollback paths, and logging  
**Output:** change record + monitoring enabled

### Monitor + evaluate
**Objective:** detect drift, failures, safety issues, abuse, privacy risks  
**Output:** monitoring dashboard/signals + periodic review notes

### Incident response
**Objective:** triage, contain, remediate, learn  
**Output:** incident record + post-incident review + control updates

### Retire
**Objective:** decommission safely, retain required records, prevent orphaned risk  
**Output:** retirement record + access/logging cleanup

## 5) Required artefacts (the evidence pack)
Minimum viable artefacts before deployment:
- Intake form
- Risk register entries (risks → controls → evidence → owner)
- Model card (intent, limits, evals, risks)
- System card (data flows, oversight, monitoring, escalation)
- Monitoring plan (signals, thresholds, cadence, owners)
- Incident response playbook (severity, escalation, rollback)

## 6) Decision rights (who approves what)
Minimum viable decision rights for an SME:
- **Product owner/business owner:** owns purpose and acceptable risk for the use case
- **Technical owner (eng/data):** owns system design, deployment, and monitoring integrity
- **Security/Privacy:** approves data protection, access controls, leakage risks
- **Risk/Compliance (if present):** confirms evidence completeness and review cadence
- **Final Go/No-Go:** named accountable approver (single-threaded decision)

## 7) Minimum viable governance cadence
- Monitoring review: monthly (weekly for higher-risk systems)
- Governance review: quarterly (portfolio view)
- Post-incident review: within 5 working days

## 8) SME implementation in 14 days (practical steps)
1) Define scope + roles (one accountable owner per system)
2) Adopt intake form + risk register templates
3) Create an evidence gate checklist (what must exist before deployment)
4) Stand up a monthly monitoring review meeting (30 minutes)
5) Create incident playbook (severity + escalation + rollback)
6) Apply to one pilot use case and refine

## 9) What “good” looks like (observable evidence)
- Intake forms exist for all deployed systems
- Risk register entries have owners and review dates
- Model/system documentation exists and matches reality
- Monitoring is active with thresholds and escalation
- Incidents are recorded and drive control improvements
- Vendor obligations and responsibilities are explicit in writing

## 10) How this framework is used
- Referenced during UAT sign-off to confirm evidence exists
- Used as a CAB input for AI-enabled releases
- Reviewed in weekly delivery forums for risk ownership and open issues
- Scales requirements by risk tier to avoid slowing low-risk delivery

Data governance foundation
AI governance is only as strong as the data governance it stands on. An AI system trained on poorly governed data — uncatalogued, unclassified, of unknown quality, with no lineage — cannot be meaningfully governed regardless of what policies surround it.
This framework assumes the following data governance capabilities are in place (or being built in parallel):
CapabilityWhat it meansWhy AI governance needs itData ownershipEvery critical data asset has a named owner accountable for its quality and appropriate useAI risk assessments require knowing who is responsible for training data, evaluation data, and production dataData stewardshipStewards operate day-to-day governance: quality checks, access reviews, classification enforcementStewards are the operational layer that makes AI governance executable, not theoreticalData quality managementQuality is measured against defined dimensions (accuracy, completeness, consistency, timeliness, validity, uniqueness)Model performance degrades with poor data quality; monitoring plans must include data quality signalsMetadata managementData assets are catalogued with business and technical metadata, enabling discovery and understandingEU AI Act Article 10 (data governance) requires documentation of training data characteristics — impossible without metadataData lineageThe path from raw data to model input to decision output is traceableAuditability under the EU AI Act and GDPR requires demonstrating how data flows through AI systemsData classificationData is labelled by sensitivity (public, internal, confidential, restricted) and category (personal, financial, health)Risk classification of AI systems depends on the sensitivity of data they process
Reference framework: DAMA DMBOK2 (Data Management Body of Knowledge) provides the canonical structure for these capabilities. This governance OS does not replicate DMBOK but aligns with it as the data governance backbone.
Where an organisation's data governance maturity is low, the maturity model and readiness scorecard in this repo will flag it — and the intake form includes data governance readiness questions to prevent AI deployment on ungoverned data.

Regulatory alignment
This governance OS is designed for multi-regulatory compliance. While the EU AI Act is the primary driver, AI governance intersects with several other regulatory frameworks:
RegulationRelevance to AI governanceEU AI Act (Regulation 2024/1689)Primary framework. Defines risk tiers, obligations for providers and deployers, documentation requirements, conformity assessment, and post-market monitoring. This repo's controls map, templates, and case studies are built directly from the Act.GDPR (Regulation 2016/679)AI systems processing personal data must comply with GDPR principles: lawfulness, purpose limitation, data minimisation, accuracy, storage limitation, integrity/confidentiality, and accountability. Article 22 governs automated individual decision-making. The DPIA-lite template in this repo addresses GDPR data protection impact assessments.Digital Markets Act (DMA, Regulation 2022/1925)Relevant for organisations using or providing AI through gatekeeper platforms. DMA obligations around data access, interoperability, and transparency intersect with AI governance when AI systems depend on or operate within gatekeeper ecosystems.Digital Services Act (DSA, Regulation 2022/2065)Relevant for AI systems involved in content moderation, recommendation algorithms, or online platform services. DSA requires transparency of recommender systems and risk assessments for very large platforms — both governance-adjacent.SOx (Sarbanes-Oxley Act, 2002)Relevant for publicly listed companies (or those with US reporting obligations). SOx Section 404 requires internal controls over financial reporting. Where AI systems influence financial data, reporting, or decision-making, data governance controls (quality, lineage, access) must satisfy SOx IT General Controls (ITGCs).NIST AI RMF 1.0Not a regulation but a governance framework. This repo includes a full crosswalk between EU AI Act obligations and NIST AI RMF functions, enabling organisations to implement once and demonstrate compliance across both.ISO/IEC 42001International standard for AI management systems. This repo aligns conceptually with ISO 42001's management system structure (policy, objectives, roles, continual improvement) without claiming certification.
This multi-regulatory alignment ensures the governance OS is useful beyond EU AI Act compliance alone — it provides a foundation that scales as regulatory obligations increase.
