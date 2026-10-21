# Case Study: Governing HR / People Analytics AI End-to-End (Candidate Screening & Internal Mobility)

> **Purpose:** The fourth case study in this repo, and the one most organisations will actually face. Very few companies build hiring AI; almost all of them buy it. This case follows a high-risk HR system through the framework from the **deployer's** side: the organisation that buys a vendor platform and becomes legally responsible for how it is used. It covers the Annex III classification, a prohibited feature hidden inside a bought product, a bias audit that finds two sources of discrimination risk, the Dutch works council, candidate transparency and appeals, and a vendor model update that silently disadvantages older candidates.
>
> **How to read it:** Follow the system from intake to board reporting. Each stage links to the artefact that governs it. Appendices A–D hold the reusable pieces: a bias audit methodology, a candidate transparency notice, a human review process and a board reporting format.
>
> **Simulated scenario.** Lindgracht MedTech and Corvane Talent Cloud are fictional. All figures are illustrative. This is a governance worked example, not legal advice. Employment, equality and data-protection positions must be confirmed with counsel in each jurisdiction.
>
> **Regulatory timeline (post-Omnibus):** Hiring and promotion systems are Annex III high-risk. Under the Digital Omnibus (Regulation (EU) 2026/1744), Annex III high-risk obligations apply from **2 December 2027**. Several obligations that bite on HR AI did not move: the Article 5 prohibitions, including emotion recognition in the workplace, have applied since **2 February 2025**; AI literacy duties apply; and GDPR and national employment law apply now. Lindgracht governs as if the high-risk regime were already live, because for this use case most of the hard law already is.

---

## The System

| Attribute | Detail |
|---|---|
| **Organisation** | Lindgracht MedTech B.V. — Netherlands-headquartered medical-technology group, ~7,000 employees across 9 EU countries plus a US subsidiary |
| **Hiring volume** | ~60,000 applications and ~1,400 external hires a year; ~600 internal moves |
| **AI system** | Corvane Talent Cloud — vendor SaaS bought by HR |
| **Module A — Screening** | Parses CVs, scores candidate–job match, ranks applicants for recruiters |
| **Module B — Internal mobility** | Ranks employees for internal vacancies and promotion pools |
| **Module C — "Interview Insights"** | Analyses recorded video interviews; produces "engagement" and "confidence" scores from facial expressions and voice |
| **Module D — Written assessment** | Scores candidates' written answers for "communication style" |
| **Users** | Recruiters, hiring managers, HR business partners |
| **Affected persons** | External candidates and current employees |
| **Operator roles** | Corvane = provider. Lindgracht = deployer. |

---

## Stage 1 — Intake and Classification

*Artefact: [`intake-form.md`](../6_templates/intake-form.md)*

**Prohibited practices check (Article 5) — failed on Module C.** Interview Insights infers emotional states from candidates' faces and voices. Article 5(1)(f) prohibits AI systems that infer emotions in the workplace, except for medical or safety reasons, and the Commission's guidelines on prohibited practices (February 2025) read "workplace" broadly enough to cover candidates in a recruitment process. Because the module works on biometric data (facial expressions, voice), it falls within the Article 3(39) definition of an emotion recognition system. It cannot be used.

*Module D is different.* It scores written text, not biometric data, so it is not an emotion recognition system under Article 3(39). It is not prohibited, but it carries its own discrimination risk (Stage 6).

**High-risk classification (Annex III).** Module A falls under Annex III point 4(a): AI intended to analyse and filter applications and evaluate candidates. Module B falls under point 4(b): decisions affecting promotion and the allocation of work. The Article 6(3) exemption was considered and rejected. An Annex III system that profiles natural persons is always high-risk, and both modules profile.

**Operator role.** Lindgracht is a deployer. It would become a *provider* under Article 25 if it put its own name on the system, substantially modified it, or changed its intended purpose. That risk becomes live in Stage 5.

**Applicable law (initial map).** EU AI Act; GDPR; Dutch Works Councils Act (WOR); EU and Dutch equal-treatment law; NYC Local Law 144 if the US subsidiary uses the tool for New York City roles.

Considered and documented as out of scope: the DMA, because its obligations fall on designated gatekeepers rather than on an employer that recruits through their platforms; and SOx, because the system's outputs do not feed financial reporting.

**Data governance readiness (intake Section 4).**

| Capability | Status |
|---|---|
| Data owner | ✓ Head of Talent Acquisition |
| Data catalogued | Partial — application fields catalogued; vendor-derived features not |
| Data quality measured | ✗ CV parsing quality never measured |
| Lineage documented | ✗ Vendor's parse → feature → score pipeline undocumented |

**Intake outcome:** High-risk, with one prohibited module. Two gates before anything else proceeds: Module C switched off and verified, and CV parsing quality measured before the bias audit.

---

## Stage 2 — Removing the Prohibited Feature

*Artefacts: [`vendor-governance-framework.md`](../8_tooling/vendor-governance-framework.md), [`ai-tool-evaluation-rubric.md`](../8_tooling/ai-tool-evaluation-rubric.md)*

Module C had been enabled by default in the vendor's "Professional" tier. Nobody at Lindgracht had chosen to run emotion recognition. It came bundled.

Actions taken:

- **Contract:** an amendment removing Module C from the subscription and prohibiting re-enablement without written governance approval.
- **Technical verification:** a configuration export and test-account walkthrough confirming the module is unavailable, not merely hidden.
- **Data:** written confirmation from the vendor that any interview analysis already produced for Lindgracht candidates has been deleted.
- **Procurement rule:** any new vendor module now requires a governance intake before activation.

**The lesson:** prohibited practices rarely arrive as a project called "emotion recognition". They arrive as a feature toggle in a product you have already bought.

---

## Stage 3 — Regulatory Landscape: What Applies, and When

*Artefact: [`eu-ai-act-controls-map.md`](../4_eu-ai-act/eu-ai-act-controls-map.md)*

| Obligation | Source | Applies to Lindgracht? | When |
|---|---|---|---|
| No emotion recognition in the workplace, including candidates | AI Act Art 5(1)(f) | Yes — Module C removed | Since 2 Feb 2025 |
| AI literacy for staff operating the system | AI Act Art 4 (as revised by the Omnibus) | Yes — recruiters and HRBPs trained | In force |
| Deployer duties: use per instructions, competent human oversight, relevant input data, monitoring, informing the provider of risks and serious incidents, log retention (at least six months) | AI Act Art 26(1)–(6) | Yes | 2 Dec 2027 — implemented now |
| Inform workers' representatives and affected workers before workplace use | AI Act Art 26(7) | Yes — internal mobility module | 2 Dec 2027 — done now |
| Inform people that a high-risk system is used in decisions about them | AI Act Art 26(11) | Yes — candidates and employees | 2 Dec 2027 — done now |
| Right to an explanation of the AI system's role in an individual decision | AI Act Art 86 | Yes | 2 Dec 2027 — designed in now |
| Exceptional legal basis to process special-category data for bias detection | AI Act Art 4a (added by the Omnibus) | Available, not mandatory | Option under strict conditions |
| Safeguards on solely automated decisions | GDPR Art 22 (and CJEU *SCHUFA*, C-634/21) | Yes — shapes the oversight design | Now |
| Data protection impact assessment | GDPR Art 35 | Yes — systematic evaluation and profiling of applicants | Now |
| Transparency to candidates and employees | GDPR Arts 13–14 | Yes | Now |
| Works council consent | Dutch WOR Art 27 | Very likely — recruitment and promotion policy, employee data, performance-related systems. Confirm with counsel. | Now |
| Non-discrimination (sex, age, racial or ethnic origin, disability and other grounds) | Directives 2006/54/EC, 2000/78/EC, 2000/43/EC; Dutch equal-treatment legislation | Yes | Now |
| Fundamental rights impact assessment | AI Act Art 27 | Not mandatory: Lindgracht is a private employer, not a public body or public-service provider, and this is not an Annex III 5(b)/(c) use. A voluntary rights review is folded into the DPIA. | — |
| Independent bias audit, public summary, candidate notice 10 business days before use | NYC Local Law 144 | Only if the US subsidiary uses the tool for NYC roles | Now (US) |

**The headline:** the AI Act's high-risk clock moved to December 2027. The emotion-recognition ban, GDPR, equality law and the works council did not.

---

## Stage 4 — Stakeholder Impact Assessment

| Stakeholder | How affected | Main risk | Voice in governance |
|---|---|---|---|
| External candidates (~60,000/yr) | Screened and ranked | Unfair exclusion; opaque rejection | Notice, explanation, human review route |
| Employees (internal mobility) | Ranked for internal roles and promotion pools | Career harm; perceived surveillance | Works council; notice; review route |
| Women in engineering roles | Scored on experience history | Career-gap penalties | Bias audit dimension |
| Candidates aged 50+ | Scored on qualifications and experience | Age proxies (graduation year, "recency") | Bias audit dimension |
| Candidates educated outside the EU | CVs parsed and scored | Parse failures; written-style scoring | Bias audit dimension |
| Disabled candidates | Assessment formats | Inaccessible formats; timed tasks | Reasonable-adjustment route |
| Recruiters and hiring managers | Oversee the ranking | Automation bias; workload | Training; oversight design |
| Works council (ondernemingsraad) | Represents employees | — | Consent; Art 26(7) information |
| DPO | Owns data protection review | — | Owns the DPIA |
| Corvane (vendor) | Provider | — | Contract, documentation, change notification |
| Supervisory authorities | — | — | Evidence pack on request |

---

## Stage 5 — Data Governance Before the Bias Audit

*Artefacts: [`data-governance-dependency-map.md`](../2_risk-and-controls/data-governance-dependency-map.md), [`data-governance-baseline.md`](../3_scorecards/data-governance-baseline.md)*

**Decision 1 — no calibration on historical hiring decisions.** Corvane offered to "calibrate the model to your best hires" using five years of Lindgracht's hiring outcomes. Governance declined, for two reasons.

First, historical decisions encode historical bias. That is the pattern behind Amazon's experimental recruiting model, scrapped after it learned from a decade of male-dominated CVs to downgrade applications mentioning "women's".

Second, depending on how it was done, calibration could amount to a substantial modification under Article 25, turning Lindgracht into a provider with full provider obligations. The question was referred to counsel and the offer declined in the meantime. Scoring is driven instead by structured, job-related requirements that hiring managers own.

**Decision 2 — define and catalogue the inputs.** In scope: CV text, application-form answers and structured job requirements. Excluded from scoring: photo, date of birth, nationality and address/postcode. Excluding a field does not remove its proxies. Graduation year still appears in CV text and is tracked as an age proxy.

**Data quality: the first fairness finding was a data finding.** Nobody had measured how well the vendor parsed CVs. The HR Data Steward measured it.

| Group | CV parse failure rate (simulated) |
|---|---|
| All applications | 6.1% |
| Two-column or designed PDF layouts | 14.8% |
| Candidates educated outside the EU | 11.9% |

A failed parse produced a near-empty profile, and a near-empty profile produced a low match score. Candidates were being ranked down for the layout of their CV and where they had studied, not for their fit. A data quality problem had become a fairness problem.

**Lineage.** Corvane supplied its instructions for use (Article 13) and feature documentation. Lindgracht documented its own configuration lineage: job requirements → weights → ranking. The HR Data Steward now owns a parse-quality KPI.

---

## Stage 6 — Risk Assessment

*Artefact: [`risk-register.md`](../6_templates/risk-register.md)*

| ID | Risk | L | I | Score | Rating | Treatment |
|---|---|---|---|---|---|---|
| HR-01 | Prohibited practice bundled in vendor product (Module C) | 5 | 5 | 25 | Critical | **Eliminate** — module removed and verified |
| HR-02 | "Continuous experience" feature penalises career gaps: indirect sex discrimination risk | 4 | 5 | 20 | Critical | Mitigate — remove penalty; requirement-based scoring |
| HR-03 | Parse failures rank down non-standard CVs and non-EU-educated candidates | 4 | 4 | 16 | Critical | Mitigate — exception queue: hold unscored, show the reason, recruiter reviews the original CV |
| HR-04 | Recruiters rubber-stamp the ranking, so the ranking becomes the decision (GDPR Art 22) | 4 | 4 | 16 | Critical | Mitigate — oversight design, sampling, metrics |
| HR-05 | Age proxies (graduation year, qualification recency) | 3 | 4 | 12 | High | Mitigate — feature review; age-band monitoring |
| HR-06 | Written-style scoring (Module D) disadvantages non-native speakers | 3 | 4 | 12 | High | Mitigate — disable where written English is not an essential job requirement |
| HR-07 | Vendor changes the model without notice | 3 | 4 | 12 | High | Mitigate — change-notification clause; version pinning |
| HR-08 | Employee distrust of internal mobility ranking | 3 | 3 | 9 | Medium | Mitigate — works council involvement; transparency |

---

## Stage 7 — The Bias Audit

*Full method in [Appendix A](#appendix-a--bias-audit-methodology).*

**What was measured.** Selection rates at the shortlisting stage by group, and the **selection-rate ratio** for each group: its rate divided by the rate of the most-selected group. Where a structured human re-review provided a "qualified" reference set, an **equal-opportunity** check compared shortlisting rates among qualified candidates.

**Where the group data came from.** Sex and age band came from a voluntary equality-monitoring survey, stored separately from the hiring system, access-restricted and never used by the model. Education country and CV layout came from application data. Ethnicity was not collected for this cycle.

Article 4a, added by the Omnibus, gives deployers of high-risk systems an exceptional legal basis to process special-category data where strictly necessary for bias detection, under strict safeguards and with no obligation to do so. Lindgracht documented the option as considered and not used this cycle, to be revisited if other signals point that way. Any future use would sit inside the DPIA.

**The threshold.** A ratio below 0.80 triggers investigation. The figure is borrowed from the US "four-fifths" rule of thumb and used as a trigger, not a pass mark. EU equality law has no numeric safe harbour, so a ratio above 0.80 does not make a disparity lawful.

**Findings (simulated):**

| Group (comparison) | Selection-rate ratio | Root cause |
|---|---|---|
| Women, engineering roles | 0.71 | "Continuous experience" feature penalised gaps of 12+ months |
| Candidates educated outside the EU, all roles | 0.76 | Parse failures (Stage 5) |
| Candidates aged 50+, all roles | 0.84 | Above trigger; graduation-year proxy watched |

**Fixes:** the career-gap penalty was removed and scoring re-based on job requirements; parse failures now go to an exception queue, where the candidate is held unscored, the reviewer sees the reason (for example, "CV could not be parsed: layout"), and a recruiter reviews the original CV before any decision; and Module D was disabled for roles where written English is not essential.

**Re-test (simulated):** women in engineering 0.93; non-EU-educated 0.91; aged 50+ 0.88. The equal-opportunity check on the human re-review sample showed qualified candidates shortlisted at comparable rates across groups.

**The fairness choice, documented.** When base rates differ between groups, common fairness criteria cannot all hold at once. Lindgracht chose selection-rate parity as the screening signal and equal opportunity among qualified candidates as the outcome standard. It did not use calibration against job performance, because performance data arrives years later and is itself shaped by who was hired. The Tier 2 working group signed off the choice. Which fairness metric to use is a governance decision, not a technical default.

---

## Stage 8 — Human Oversight, Transparency and Contestability

**Human oversight.** The system ranks; people decide. There is no automated rejection: every shortlist and every rejection is a recruiter decision.

That design matters for GDPR Article 22. In *SCHUFA* (C-634/21, 2023), the CJEU held that a score can itself be an automated decision where the decision-maker draws strongly on it. By the same logic, a ranking that recruiters rubber-stamp risks becoming one. So oversight is built to be real, not ceremonial:

- recruiters see the main factors behind each ranking, not just a number;
- a weekly 5% random sample of below-cutoff candidates is re-reviewed by a second recruiter;
- override rates and review times are monitored for rubber-stamping;
- recruiters complete AI literacy training (Article 4) before getting access.

**Transparency.**

- Candidates and employees are told at the point of application that an AI system assists screening, what it does and does not do, and how to ask for a human review ([Appendix B](#appendix-b--candidate-transparency-notice-template)). This meets GDPR Articles 13–14 now and Article 26(11) from December 2027.
- The works council was informed before the internal mobility module went live (Article 26(7)), and its consent was sought under WOR Article 27 for the internal mobility module and the updated recruitment and promotion policy.

**Contestability.** Any candidate or employee can ask for a human review of an AI-assisted outcome, and for an explanation of the system's role and the main elements of the decision ([Appendix C](#appendix-c--human-review-and-appeals-process)). This anticipates Article 86 and is good practice under GDPR now.

---

## Stage 9 — Documentation and Accountability

*Artefacts: [`system-card-template.md`](../6_templates/system-card-template.md), [`ai-documentation-standard.md`](../6_templates/ai-documentation-standard.md), [`raci.md`](../1_framework/raci.md)*

- **System card** covering the vendor model, Lindgracht's configuration, recruiter review, the review route and the removed module.
- **Vendor documentation** (instructions for use under Article 13; model documentation) filed as the model evidence. Lindgracht does not author a model card for a model it did not build.
- **DPIA** under GDPR Article 35, including the voluntary fundamental-rights review.
- **Bias audit report**, signed off, with the documented fairness choice.
- **Works council file:** information provided, consent request and outcome.

**RACI for HR AI** (R = Responsible, A = Accountable, C = Consulted, I = Informed; one Accountable per row)

| Activity | Head of TA (AI System Owner) | HR Data Steward | DPO | Employment counsel | Works council | AI Governance Lead | Vendor | Recruiters |
|---|---|---|---|---|---|---|---|---|
| Remove prohibited module | A | I | C | C | I | R | R | I |
| DPIA | C | C | A/R | C | I | C | C | I |
| Bias audit | A | R | C | C | I | R | C | I |
| Works council information and consent | A | I | C | R | C | C | I | I |
| Candidate notice | A | I | R | C | I | C | I | I |
| Human review requests | A | I | C | C | I | I | I | R |
| Fairness monitoring | A | R | I | I | I | R | C | C |
| Incident escalation | A | C | C | C | I | R | C | I |

---

## Stage 10 — Monitoring with Fairness KPIs

*Artefacts: [`ai-monitoring-playbook.md`](../7_monitoring-incident/ai-monitoring-playbook.md), [`governance-cadence.md`](../1_framework/governance-cadence.md)*

| KPI | Trigger | Frequency | Owner |
|---|---|---|---|
| Selection-rate ratio by sex, age band and education origin, per role family | Below 0.80 | Monthly for six months, then quarterly | AI System Owner + HR Data Steward |
| CV parse-failure rate by layout and education origin | Gap of 2+ percentage points versus overall | Weekly | HR Data Steward |
| Exception queue: oldest unreviewed parse failure | Older than 3 working days | Daily | TA operations |
| Recruiter override rate | Below 2% (possible rubber-stamping) or above 40% (ranking not useful) | Monthly | TA operations |
| Below-cutoff sample: share a second recruiter would have shortlisted | Above 10% | Weekly | TA operations |
| Human review requests and outcomes | Any overturned decision triggers root-cause analysis | Monthly | DPO |
| Vendor model version | Any change without notice is an incident | Continuous | Vendor manager |
| Score distribution drift | Population Stability Index above 0.25 | Monthly | AI Governance Lead |

In hiring, monitoring is the main line of defence. Rejected candidates rarely complain; most simply move on. In the GenAI case a customer surfaced the error. A discriminatory screening pattern can run for months without a single complaint.

---

## Stage 11 — Incident: A Silent Vendor Update (Simulated)

*Artefact: [`ai-incident-response-playbook.md`](../7_monitoring-incident/ai-incident-response-playbook.md)*

Four months after go-live, the monthly fairness report shows the selection-rate ratio for candidates aged 50+ in sales roles falling from 0.88 to 0.69 over three weeks. Corvane's release notes, checked afterwards, show a model update that increased the weight on "recency of qualifications", a feature that correlates with age. Lindgracht had received no advance notice, despite the change-notification clause.

**Detection.** Monitoring caught it. No candidate had complained.

**Triage.** Could this be a serious incident? The AI Act's definition includes an infringement of Union-law obligations intended to protect fundamental rights (Article 3(49)(c)), and EU employment equality law prohibits age discrimination. Lindgracht treated it as SEV-1 pending legal assessment and escalated to Legal and the DPO the same day. Classification and the reporting clock run in parallel, so the triage gate is biased toward escalating early.

From December 2027, Article 26(5) requires a deployer that identifies a serious incident to inform the provider immediately and then the relevant authorities; Article 73 reporting sits primarily with the provider. Lindgracht's contract already required both, so it acted on them now.

**Containment.** AI ranking was paused for sales roles; recruiters screened manually; the vendor was asked to roll back.

**Investigation.** Vendor version history and Lindgracht's own logs (retained under Article 26(6)) reconstructed the affected window: 1,140 candidates aged 50+ had been ranked below the cutoff during those three weeks (simulated).

**Remediation.** The vendor rolled back the update. Every affected candidate was re-reviewed by a recruiter, and 37 who would otherwise have been screened out were invited to interview (simulated). The vendor's breach of the change-notification clause triggered the contractual remedy.

**Post-mortem: two new controls.**

1. **Version pinning.** Lindgracht's tenant stays on an approved model version until governance signs off a new one.
2. **Pre-release bias regression.** Before any new version goes live, Lindgracht runs its fairness checks against the vendor's staging environment on a held-out sample.

**The lesson:** with bought AI, your governance is only as strong as your change control over someone else's model.

---

## Stage 12 — Board Reporting and Maturity

*Artefact: [`maturity-model.md`](../2_risk-and-controls/maturity-model.md); board format in [Appendix D](#appendix-d--board-level-reporting-format)*

The HR AI system is reported to the board quarterly on one page (Appendix D).

Maturity assessment after the first six months:

| Domain | Level |
|---|---|
| Governance structure and accountability | 3 |
| Risk management | 3 |
| Regulatory compliance | 2 |
| Documentation and evidence | 2 |
| Monitoring and operations | 3 |
| Human oversight and AI literacy | 2 |
| Data ownership and accountability | 3 |
| Metadata management | 2 |
| Data quality measurement | 2 |
| Data cataloguing adoption | 2 |
| **Overall (lowest domain)** | **2** |

Strong monitoring did not lift the overall score, because overall maturity is the lowest domain. The next target is Level 3 in data quality and documentation before Annex III obligations apply in December 2027.

---

## What This Case Study Demonstrates

1. **Bought AI is still your AI.** Most organisations are deployers of HR AI, not providers. Article 26 makes the deployer responsible for oversight, input data, monitoring, logs, worker information and transparency. None of that can be outsourced to the vendor's brochure.
2. **Prohibited practices hide in feature toggles.** The highest-severity risk in this case was a default setting.
3. **Fairness is a governance choice.** Which metric, which threshold and which data were each decided, documented and signed off, not left to a vendor default.
4. **The data thesis holds again.** One of the two discrimination findings came from a CV parser, not the ranking model.
5. **The deadline moved; most of the law didn't.** Treating December 2027 as the start date would have left Lindgracht running a prohibited feature and an unaudited screening system, exposed under GDPR, equality law and the works council's rights.
6. **In hiring, monitoring is the main defence.** The people harmed by a biased screen rarely see it, so they rarely complain.

---

## How It Compares to the Credit Scoring Case

| | Credit scoring | HR / people analytics |
|---|---|---|
| Annex III category | 5(b) — creditworthiness | 4(a)/(b) — recruitment, promotion |
| Who built the model | The lender | A vendor; Lindgracht is the deployer |
| Main governance lever | Own data and model | Contract, configuration and oversight |
| FRIA (Art 27) | Mandatory for deployers of Annex III 5(b) systems | Not mandatory for a private employer |
| Data finding | Missing lineage and quality measurement | CV parse failures |
| Incident | Data-provider schema change | Vendor model update without notice |

---

## Try It Yourself

1. Run the [`intake-form.md`](../6_templates/intake-form.md) and check **every module** against Article 5 before anything else.
2. Classify under Annex III point 4. Don't rely on Article 6(3) if the system profiles people.
3. Measure input data quality by group before the bias audit ([`data-governance-baseline.md`](../3_scorecards/data-governance-baseline.md)).
4. Run the bias audit in Appendix A and document your fairness choice.
5. Map the works council, GDPR and equality law alongside the AI Act. They apply now.
6. Put change control over the vendor's model into the contract ([`vendor-governance-framework.md`](../8_tooling/vendor-governance-framework.md)).

---

## Appendix A — Bias Audit Methodology

1. **Define the decision points.** Application → shortlist; shortlist → interview; internal pool → selection. Audit each separately. Disparities can enter at any stage, including the human ones.
2. **Define groups and lawful data sources.** Use voluntary equality-monitoring data stored separately from the hiring system, with restricted access and never used for decisions. Start with dimensions that are not special-category data (sex, age band, education country, CV format). Use Article 4a for special-category data only where strictly necessary, under its safeguards and inside the DPIA, and delete the data once the bias is corrected.
3. **Check sample sizes.** Don't report ratios for very small groups in a single period. Pool across periods or role families and report the uncertainty.
4. **Compute selection rates and ratios**, including intersectional groups such as women aged 50+.
5. **Test significance and practical size.** Use a statistical test (Fisher's exact or chi-square) alongside the ratio. A ratio near the trigger on 40 candidates means something different from the same ratio on 4,000.
6. **Find the root cause.** Review features for proxies (career gaps, graduation year, postcode, names, school prestige); review data quality by group (parse failures, missing fields); and review the human stages (interview pass rates).
7. **Check equal opportunity** on a structured human re-review sample where a "qualified" reference is available.
8. **Remediate, re-test and document.** Record the findings, fixes, re-test results and fairness-metric choice, and get Tier 2 sign-off.
9. **Set cadence and triggers.** Monthly for the first six months, then quarterly, and after every vendor model change.
10. **Compare with external standards where they apply.** NYC Local Law 144 requires an independent audit within the year before use, a public summary and candidate notice. EU law has no equivalent publication requirement, but supervisors and works councils will ask for the same evidence.

---

## Appendix B — Candidate Transparency Notice (Template)

> **How we use AI in our recruitment process**
>
> We use an AI system supplied by **[vendor]** to help our recruiters review applications for **[role family]**. Here is what that means for you.
>
> **What the system does.** It reads your CV and application answers and compares them with the requirements of the role. It suggests an order in which our recruiters review applications.
>
> **What it does not do.** It does not make decisions: a recruiter decides who is shortlisted and who is not. It does not analyse your face, voice or emotions. It does not use your photo, date of birth, nationality or address.
>
> **What information it uses.** **[List: CV text, application answers, job requirements]**.
>
> **Your rights.** You can ask for a person to review any decision about your application, and ask how the AI system was used and the main reasons for the decision. You also have rights under data protection law, including access to your data, correction and objection. **[Add GDPR Article 22 wording reviewed by your DPO.]**
>
> **How to ask for a review.** **[Link or email]**. We will acknowledge your request within **[5]** working days and respond within **[15]** working days.
>
> **Questions about your data.** Contact our Data Protection Officer at **[contact]**. We keep application data for **[retention period]**.
>
> **Adjustments.** If you need an adjustment to any part of our process, tell us at **[contact]**.

---

## Appendix C — Human Review and Appeals Process

| Element | Design |
|---|---|
| Who can request | Any candidate or employee affected by an AI-assisted outcome |
| How | A link in the rejection message, email or the HR portal; no reason required |
| Timescales | Acknowledge within 5 working days; outcome within 15 (illustrative) |
| Reviewer | A trained recruiter who did not make the original decision |
| How the review runs | The reviewer reads the application first **without** the AI ranking, then sees the ranking and its main factors |
| Possible outcomes | Upheld; overturned (the candidate progresses); referred (for example, to a hiring manager or for an adjustment) |
| What the explanation covers | The AI system's role in the process; the main elements of the decision; what the person can do next |
| Record-keeping | Every request, outcome and reason logged |
| Feedback loop | Any overturned decision triggers a root-cause check; review volumes and outcomes are monitored |
| Protections | No adverse treatment for asking; accessible formats available |

---

## Appendix D — Board-Level Reporting Format

> **AI in HR — Quarterly Board Report** (one page)
>
> **System and risk tier:** Corvane Talent Cloud — Annex III high-risk (recruitment, internal mobility)
>
> **Overall status:** Green / Amber / Red, with a one-line reason
>
> **Fairness this quarter:** selection-rate ratios by monitored group against the 0.80 trigger; any group below the trigger and the action taken
>
> **Oversight health:** override rate; below-cutoff sample result; human review requests (received / upheld / overturned)
>
> **Incidents:** number by severity; any serious-incident assessment and its outcome
>
> **Vendor:** model versions approved this quarter; any contract breaches
>
> **Readiness for 2 December 2027:** share of Annex III deployer obligations evidenced; gaps and owners
>
> **Top three risks:** from the risk register, with trend
>
> **Decisions requested from the board:** for example, approval of a new module, budget for an independent audit, or a risk acceptance
>
> **Next quarter:** planned audits, works council engagements and training
