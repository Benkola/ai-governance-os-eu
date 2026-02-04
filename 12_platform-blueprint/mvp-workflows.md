# MVP Workflows

## Workflow 1: Intake → Classification
**Inputs**
- Use case description, users, business purpose
- Data types/sources, vendor involvement, deployment context

**Steps**
1) Capture intake fields
2) Identify likely risk tier (hypothesis, not legal determination)
3) Determine which obligations are likely relevant
4) Generate a “next required evidence” checklist

**Outputs**
- Completed intake record
- Draft classification + obligation shortlist
- Evidence pack checklist

---

## Workflow 2: Controls → Evidence Pack Generation
**Inputs**
- Intake record
- Controls map reference
- Organisation context (SME constraints, tooling)

**Steps**
1) Select controls required for the likely obligation set
2) Generate evidence artefacts:
   - Risk register entries (with owners/cadence)
   - Model card + system card drafts
   - Monitoring plan draft
   - Incident response draft
3) Flag missing inputs or unclear decisions for human review

**Outputs**
- Draft evidence pack (editable)
- Missing-information list

---

## Workflow 3: Approval → Audit Log
**Inputs**
- Evidence pack + checklist completeness
- Decision rights (approver list)

**Steps**
1) Confirm completeness against the evidence gate
2) Capture explicit go/no-go decision
3) Record rationale + conditions (e.g., “must add monitoring threshold X”)

**Outputs**
- Approval record
- Conditions of deployment
- Review schedule

---

## Workflow 4: Monitoring Setup → Review Cadence
**Inputs**
- System context + key metrics
- Owners and cadence

**Steps**
1) Define monitoring signals + thresholds
2) Define review cadence (monthly/weekly) based on risk
3) Define escalation path and rollback trigger

**Outputs**
- Monitoring plan
- Review calendar prompts (conceptual)

---

## Workflow 5: Incident → Post-Incident Review
**Inputs**
- Incident report (what happened, impact, timeframe)

**Steps**
1) Triage severity + containment actions
2) Capture root cause hypothesis
3) Define corrective actions (controls, monitoring, documentation updates)
4) Capture post-incident review within 5 working days

**Outputs**
- Incident record
- Lessons learned + control updates
- Evidence pack updates

---

## Exports (board/procurement/regulator)
- Board pack: purpose, risk, decision, monitoring, accountability
- Procurement pack: vendor responsibilities, evidence demands, monitoring commitments
- Regulator-ready pack (conceptual): traceability + evidence + incident readiness
