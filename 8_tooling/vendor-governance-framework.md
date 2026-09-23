# Vendor Governance Framework

> **Purpose:** Governs third-party AI across its whole lifecycle with you — from due diligence before you buy, through contractual protections, to ongoing monitoring and eventual exit. Most organisations' AI risk doesn't live in models they built; it lives in models they bought. The EU AI Act makes this explicit: deployers of third-party high-risk AI inherit obligations, and importers/distributors have their own duties. If you can't govern your AI supply chain, you can't govern your AI.
>
> **When to use:** For every AI system, tool, or AI-enabled service provided by a third party — from a foundation-model API to an AI feature inside a SaaS product.
>
> **Owner:** Procurement + AI Governance Lead jointly; Legal, Security, and DPO contribute.
>
> **Relationship to other artefacts:** Follows the tool evaluation rubric (which decides *whether* to engage a vendor); this framework governs the relationship once you do.

---

## 1. Why Vendor AI Is a Distinct Governance Problem

When you build a model, you control the data, the training, the documentation, and the monitoring. When you buy one, you control none of that directly — you depend on the vendor for it. This shifts the governance problem:

- **You can't inspect what you can't see.** Vendor models are often black boxes. Your governance depends on what the vendor discloses.
- **You inherit obligations you can't fully discharge alone.** As a deployer of high-risk AI, you owe Article 26 obligations — but satisfying them requires vendor cooperation (documentation, transparency, support).
- **The vendor can change the system under you.** An API model can be updated without notice, changing behaviour your governance assessed.
- **The risk surface is the contract.** With vendor AI, your primary governance lever is the contract — audit rights, documentation obligations, change notification, exit terms. What you didn't negotiate, you don't have.

---

## 2. The Vendor Governance Lifecycle

```
Due Diligence  →  Contracting  →  Onboarding  →  Ongoing Monitoring  →  Renewal / Exit
   (assess)       (protect)       (integrate)      (verify)             (transition)
```

---

## 3. Stage 1 — Due Diligence Checklist

Before engaging, assess the vendor across these dimensions. (This complements the tool evaluation rubric — the rubric scores the tool; this assesses the vendor as an organisation.)

### Vendor organisation
- [ ] Financial stability and viability (will they exist in 3 years?)
- [ ] Track record and references in your sector
- [ ] Security posture (SOC 2, ISO 27001, pen-test history)
- [ ] Management-system certifications (ISO 42001 for AI)
- [ ] Incident and breach history, and how handled

### AI-specific
- [ ] Model documentation available (cards, training data summary, limitations)
- [ ] Bias testing and fairness approach documented
- [ ] EU AI Act operator role stated (provider/deployer/distributor)
- [ ] Support for your compliance obligations (documentation, transparency)
- [ ] Model change/versioning and notification policy

### Data & privacy
- [ ] Data Processing Agreement available and adequate
- [ ] Clear position on using your data for their model training
- [ ] Data residency and sub-processor transparency
- [ ] GDPR compliance demonstrated

### Deliverable
A due diligence report with a go/no-go recommendation, feeding the contracting stage.

---

## 4. Stage 2 — Contractual Requirements

The contract is where vendor governance is won or lost. What you don't secure here, you don't have later. Require:

| Requirement | Why | What to secure |
|-------------|-----|----------------|
| **Documentation obligations** | You need it for your compliance | Vendor commits to provide and maintain model/system documentation sufficient for your AI Act obligations |
| **Transparency** | Article 13/50 duties | Vendor discloses model capabilities, limitations, intended use, known risks |
| **Audit rights** | Verify, don't trust | Right to audit the vendor's AI governance, or receive third-party audit reports |
| **Change notification** | The model can change under you | Vendor notifies you of material model changes before they take effect, with time to reassess |
| **Data processing terms** | GDPR + your data protection | DPA; explicit terms on training use, residency, retention, deletion, sub-processors |
| **Performance / SLA** | Reliability and accuracy | Defined performance levels, uptime, support response |
| **Incident cooperation** | Article 73, breach response | Vendor cooperates in incident investigation and regulatory notification; timely breach notification to you |
| **Liability & indemnity** | Allocate risk | Clear liability allocation for AI failures, IP infringement, data breaches |
| **Exit & portability** | Avoid lock-in | Data export, transition assistance, defined exit terms |
| **Regulatory cooperation** | You may face inspection | Vendor supports your regulatory engagement and provides evidence when needed |

**The negotiating principle:** for a high-risk use, if the vendor won't commit to documentation, audit rights, and change notification, you cannot demonstrate compliance — which means you can't use them for high-risk regardless of how good the tool is. These aren't nice-to-haves; they're the difference between a governable and an ungovernable dependency.

---

## 5. Stage 3 — Onboarding

Once contracted, integrate the vendor system into your governance:

- [ ] Register the vendor system in your AI inventory with risk classification
- [ ] Complete an intake form for the use case (treat vendor AI like any AI system)
- [ ] Produce a system card documenting how the vendor component fits your pipeline
- [ ] Establish monitoring — including vendor-provided metrics AND your own independent checks
- [ ] Assign an internal owner accountable for the vendor relationship and its governance
- [ ] Document the division of responsibility (what the vendor governs vs what you govern)

---

## 6. Stage 4 — Ongoing Monitoring

Vendor governance doesn't end at onboarding. Continuously:

| What to monitor | How |
|-----------------|-----|
| **Model changes** | Track vendor change notifications; reassess when the model materially changes |
| **Performance** | Monitor the vendor system's outputs independently — don't rely solely on vendor-reported metrics |
| **Compliance drift** | Confirm the vendor maintains certifications, DPA terms, and documentation currency |
| **Incident signals** | Watch for vendor security incidents, outages, or regulatory actions |
| **Contract adherence** | Periodically verify the vendor is meeting contractual governance commitments |
| **Vendor viability** | Watch for signals of financial or operational instability |

Review vendor AI on the governance cadence — at least annually, more often for high-risk dependencies.

---

## 7. Stage 5 — Renewal / Exit

Every vendor relationship ends eventually. Govern the transition:

**At renewal:**
- Re-run due diligence (has the vendor's risk profile changed?)
- Reassess against current regulation (has the AI Act, or your obligations, changed?)
- Renegotiate terms that proved inadequate

**At exit (planned or forced):**
- Execute the data portability and export provisions you negotiated
- Transition to the replacement with governance continuity (no gap in oversight)
- Confirm vendor data deletion per the contract
- Update the AI inventory and retire the system record

**Forced exit triggers:** vendor breach, unacceptable model change, loss of certification, financial failure, or a regulatory action against the vendor. Your exit strategy is only real if you can execute it under pressure — which is why portability must be contractual, not hoped-for.

---

## 8. Division of Responsibility (Provider vs Deployer)

Under the EU AI Act, when you deploy third-party high-risk AI, obligations split. Document clearly who owns what:

| Obligation | Typically Provider (vendor) | Typically Deployer (you) |
|------------|----------------------------|--------------------------|
| Technical documentation (Annex IV) | ✔ produces | receives, relies on |
| Risk management of the model | ✔ | monitors in your context |
| Data governance (training) | ✔ | governs your input data |
| Human oversight design | provides capability | ✔ implements and operates |
| Monitoring in deployment | provides tools | ✔ operates |
| Transparency to end users (Art 50) | enables | ✔ discharges |
| Incident reporting (Art 73) | ✔ for the model | informs provider; reports in your context |
| Use within intended purpose | defines | ✔ stays within |

The most dangerous gaps are the obligations each party assumes the other owns. Document the split explicitly — ambiguity here is where compliance falls through.

---

## The Principle

Your AI is only as governable as your least-governable vendor. A single black-box dependency with no audit rights, no change notification, and no exit path can undermine an otherwise mature governance programme. Vendor governance is not procurement's problem or governance's problem — it's the seam between them, and seams are where things fail. Govern the supply chain, or the supply chain governs you.
