# AI Tool Evaluation Rubric

> **Purpose:** A governance-first scoring rubric for evaluating AI tools and platforms before you buy them. Most tool evaluations are feature checklists — "does it do X?" This rubric asks the questions that actually determine whether a tool is safe, compliant, and defensible to deploy: how does it handle bias, transparency, data privacy, security, and regulatory obligations? A tool can win on features and still be a governance liability.
>
> **When to use:** Any time you're evaluating an AI/ML tool, platform, or AI-enabled SaaS for procurement — whether it's a model-monitoring platform, an LLM API, a vendor AI product, or an AI feature bolted onto existing software.
>
> **Owner:** AI Governance Lead facilitates the scoring; Procurement, Security, DPO, and the requesting business team contribute.
>
> **How it works:** Score each criterion 0–4. Weight by importance to your use case. The weighted total gives a comparable score across tools — but the veto conditions (Section 4) can disqualify a tool regardless of score.

---

## 1. Scoring Scale

| Score | Meaning |
|-------|---------|
| **0** | Absent — the tool does not address this at all |
| **1** | Minimal — addressed superficially or with significant gaps |
| **2** | Adequate — meets baseline expectations |
| **3** | Strong — exceeds baseline, well-documented |
| **4** | Excellent — best-in-class, verifiable, exceeds requirements |

---

## 2. The Evaluation Categories

Eight categories, each with sub-criteria. The weights below are defaults — adjust them to your use case (a high-risk system weights governance and fairness higher; an internal productivity tool weights integration and cost higher).

### Category 1 — Governance & Compliance (default weight: 20%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| EU AI Act alignment | Does the vendor understand and support AI Act obligations? Do they state their operator role (provider/deployer)? | |
| Documentation provided | Does the vendor supply model cards, system documentation, or Annex IV-relevant material? | |
| Conformity support | For high-risk uses, can the vendor support conformity assessment and provide required documentation? | |
| Regulatory roadmap | Does the vendor track and adapt to regulatory change (Omnibus, standards)? | |
| Certifications | ISO 42001, SOC 2, or equivalent management-system certifications | |

### Category 2 — Bias & Fairness (default weight: 15%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| Bias testing | Does the tool test for or support testing of bias across groups? | |
| Fairness metrics | Are fairness metrics available and configurable? | |
| Representative data | For pre-trained models, is training data documented and representative? | |
| Bias mitigation | Does the tool support fairness constraints or bias remediation? | |

### Category 3 — Transparency & Explainability (default weight: 12%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| Explainability | Can the tool explain its outputs (feature importance, reasoning)? | |
| Model transparency | Is the model architecture and behaviour documented, or is it a black box? | |
| Disclosure support | Does it support Article 50 transparency (AI disclosure, content marking)? | |
| Auditability | Can decisions be reconstructed and audited? | |

### Category 4 — Security (default weight: 15%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| AI-specific security | Protection against data poisoning, model extraction, adversarial inputs, prompt injection | |
| Access controls | Role-based access, least-privilege, authentication | |
| Vulnerability management | Patching cadence, security disclosures, pen-test history | |
| Incident history | Track record of breaches and how they were handled | |

### Category 5 — Data Privacy (GDPR) (default weight: 15%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| Data processing terms | Clear DPA; is customer data used for vendor model training? (Should be opt-out or no) | |
| Data residency | Where is data stored and processed? EU data residency available? | |
| Data minimisation | Does the tool support minimising personal data processed? | |
| Data subject rights | Can it support access, erasure, and Article 22 rights? | |
| Sub-processors | Are sub-processors disclosed and governed? | |

### Category 6 — Performance & Reliability (default weight: 10%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| Accuracy / quality | Documented performance on relevant benchmarks | |
| Reliability | Uptime SLA, latency, failure handling | |
| Monitoring support | Does it support or integrate with monitoring (drift, performance)? | |
| Scalability | Does it scale to your volume? | |

### Category 7 — Integration (default weight: 8%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| API quality | Well-documented, stable API | |
| Ecosystem fit | Integrates with your MLOps / data stack | |
| Export / portability | Can you get your data and configs out? (Avoids lock-in) | |
| Implementation effort | Realistic time-to-value | |

### Category 8 — Cost & Commercial (default weight: 5%)

| Criterion | What to look for | Score (0–4) |
|-----------|------------------|-------------|
| Total cost of ownership | Licensing + implementation + ongoing, not just headline price | |
| Pricing transparency | Clear, predictable pricing | |
| Contract flexibility | Exit terms, scaling terms, no punitive lock-in | |
| Vendor viability | Is the vendor financially stable and likely to persist? | |

---

## 3. Scoring Worksheet

| Category | Weight | Avg score (0–4) | Weighted score |
|----------|--------|-----------------|----------------|
| 1. Governance & Compliance | 20% | | |
| 2. Bias & Fairness | 15% | | |
| 3. Transparency & Explainability | 12% | | |
| 4. Security | 15% | | |
| 5. Data Privacy (GDPR) | 15% | | |
| 6. Performance & Reliability | 10% | | |
| 7. Integration | 8% | | |
| 8. Cost & Commercial | 5% | | |
| **Total** | **100%** | | **/4.0** |

**Interpretation:**

| Weighted total | Verdict |
|----------------|---------|
| 3.0 – 4.0 | Strong — proceed to PoC / contract |
| 2.0 – 2.9 | Adequate — proceed with documented mitigations for weak areas |
| 1.0 – 1.9 | Weak — significant governance gaps; reconsider or require remediation |
| Below 1.0 | Reject |

---

## 4. Veto Conditions (Automatic Disqualification)

Some failures disqualify a tool regardless of how well it scores elsewhere. If any of these is true, the tool fails — a high feature score cannot compensate:

- [ ] Vendor uses your data to train its models without consent, and won't stop
- [ ] No Data Processing Agreement available (and personal data is involved)
- [ ] Vendor cannot or will not provide documentation needed for your compliance obligations (for high-risk uses)
- [ ] No EU data residency option where your data sovereignty requirements demand it
- [ ] Known unresolved security vulnerability or unhandled breach history
- [ ] Vendor supports a prohibited practice (Article 5) as a core function
- [ ] No exit path — total lock-in with no data portability

A veto condition is a governance red line. Document it and move on.

---

## 5. How to Use This in a Real Evaluation

1. **Adjust the weights** to your use case before scoring. A high-risk system weights governance, fairness, and privacy heavily. An internal minimal-risk tool weights integration and cost more.
2. **Score independently, then reconcile.** Have Security score the security category, DPO score privacy, governance score compliance. Reconcile differences in discussion — the disagreements are informative.
3. **Check veto conditions first.** No point scoring a tool in detail if it fails a red line.
4. **Compare weighted totals across shortlisted tools** — but let the veto conditions and the governance category (not the feature categories) drive the final call.
5. **Feed the result into the vendor governance framework** (next artefact) for the tools that pass.

The point of this rubric is to make the governance dimensions of a tool decision as rigorous as the feature comparison usually is. Most bad AI procurement decisions aren't made because the tool lacked features — they're made because nobody scored the governance until it was too late.
