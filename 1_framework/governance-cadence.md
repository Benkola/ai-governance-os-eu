# Governance Cadence

> **Purpose:** Defines when governance activities happen — meeting rhythms, reporting cycles, review cadences, and escalation triggers. This is the heartbeat of the governance programme. Without cadence, governance is a collection of documents. With cadence, it's an operating system.
>
> **Why this matters:** Regulators don't just ask "do you have a risk management system?" — they ask "when did you last review it?" (Article 9.2(c)). Evidence of cadence is evidence of functioning governance.

---

## Meeting Rhythms

### Tier 1: AI Governance Committee

| Element | Detail |
|---------|--------|
| **Frequency** | Quarterly (Q1, Q2, Q3, Q4) + triggered |
| **Duration** | 90 minutes |
| **Chair** | CEO / COO |
| **Secretary** | AI Governance Lead |
| **Standing agenda** | |

| Time | Agenda Item | Owner | Output |
|------|------------|-------|--------|
| 0–10 min | AI system portfolio summary (new, changed, retired since last meeting) | AI Governance Lead | Noted |
| 10–30 min | Risk dashboard review — all Critical and High risks | AI Governance Lead | Decisions on escalated risks |
| 30–45 min | Regulatory update and horizon scan | Compliance Officer | Action items if new obligations |
| 45–60 min | High-risk deployment approvals (if any pending) | Tier 2 recommendation | Approve / Reject / Conditional |
| 60–75 min | Governance maturity assessment and programme KPIs | AI Governance Lead | Noted, actions if gaps |
| 75–90 min | Strategic decisions, budget, and resource requests | AI Governance Lead | Decisions documented |

| **Triggered meetings** | Convened within 48 hours for: Critical risk materialised, major AI incident (Article 62 serious incident), new regulation with material impact, board request |
| **Outputs** | Minutes with decisions, action owners, deadlines. Distributed within 5 business days. |
| **Quorum** | Chair + 3 members (must include DPO or Head of Risk) |

---

### Tier 2: AI Governance Working Group

| Element | Detail |
|---------|--------|
| **Frequency** | Monthly (first Tuesday of each month) + as needed |
| **Duration** | 60 minutes |
| **Chair** | AI Governance Lead |
| **Standing agenda** | |

| Time | Agenda Item | Owner | Output |
|------|------------|-------|--------|
| 0–10 min | Actions from previous meeting | AI Governance Lead | Status update, close or carry |
| 10–25 min | New intake forms — classification decisions | AI Governance Lead | Risk tier assigned per system |
| 25–40 min | Risk assessment reviews — risk scores and treatment plans | Risk Owner(s) | Approved / Revise / Escalate |
| 40–50 min | Evidence pack reviews — completeness check | AI Governance Lead | Signed off / Gaps identified |
| 50–55 min | Monitoring exceptions and alerts | ML Engineering Lead | Actions assigned |
| 55–60 min | Regulatory updates (brief) | Compliance Officer | Noted |

| **Ad-hoc meetings** | Convened within 5 business days for: New high-risk intake requiring urgent classification, incident triage (severity 1 or 2), evidence pack deadline approaching with gaps, regulatory query received |
| **Outputs** | Decision log with rationale, updated risk register entries, evidence pack status tracker. Distributed within 3 business days. |
| **Quorum** | Chair + AI Governance Lead + 2 other members |

---

### Tier 3: Operational Stand-Up (Optional for Mature Programmes)

| Element | Detail |
|---------|--------|
| **Frequency** | Fortnightly or as needed |
| **Duration** | 30 minutes |
| **Chair** | AI System Owner (rotates by system) |
| **Attendees** | AI System Owner, Data Steward, ML Engineer, Product Owner |
| **Purpose** | Operational coordination — monitoring status, data quality issues, evidence production progress, upcoming deadlines |
| **Output** | Operational actions. Escalate to Tier 2 if governance decision required. |

---

## Reporting Cycles

### Monthly Report (Tier 2 → Tier 1 preparation)

| Report Element | Content | Produced By | Deadline |
|---------------|---------|-------------|----------|
| AI System Inventory Status | Total systems, new additions, retirements, classification breakdown | AI Governance Lead | 5th of month |
| Risk Register Summary | All open risks by rating, changes since last month, overdue treatments | AI Governance Lead | 5th of month |
| Evidence Pack Tracker | Completion status per high-risk system, gaps, target dates | AI Governance Lead | 5th of month |
| Monitoring Dashboard | Model performance metrics, data quality metrics, alerts triggered | ML Engineering Lead + Data Steward | 5th of month |
| Incident Log | Incidents this month, severity, status, root cause (if known) | AI Governance Lead | 5th of month |
| Regulatory Updates | New guidance, enforcement actions, standards publications | Compliance Officer | 5th of month |

### Quarterly Report (Tier 1 Committee Pack)

| Report Element | Content | Produced By | Deadline |
|---------------|---------|-------------|----------|
| Executive Summary | 1-page summary: portfolio health, key risks, regulatory status, recommendations | AI Governance Lead | 10 days before Tier 1 |
| Risk Dashboard | All systems by risk tier, all risks by rating, trend analysis (improving/stable/worsening) | AI Governance Lead | 10 days before Tier 1 |
| Governance Maturity Assessment | Current maturity level vs target, progress since last quarter | AI Governance Lead | 10 days before Tier 1 |
| Regulatory Horizon Scan | Upcoming deadlines, new regulations, enforcement trends, impact assessment | Compliance Officer | 10 days before Tier 1 |
| KPI Report | See KPIs section below | AI Governance Lead | 10 days before Tier 1 |
| Deployment Approval Requests | High-risk systems pending Tier 1 approval with Tier 2 recommendation | AI Governance Lead | 10 days before Tier 1 |
| Budget and Resource Status | Spend vs budget, resource utilisation, requests for next quarter | AI Governance Lead | 10 days before Tier 1 |

### Annual Report

| Report Element | Content | Audience |
|---------------|---------|----------|
| Annual Governance Effectiveness Review | Year-in-review: systems governed, risks managed, incidents, maturity progress, regulatory engagement, lessons learned | Board, Tier 1, regulators (if requested) |
| AI System Portfolio Review | Full inventory audit, re-classification exercise, retirement candidates | Tier 1 |
| Regulatory Compliance Status | Compliance posture across all applicable regulations per AI system | Tier 1, regulators |
| Programme Investment Case | ROI of governance programme, cost avoidance (fines, incidents), next year plan | Board |

---

## Review Cadences

| What Is Reviewed | Cadence | Trigger for Ad-Hoc Review | Owner |
|-----------------|---------|---------------------------|-------|
| AI system risk classification | Annually | Material change to system, new regulation, incident | AI Governance Lead |
| Individual risk scores | Quarterly (minimum) | Monitoring alert, incident, treatment completion | Risk Owner |
| Full risk register | Quarterly | Post-incident, new regulation, Tier 1 directive | AI Governance Lead |
| Evidence packs | Annually per system | Material change, re-assessment, regulatory query | AI System Owner |
| Data quality metrics | Monthly | Threshold breach, pipeline change, data source change | Data Steward |
| Model performance metrics | Monthly | Performance below threshold, retraining | ML Engineering Lead |
| Human oversight effectiveness | Quarterly | Reviewer behaviour anomaly, incident | AI System Owner |
| AI literacy training compliance | Quarterly | New employees, role changes, regulatory update | AI Governance Lead |
| Vendor AI assessments | Annually per vendor | Contract renewal, vendor incident, new AI Act guidance | Procurement + AI Governance Lead |
| Operating model and RACI | Annually | Org restructure, new function, programme review | AI Governance Lead |
| Governance cadence itself | Annually | Programme maturity change, feedback | AI Governance Lead |

---

## Escalation Triggers

### Automatic Escalation to Tier 2

These events automatically trigger a Tier 2 Working Group discussion (ad-hoc meeting or next scheduled meeting if within 5 business days):

| Trigger | Response Time | Required Action |
|---------|---------------|-----------------|
| New high-risk AI system intake submitted | Next scheduled Tier 2 (or ad-hoc if >5 days away) | Classify, assign risk assessment owner |
| Risk score moves from Medium → High or High → Critical | Within 5 business days | Review treatment plan, consider escalation to Tier 1 |
| Model performance below declared accuracy threshold for >7 days | Within 5 business days | Investigate, determine if deployment should be paused |
| Data quality threshold breach affecting AI system | Within 5 business days | Investigate root cause, assess impact on model outputs |
| Evidence pack gap identified <30 days before regulatory deadline | Immediately | Resource allocation, remediation plan |
| AI incident (severity 2 or 3) | Next scheduled Tier 2 | Review, lessons learned, risk register update |

### Automatic Escalation to Tier 1

These events automatically trigger Tier 1 Committee awareness (within 48 hours) and may require an ad-hoc meeting:

| Trigger | Response Time | Required Action |
|---------|---------------|-----------------|
| Risk rating of Critical on any AI system | Within 48 hours (awareness); ad-hoc meeting if deployment decision needed | Tier 1 decision on deployment pause, additional resources |
| AI incident (severity 1 — serious incident) | Within 24 hours | Incident response activation, regulatory notification assessment |
| Regulatory enquiry or inspection received | Within 24 hours | Legal engagement, evidence gathering, response coordination |
| New regulation with material impact on AI programme | Within 5 business days | Impact assessment, budget/resource implications |
| High-risk deployment approval required | Next scheduled Tier 1 (or ad-hoc if timeline-critical) | Approve / Reject / Conditional |
| Governance programme KPI below threshold for 2 consecutive quarters | Next scheduled Tier 1 | Root cause analysis, programme adjustment |

### Incident Severity Levels (for escalation clarity)

| Severity | Description | Examples | Escalation |
|----------|-------------|----------|------------|
| **1 — Critical** | Serious incident under AI Act Article 62, fundamental rights infringement, or significant harm to persons | AI system causes discriminatory mass-decision affecting >1,000 persons; AI system contributes to physical harm; data breach exposing AI training data with special category personal data | Tier 1 within 24h. Regulators within 72h (if Article 62 applies). CEO/Board informed. |
| **2 — Major** | Significant operational impact, regulatory non-compliance discovered, or risk of harm | Model deployed without completed evidence pack; monitoring reveals undeclared bias; vendor AI component fails security assessment; human oversight failure detected | Tier 2 immediately. Tier 1 informed at next meeting. |
| **3 — Moderate** | Contained issue, process failure, or near-miss | Intake form bypassed; data quality breach caught before model retraining; monitoring alert triggered but below threshold; evidence pack incomplete but deadline >30 days away | Tier 2 at next meeting. |
| **4 — Minor** | Process improvement opportunity | Template gap identified; minor documentation correction needed; training not completed on schedule | AI Governance Lead resolves. Log and report at next Tier 2. |

---

## Governance KPIs

Tracked quarterly, reported to Tier 1.

### Coverage KPIs

| KPI | Target | Measurement |
|-----|--------|-------------|
| % of AI systems with completed intake forms | 100% | Systems with intake / total AI systems in inventory |
| % of high-risk systems with completed risk assessments | 100% | Assessed high-risk systems / total high-risk systems |
| % of high-risk systems with signed-off evidence packs | 100% | Signed-off packs / total high-risk systems |
| % of employees in AI roles who completed AI literacy training | 100% | Trained / total in scope |

### Quality KPIs

| KPI | Target | Measurement |
|-----|--------|-------------|
| Average time from intake to classification decision | <10 business days | Days between intake submission and Tier 2 classification |
| Average time from classification to evidence pack sign-off | <60 business days (high-risk) | Days between classification and evidence sign-off |
| % of risk treatments completed on schedule | >85% | On-time treatments / total due treatments |
| Evidence pack first-time pass rate (no gaps at Tier 2 review) | >70% | Packs passed first review / total reviewed |

### Risk KPIs

| KPI | Target | Measurement |
|-----|--------|-------------|
| Number of Critical-rated risks | 0 (aspiration); <3 (realistic) | Count from risk register |
| Risk score trend (aggregated across all systems) | Stable or improving | Quarter-over-quarter comparison |
| Number of AI incidents (severity 1 or 2) | 0 | Incident log |
| Mean time to resolve monitoring alerts | <48 hours | Alert triggered to resolution |

### Operational KPIs

| KPI | Target | Measurement |
|-----|--------|-------------|
| Tier 2 meeting attendance rate | >80% | Attendees / expected attendees |
| Tier 2 actions completed on time | >90% | On-time / total actions |
| AI system inventory accuracy | >95% | Verified systems / total claimed systems |
| Regulatory deadline compliance | 100% | Deadlines met / total deadlines |

---

## Annual Governance Calendar

| Month | Standing Activities | Periodic Activities |
|-------|--------------------|--------------------|
| **January** | Monthly Tier 2, Monthly report | Annual governance effectiveness review (prior year), Annual RACI review |
| **February** | Monthly Tier 2, Monthly report | AI literacy training plan for year |
| **March** | Monthly Tier 2, Monthly report | Q1 Tier 1 Committee meeting |
| **April** | Monthly Tier 2, Monthly report | Annual AI system inventory audit begins |
| **May** | Monthly Tier 2, Monthly report | AI system inventory audit completed |
| **June** | Monthly Tier 2, Monthly report | Q2 Tier 1 Committee meeting, Half-year maturity assessment |
| **July** | Monthly Tier 2, Monthly report | Annual vendor AI assessment cycle begins |
| **August** | Monthly Tier 2, Monthly report | Regulatory horizon scan (extended) |
| **September** | Monthly Tier 2, Monthly report | Q3 Tier 1 Committee meeting |
| **October** | Monthly Tier 2, Monthly report | Operating model review |
| **November** | Monthly Tier 2, Monthly report | Governance programme budget proposal (next year) |
| **December** | Monthly Tier 2, Monthly report | Q4 Tier 1 Committee meeting, Annual governance report to Board |

---

## Implementation Notes

### For Organisations Starting from Zero

If no governance cadence exists today, don't try to implement everything at once. Sequence:

1. **Month 1:** Establish Tier 2 Working Group monthly meeting. Just the meeting. Set the agenda. Show up.
2. **Month 2:** Produce the first monthly report. Even if incomplete. The act of trying to fill in the template reveals what data you don't have.
3. **Month 3:** Hold the first Tier 1 quarterly meeting. Present what you have. Get strategic buy-in.
4. **Month 4–6:** Add monitoring cadences, escalation triggers, and KPI tracking as systems come into governance.
5. **Month 7–12:** Achieve full cadence. Refine based on experience.

### For Organisations with Existing GRC

If you already have risk committee meetings, compliance reporting, and incident management:

1. **Don't create parallel governance.** Integrate AI governance into existing structures. AI risks go into the enterprise risk register. AI incidents follow existing incident management. AI compliance is part of the compliance function.
2. **Add AI-specific agenda items** to existing meetings rather than creating new meetings. The Tier 2 Working Group may be a new meeting, but the Tier 1 Committee should be an extension of an existing risk committee or executive meeting.
3. **Use existing reporting cycles.** If your organisation reports risk quarterly, add AI risk to the quarterly report. Don't create a separate AI risk reporting cycle.

### Common Failure Modes

| Failure Mode | What It Looks Like | Fix |
|-------------|-------------------|-----|
| Meeting without decisions | Tier 2 meets monthly, discusses risks, but never formally approves or rejects anything | Require every agenda item to have a decision owner and a "Decide / Defer / Escalate" outcome |
| Reporting without reading | Monthly reports produced, nobody reads them | Shorten the report. Make the executive summary one page. Tie KPIs to individual accountability. |
| Escalation without response | Alerts escalated to Tier 1, but no action taken | Track escalation resolution time as a KPI. Report unresolved escalations to the Board. |
| Cadence without coverage | Meetings happen, but only cover 3 of 20 AI systems | Rotate systems through the agenda. Every high-risk system reviewed at least once per quarter. |
| Annual review as only review | Everything reviewed once a year, nothing in between | The annual review is the minimum for low-risk items. High-risk items need quarterly minimum. |
