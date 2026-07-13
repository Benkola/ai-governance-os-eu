# RACI Matrix — AI Governance Lifecycle

> **Purpose:** Defines who is Responsible, Accountable, Consulted, and Informed for every activity in the AI governance lifecycle. Eliminates ambiguity about ownership.
>
> **How to read:** R = Responsible (does the work), A = Accountable (owns the outcome, one per row only), C = Consulted (provides input before the decision), I = Informed (told after the decision).
>
> **Key design principle:** Data Steward and Data Owner appear as explicit roles because AI governance cannot function without data governance execution. Most RACI matrices for AI governance omit these roles and then wonder why Article 10 compliance fails.

---

## Roles Key

| Abbreviation | Role | Primary Function |
|-------------|------|------------------|
| **AGL** | AI Governance Lead | Coordinates governance programme, chairs Tier 2 |
| **ASO** | AI System Owner | Owns compliance for their specific AI system |
| **DO** | Data Owner | Business authority over data quality and use decisions |
| **DS** | Data Steward | Executes data quality, lineage, cataloguing, classification |
| **MLE** | ML Engineering Lead | Builds, deploys, and monitors AI systems technically |
| **PO** | Product Owner | Owns business requirements and user outcomes |
| **DPO** | Data Protection Officer | GDPR compliance and privacy |
| **CO** | Compliance Officer | Cross-regulatory compliance |
| **SEC** | Security / CISO | Cybersecurity, adversarial risk, data protection |
| **T1** | Tier 1 Committee | Strategic governance body (C-suite) |
| **T2** | Tier 2 Working Group | Tactical governance body (cross-functional) |

---

## Phase 1: Intake and Classification

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Submit AI use case intake form | I | R/A | C | C | C | C | I | I | I | | |
| Identify applicable datasets | I | C | A | R | C | | I | | | | |
| Assess data governance readiness (intake Section 4) | C | I | A | R | C | | | | | | |
| Confirm data owner for each dataset | A | I | R | I | I | | | | | | |
| Check prohibited practices (Article 5) | R | C | | | C | | C | A | | | I |
| Classify risk tier (prohibited / high / limited / minimal) | R | C | | | C | | C | C | | | A |
| Map applicable regulations (AI Act + GDPR + DORA + sector) | C | I | | | | | C | R/A | | | I |
| Register system in AI inventory | R/A | C | I | I | C | | I | I | | | I |

**Key decisions in this phase:**
- Risk classification is decided by Tier 2 (Accountable), with input from AI Governance Lead, Compliance Officer, and DPO.
- Data governance readiness is the Data Steward's work product, but the Data Owner is Accountable for the data being fit for purpose.

---

## Phase 2: Risk Assessment

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Identify known and foreseeable risks (Art 9.2a) | R | A | C | C | C | C | C | C | C | | I |
| Assess foreseeable misuse risks (Art 9.2b) | R | A | | | C | C | C | C | C | | I |
| Profile training/validation/testing data | I | I | C | R/A | C | | I | | | | |
| Assess dataset bias and representativeness (Art 10.2f) | C | I | C | R | A | | C | | | | I |
| Verify data quality meets defined thresholds | I | I | A | R | C | | | | | | |
| Document data lineage for AI datasets | I | I | C | R/A | C | | | | | | |
| Score risks (likelihood × impact) | R/A | C | | | C | | C | C | C | | I |
| Determine risk treatment (eliminate / mitigate / accept) | R | C | C | | C | | C | C | C | | A |
| Assign risk treatment owners | A | I | I | I | I | I | I | I | I | | R |
| Conduct DPIA (if personal data involved) | C | C | C | C | | | R/A | I | | | I |
| Conduct FRIA (if high-risk, public sector / certain deployers) | R/A | C | | | C | | C | C | | | I |
| Approve risk assessment | I | I | | | | | I | I | | | R/A |

**Key decisions in this phase:**
- Data profiling and lineage are Data Steward responsibilities — the AI governance team consumes these outputs but doesn't produce them.
- Bias assessment is the ML Engineering Lead's accountability, with Data Steward providing the data profiling inputs.
- Risk treatment decisions are Tier 2's accountability.

---

## Phase 3: Documentation and Evidence

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Produce Annex IV technical documentation | C | A | | C | R | C | C | | | | I |
| Document data governance practices (Art 10) | C | I | A | R | C | | I | | | | |
| Document design choices for datasets (Art 10.2) | I | I | C | R | A | | | | | | |
| Produce transparency documentation (Art 13) | C | A | | | R | C | C | | | | I |
| Design human oversight measures (Art 14) | C | A | | | R | C | | | | | I |
| Document human oversight training requirements | R | A | | | C | C | | C | | | I |
| Produce conformity self-assessment | R/A | C | | | C | | C | C | | | I |
| Compile evidence pack | R/A | C | I | C | C | | C | C | C | | I |
| Review evidence pack for completeness | A | I | | | | | C | C | | | R |
| Sign off evidence pack | I | I | | | | | I | I | | | R/A |

**Key decisions in this phase:**
- Evidence pack compilation is the AI Governance Lead's responsibility, but it depends on inputs from every other role.
- The Data Steward is Consulted on the evidence pack because they provide the data governance evidence (quality metrics, lineage documentation, catalogue entries).
- Evidence pack sign-off is Tier 2's accountability.

---

## Phase 4: Deployment Approval

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Verify all evidence requirements met | R/A | C | | C | C | | C | C | C | | I |
| Verify data governance readiness confirmed | C | I | A | R | | | | | | | I |
| Recommend deployment approval | R | C | | | | | C | C | C | | A |
| Approve high-risk deployment | I | I | | | | | I | I | | R/A | C |
| Approve limited/minimal-risk deployment | I | I | | | | | I | I | | I | R/A |
| Register in EU database (if required) | R/A | C | | | | | | C | | | I |
| Log deployment decision and rationale | R/A | I | | | | | I | I | | I | I |

**Key decisions in this phase:**
- High-risk deployments are approved by Tier 1 (the governance committee). This is non-negotiable for Annex III systems.
- Limited and minimal-risk deployments are approved by Tier 2 (the working group).
- The Data Owner confirms data governance readiness as a deployment gate.

---

## Phase 5: Monitoring and Operations

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Monitor model accuracy, robustness (Art 15) | I | A | | | R | | | | | | I |
| Monitor data quality (input features) | I | I | A | R | C | | | | | | |
| Monitor data drift / distribution shift | I | I | C | R | A | | | | | | |
| Monitor human oversight effectiveness (Art 14) | R | A | | | C | | | | | | I |
| Track AI literacy training completion (Art 4) | R/A | I | | | I | I | | C | | I | I |
| Conduct quarterly risk register review | R/A | C | C | C | C | | C | C | C | I | I |
| Produce monitoring reports | C | R | | C | A | | | | | | I |
| Escalate monitoring alerts | R | A | | I | R | | I | I | I | I* | I |
| Post-market monitoring (if provider) | C | A | | C | R | | | C | | | I |

*T1 informed immediately for Critical-rated alerts.

**Key decisions in this phase:**
- Data quality monitoring is the Data Steward's ongoing responsibility. This is where the data governance–AI governance bridge is most active day-to-day.
- Data drift detection is a shared responsibility: the Data Steward monitors data distribution, the ML Engineering Lead monitors model performance. Both signals are needed to diagnose problems (see dependency map).

---

## Phase 6: Incident Response

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Detect incident (automated or reported) | I | I | | I | R | | | | R | | |
| Classify incident severity | R/A | C | | | C | | C | C | C | | I |
| Contain incident (technical) | I | C | | | R/A | | | | C | | I |
| Investigate root cause | C | A | C | R* | R* | | C | | C | | I |
| Notify regulator (if serious incident) | C | I | | | | | C | R/A | | I | I |
| Notify affected persons (if required) | C | I | | | | | R/A | C | | I | I |
| Update risk register | R/A | C | | | C | | | C | | | I |
| Conduct post-incident review | R/A | C | C | C | C | C | C | C | C | I | I |
| Implement corrective actions | C | A | C | R* | R* | | | C | C | | I |

*Data Steward investigates if root cause is data-related; ML Engineering investigates if root cause is model-related. Often both are involved.

---

## Phase 7: Change and Retirement

| Activity | AGL | ASO | DO | DS | MLE | PO | DPO | CO | SEC | T1 | T2 |
|----------|-----|-----|----|----|-----|----|----|----|----|----|----|
| Assess material change impact | R | A | C | C | C | C | C | C | | | I |
| Determine if re-assessment required | R/A | C | | | C | | C | C | | | I |
| Update evidence pack for changes | C | A | | C | R | | C | | | | I |
| Plan system retirement | C | A | C | C | R | C | C | | | | I |
| Archive evidence and documentation | R/A | C | | C | C | | I | I | | | I |
| Data retention / deletion after retirement | I | I | A | R | C | | C | | | | |
| Update AI inventory | R/A | I | | | | | I | I | | | I |
| Deregister from EU database (if applicable) | R/A | C | | | | | | C | | | I |

---

## RACI Design Principles

1. **One Accountable per row.** If accountability is unclear, governance breaks down. Every row has exactly one "A."

2. **Data Steward and Data Owner are first-class governance roles.** They appear in every phase because every phase has data governance dependencies. This is not an afterthought — it's a design requirement driven by Articles 9, 10, 12, and 15.

3. **The AI Governance Lead coordinates but does not own everything.** The AGL is Responsible for many coordination activities but Accountable primarily for the governance programme itself. System-level accountability sits with the AI System Owner.

4. **Tier 2 is the engine room.** Most decisions are made at Tier 2. Tier 1 handles only strategic decisions and high-risk approvals. This keeps governance proportionate.

5. **Compliance Officer owns cross-regulatory mapping.** The AI Governance Lead is not a compliance specialist. The Compliance Officer ensures that AI Act obligations are mapped alongside GDPR, DORA, MiFID II, PSD2, Solvency II, and sector-specific requirements.

---

## How to Implement This RACI

**Step 1:** Map your organisation's existing roles to these role definitions. Not every role needs a dedicated person — in smaller organisations, one person may hold 2–3 roles (e.g., AI Governance Lead + Compliance Officer).

**Step 2:** Identify gaps. The most common gaps are: no designated Data Steward for AI datasets, no AI System Owner (business assumes ML team owns compliance), and no Tier 2 Working Group (governance decisions made ad hoc).

**Step 3:** Socialise with each role holder. Walk through their column in the RACI. Confirm they understand their R, A, C, and I responsibilities. Address objections.

**Step 4:** Embed in the governance cadence. The RACI only works if it's referenced in meeting agendas, reporting templates, and escalation procedures. It's not a wall poster — it's an operating tool.
