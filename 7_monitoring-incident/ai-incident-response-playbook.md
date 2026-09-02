# AI Incident Response Playbook

> **Purpose:** Defines what happens when an AI system fails, misbehaves, or causes harm. Governance is only as good as its incident response — a beautiful risk framework means nothing if, when the model discriminates or the chatbot says something harmful, nobody knows who does what. This playbook adapts established incident-response discipline (NIST, ITIL) to AI-specific failures and aligns the process to EU AI Act obligations, including the serious-incident reporting duty under Article 73.
>
> **When to use:** The moment an AI incident is detected or reported. Keep this playbook accessible — incident response is not the time to invent a process.
>
> **Owner:** AI Governance Lead coordinates; AI System Owner is accountable for their system; Compliance Officer handles regulatory notification.

---

## 1. What Counts as an AI Incident

An AI incident is any event where an AI system causes, or risks causing, harm, non-compliance, or loss of trust. AI incidents differ from traditional IT incidents: the system may be "working" technically while producing harmful outputs.

| Incident type | Example |
|---------------|---------|
| **Discriminatory output** | Model systematically disadvantages a protected group |
| **Accuracy failure** | Model performance degrades below declared threshold, producing wrong decisions at scale |
| **Harmful generation** | GenAI system produces toxic, false, defamatory, or dangerous content |
| **Data leakage** | Model exposes training data, personal data, or confidential information |
| **Security compromise** | Data poisoning, model extraction, adversarial manipulation |
| **Oversight failure** | Human oversight mechanism found to be non-functional (rubber-stamping) |
| **Misuse** | System used outside its intended purpose in a harmful way |
| **Regulatory breach** | System operating without required documentation, or in violation of an obligation |

---

## 2. Severity Levels

Severity determines response speed and who is involved. This mirrors the governance cadence severity model.

| Severity | Definition | Examples | Response time |
|----------|-----------|----------|---------------|
| **SEV-1 Critical** | Serious harm to persons, fundamental rights infringement at scale, or an AI Act "serious incident" | Discriminatory mass-decision affecting thousands; AI contributes to physical harm; large-scale personal data exposure | Immediate — response team activated within 1 hour; regulator assessment within 24h |
| **SEV-2 Major** | Significant harm risk, regulatory non-compliance, or material business impact | Undeclared bias detected in production; model deployed without evidence pack; harmful GenAI output reaching customers | Response within 4 hours |
| **SEV-3 Moderate** | Contained issue or near-miss | Data quality breach caught before affecting decisions; monitoring alert above threshold but limited impact | Response within 1 business day |
| **SEV-4 Minor** | Process failure or improvement need | Documentation gap; training not completed; minor threshold warning | Handled in normal workflow |

---

## 3. The Six-Phase Response

### Phase 1 — Detection

*How the incident surfaces.*

| Source | Detail |
|--------|--------|
| Automated monitoring | A threshold breach from the monitoring playbook |
| Human report | An employee, customer, or affected person reports a problem |
| Oversight escalation | A reviewer flags a pattern |
| External | Regulator enquiry, media, researcher disclosure |

**On detection:** Log the incident immediately — time, source, system, initial description. Assign a preliminary severity. Notify the AI System Owner and AI Governance Lead. The clock starts here, and for potential serious incidents the regulatory timeline may start here too.

### Phase 2 — Triage

*Assess and classify.*

- Confirm the incident is real (rule out false alarm).
- Assign definitive severity (SEV-1 to SEV-4).
- Identify affected persons/systems and scale of impact.
- Determine if it may be an AI Act "serious incident" (triggers regulatory notification — see Section 5).
- Assemble the response team appropriate to severity.

### Phase 3 — Containment

*Stop the harm from spreading.*

| Option | When |
|--------|------|
| **Pause the system** | SEV-1, or when continued operation risks ongoing harm |
| **Fall back to human decision-making** | When the AI can be bypassed while investigation proceeds |
| **Restrict scope** | Limit the system to lower-risk uses temporarily |
| **Roll back** | Revert to a previous model version if the current version is the problem |
| **Continue with enhanced oversight** | For lower-severity incidents where pausing is disproportionate |

Containment is a judgement call balancing the harm of continued operation against the harm of switching the system off. Document the decision and its rationale.

### Phase 4 — Investigation

*Find the root cause.*

The investigation must distinguish the failure type (this is where the monitoring signals and data lineage pay off):

- **Is it a data problem?** Data drift, quality failure, poisoning. → Data Steward leads, using lineage to trace source.
- **Is it a model problem?** Concept drift, training flaw, specification error. → ML Engineering leads.
- **Is it an oversight problem?** Human safeguard failed. → AI System Owner leads.
- **Is it a misuse problem?** System used outside intended purpose. → AI System Owner + Compliance.

Document findings with evidence. The root cause determines the remediation.

### Phase 5 — Remediation

*Fix it.*

| Root cause | Typical remediation |
|-----------|---------------------|
| Data drift | Retrain on recent data; fix the data pipeline |
| Concept drift | Retrain with new labels; potentially re-engineer features |
| Bias | Apply fairness constraints; re-assess; adjust thresholds |
| Oversight failure | Redesign oversight; retrain reviewers; add monitoring |
| Documentation gap | Produce the missing documentation; assess how it was missed |
| Security | Patch vulnerability; assess exposure; may require breach notification |

Verify the fix before returning the system to full operation. Update the risk register with what was learned.

### Phase 6 — Post-Mortem

*Learn from it.*

Within a defined window after resolution, conduct a blameless post-mortem:
- What happened, and what was the timeline?
- What was the root cause?
- Why wasn't it caught earlier? (This often reveals a monitoring gap.)
- What corrective actions prevent recurrence?
- Do other systems share this vulnerability?
- Does the risk register, monitoring, or documentation need updating?

The post-mortem output feeds back into the framework: new risks registered, new monitoring thresholds, updated playbooks. An incident that doesn't improve the system is a wasted incident.

---

## 4. Communication Templates

### Internal escalation (SEV-1/2)

> **AI Incident Alert — [SEV-level]**
> System: [name]
> Detected: [time] via [source]
> Summary: [1-2 sentences: what is happening and who is affected]
> Immediate impact: [scale — how many affected, what harm]
> Containment status: [paused / restricted / monitoring]
> Response lead: [name]
> Next update: [time]

### Affected-person notification (where required)

> We identified an issue with an automated system that may have affected [decision/service]. We are [action taken]. If you were affected, [remedy/next step]. You have the right to [human review / contest the decision — GDPR Art 22 where applicable]. Contact: [channel].

### Regulator notification (SEV-1 serious incident)

> Follow the competent authority's prescribed format. Include: system description, nature of the incident, affected persons, timeline, containment and remediation actions, and preventive measures. Coordinate with Legal before sending.

---

## 5. Regulatory Notification (EU AI Act)

The EU AI Act requires providers of high-risk systems to report **serious incidents** to the relevant market surveillance authority.

| Question | Detail |
|----------|--------|
| **What is a serious incident?** | An incident leading (directly or indirectly) to death or serious harm to health, serious disruption of critical infrastructure, breach of fundamental rights obligations, or serious harm to property or environment |
| **Who reports?** | The provider (and deployers must inform the provider) |
| **How fast?** | Without undue delay, within the timeframe the Act and national authority specify (tight — measured in days, faster for the most serious) |
| **Coordinate with** | Legal, Compliance Officer, DPO (if personal data), and existing breach-notification processes (GDPR has its own 72-hour rule) |

**Do not sit on a potential serious incident.** If in doubt whether it qualifies, escalate to Legal and Compliance immediately. Late or absent notification is itself a breach, and misleading a regulator compounds it.

---

## 6. Roles in Incident Response

| Role | Responsibility |
|------|----------------|
| **AI Governance Lead** | Coordinates the response; classifies severity; convenes the team |
| **AI System Owner** | Accountable for their system; leads containment and remediation decisions |
| **ML Engineering Lead** | Technical investigation and fix (model/pipeline) |
| **Data Steward** | Data investigation (drift, quality, poisoning); lineage tracing |
| **Compliance Officer** | Regulatory notification; liaison with authorities |
| **DPO** | Personal-data aspects; affected-person notification; GDPR interaction |
| **Legal** | Notification decisions; liability; external communication |
| **Tier 1 Committee** | Informed on SEV-1 within 24h; decides on system withdrawal if needed |

---

## 7. Incident Response Readiness Checklist

Prepared *before* an incident, not during:

- [ ] This playbook is accessible to all response roles
- [ ] Severity levels agreed and understood
- [ ] Response team roles assigned with named individuals and backups
- [ ] Escalation contacts current (including out-of-hours for SEV-1)
- [ ] Regulatory notification process understood and Legal aligned
- [ ] Communication templates ready to use
- [ ] Containment options assessed per system (can each system be paused? rolled back?)
- [ ] Link established from monitoring alerts to this playbook
- [ ] Post-mortem process defined
- [ ] A tabletop exercise run at least annually (practise before you need it)

---

## 8. The Principle

The best incident response plan is the one you built before you needed it and hoped never to use. AI systems will fail — models drift, edge cases surface, misuse happens. A mature governance function is not one that prevents all incidents (impossible) but one that detects them fast, contains them well, learns from them honestly, and can demonstrate to a regulator that it handled them responsibly. Your governance is only as good as this playbook is ready.
