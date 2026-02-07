# AI Governance Framework (SME, EU-first) — v1

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

