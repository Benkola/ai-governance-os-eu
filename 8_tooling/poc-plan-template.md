# Proof-of-Concept (PoC) Plan Template

> **Purpose:** A structured plan for running a proof-of-concept before committing to an AI tool or vendor. A PoC is where you find out whether a tool actually works for your use case — and, just as importantly, whether it's governable. Most PoCs test features and ignore governance, then teams are surprised when the "successful" PoC becomes an ungovernable production system. This template builds governance gates into the PoC so you learn the whole truth before you commit.
>
> **When to use:** After a tool passes the evaluation rubric and before you sign a full contract. The PoC is the bridge between "looks good on paper" and "safe to deploy."
>
> **Owner:** The requesting business team runs the PoC; AI Governance Lead defines the governance gates; Security and DPO sign off on their gates.

---

## 1. PoC Overview

| Field | Detail |
|-------|--------|
| **Tool / vendor** | _Name_ |
| **Use case** | _What problem the tool would solve_ |
| **PoC owner** | _Who runs it_ |
| **Duration** | _Typically 4–8 weeks_ |
| **Rubric score** | _From the evaluation rubric_ |
| **Preliminary risk tier** | _High / Limited / Minimal (from intake)_ |
| **Decision date** | _When go/no-go is decided_ |

---

## 2. Success Criteria (Define Before Starting)

The single most important discipline: define what success looks like *before* the PoC, so the decision is evidence-based, not vibes-based. Split into functional and governance criteria — both must pass.

### Functional success criteria

| Criterion | Target | Measured how |
|-----------|--------|--------------|
| _e.g., Accuracy on our data_ | _> X%_ | _Test on representative sample_ |
| _e.g., Latency_ | _< X ms_ | _Load test_ |
| _e.g., Integration effort_ | _< X days_ | _Track implementation time_ |
| _e.g., User acceptance_ | _> X% positive_ | _User feedback_ |

### Governance success criteria (equally weighted)

| Criterion | Target | Measured how |
|-----------|--------|--------------|
| Documentation adequacy | Vendor provides docs sufficient for our compliance obligations | Review against audit checklist |
| Bias / fairness | Meets our fairness thresholds on our data | Bias test during PoC |
| Data handling | DPA in place; no unauthorised data use | Legal/DPO review |
| Explainability | Outputs can be explained to the degree our use case requires | Test explainability features |
| Monitoring feasibility | We can monitor the tool in production | Confirm monitoring integration |
| Security | Passes security assessment | Security team review |

---

## 3. Risk Gates

Beyond success criteria, define hard gates the PoC must clear. A gate failure stops the PoC regardless of functional performance.

- [ ] **Data gate:** No production personal data used in the PoC without DPA and DPO sign-off (use synthetic or anonymised data where possible)
- [ ] **Security gate:** Security team approves the PoC environment before any real data touches it
- [ ] **Scope gate:** The PoC stays within a defined, contained scope — not a backdoor into production
- [ ] **Exit gate:** You can cleanly remove the tool and any data at the end of the PoC
- [ ] **Compliance gate:** For a high-risk use case, the vendor demonstrates it can support your compliance obligations, or the PoC fails regardless of features

---

## 4. PoC Scope

| Element | Detail |
|---------|--------|
| **In scope** | _What the PoC will test_ |
| **Out of scope** | _What it deliberately won't — prevents scope creep_ |
| **Data used** | _Synthetic / anonymised / (production only with sign-off)_ |
| **Environment** | _Isolated PoC environment, not production_ |
| **Users involved** | _Who participates_ |
| **Systems touched** | _What it integrates with (kept minimal)_ |

---

## 5. PoC Plan (Week by Week)

| Week | Activity | Owner | Gate check |
|------|----------|-------|------------|
| 1 | Setup, environment, data preparation | PoC owner + Security | Security gate, Data gate |
| 2–3 | Functional testing against criteria | Business team | Functional criteria |
| 3–4 | Governance testing (bias, docs, explainability) | AI Governance Lead | Governance criteria |
| 5–6 | Integration and user testing | Business + Eng | Integration criteria |
| 7 | Results compilation and scoring | PoC owner | All criteria assessed |
| 8 | Go/no-go decision | Governance body | Final decision |

*(Compress or extend to fit the tool's complexity.)*

---

## 6. Go/No-Go Decision

At the end of the PoC, decide against the criteria:

| Dimension | Passed? | Evidence |
|-----------|---------|----------|
| Functional criteria met | ☐ Yes ☐ No ☐ Partial | |
| Governance criteria met | ☐ Yes ☐ No ☐ Partial | |
| All risk gates cleared | ☐ Yes ☐ No | |
| No veto conditions triggered | ☐ Yes ☐ No | |

**Decision:** ☐ Proceed to contract ☐ Proceed with conditions ☐ Extend PoC ☐ Reject

**If proceeding:** feed into the vendor governance framework for contracting.
**If rejecting:** document why — it informs future evaluations and protects you if the decision is questioned later.

**Decision rationale (2–3 sentences):**

---

## 7. Procurement Decision Memo (Template)

Once decided, produce a short memo for the record and for the approval chain:

> **AI Tool Procurement Decision — [Tool Name]**
>
> **Recommendation:** [Proceed / Reject]
>
> **Use case:** [1 sentence]
>
> **Evaluation:** Scored [X/4.0] on the governance rubric. [Key strengths.] [Key weaknesses and how mitigated.]
>
> **PoC result:** [Functional and governance criteria outcomes.] [Any gate issues.]
>
> **Governance position:** Risk tier [X]. [How compliance obligations will be met.] [Vendor governance terms secured.]
>
> **Conditions (if any):** [Ongoing requirements — monitoring, contractual terms, review points.]
>
> **Decision owner:** [Name] **Date:** [Date]

This memo is the audit trail for the procurement decision. If a regulator, auditor, or future colleague asks "why did we choose this tool and how did we assure it was safe?", this answers them.

---

## The Principle

A PoC that only tests features tells you half the truth. The tool might work brilliantly and still be impossible to govern — no documentation, no audit rights, data used for vendor training, a black box you can't explain to a regulator. By building governance gates and criteria into the PoC, you learn the whole truth while it's still cheap to walk away. The best time to discover a tool is ungovernable is during the PoC, not during a regulatory inspection two years later.
