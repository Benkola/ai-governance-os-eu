# Regulatory Landscape Overview

> AI governance does not operate under a single regulation. Most organisations deploying AI in the EU will need to satisfy multiple regulatory frameworks simultaneously. This overview maps the key frameworks an SME may need to navigate alongside the EU AI Act.

## Regulatory mapping

| Regulation | What it governs | Who it applies to | Key obligations | Governance intersection |
|---|---|---|---|---|
| **EU AI Act** (2024/1689) | AI systems, classified by risk tier (unacceptable, high, limited, minimal) | Providers and deployers of AI systems in the EU market, regardless of where the provider is established | Risk management system, data governance, technical documentation, record-keeping, transparency, human oversight, accuracy and robustness, post-market monitoring | Primary framework. This repo's controls map is built from its high-risk obligations (Articles 9–15). |
| **GDPR** (2016/679) | Processing of personal data | Any organisation processing personal data of EU residents | Lawful basis for processing, data minimisation, purpose limitation, DPIA for high-risk processing, data subject rights (access, erasure, portability), breach notification within 72 hours | AI systems processing personal data must satisfy GDPR alongside the AI Act. A DPIA is required where AI processing is likely to result in high risk to individuals. Automated decision-making (Article 22) gives individuals the right to contest solely automated decisions with legal or significant effects. |
| **DMA** (2022/1925) | Gatekeeper digital platforms | Designated gatekeepers (currently: Alphabet, Amazon, Apple, ByteDance, Meta, Microsoft) | Data portability, interoperability, fair access for business users, prohibition of self-preferencing, consent requirements for cross-service data combination | Relevant when an organisation's AI systems operate within or depend on gatekeeper ecosystems. DMA data access and portability obligations affect training data sourcing. Organisations building AI on gatekeeper platforms should assess whether DMA restrictions affect their data pipelines. |
| **DSA** (2022/2065) | Digital services and online platforms | Online intermediaries and platforms, with enhanced obligations for very large online platforms (VLOPs: 45M+ EU users) | Transparency of recommender systems, algorithmic risk assessments, content moderation accountability, researcher data access, annual transparency reporting | AI-powered recommendation, content moderation, and ranking systems must satisfy DSA transparency and risk assessment requirements. DSA and AI Act obligations overlap for algorithmic systems — governance should address both simultaneously. |
| **SOx** (Sarbanes-Oxley, 2002) | Financial reporting integrity and internal controls | US-listed companies, including EU companies with US reporting obligations (dual-listed, ADR programmes) | Internal controls over financial reporting (Section 404), management assessment of control effectiveness, CEO/CFO certification of financial statements (Section 302), external auditor attestation | Where AI systems influence financial data, forecasting, or reporting decisions, data governance controls (quality, lineage, access, change management) must satisfy SOx IT General Controls (ITGCs). AI-generated financial inputs require the same auditability as manual inputs. |
| **DORA** (2022/2554) | ICT risk management for financial entities | Banks, insurers, investment firms, payment providers, and critical ICT third-party providers operating in the EU | ICT risk management framework, incident reporting, resilience testing, third-party risk management, information sharing | Financial sector organisations deploying AI must ensure AI systems comply with DORA's ICT risk management requirements. AI vendors used by financial entities may be classified as critical ICT third-party providers, triggering additional oversight obligations. |
| **NIST AI RMF 1.0** (2023) | AI risk management (voluntary framework) | Any organisation (US-origin, globally referenced) | Four core functions: Govern (policies, roles, accountability), Map (context, risk identification), Measure (risk assessment, tracking), Manage (risk response, monitoring) | Not a regulation but widely adopted as a best-practice framework. This repo crosswalks EU AI Act obligations to NIST AI RMF functions in a later artefact (see 5_nist-crosswalk). Useful for organisations that want to align with both EU and US approaches. |
| **ISO/IEC 42001** (2023) | AI management systems | Any organisation seeking certification or wanting to demonstrate structured AI management | AI policy, risk assessment, objectives and planning, resource allocation, operational controls, performance evaluation, continual improvement | International standard for establishing and maintaining an AI management system. This repo aligns conceptually with ISO 42001 without claiming certification. Organisations pursuing certification can use this repo's artefacts as a starting point for required documentation. |

## Phased enforcement timeline

Not all obligations are enforceable at the same time. Key dates:

| Date | What becomes enforceable |
|---|---|
| **February 2025** | Prohibited AI practices (Article 5) and AI literacy obligations (Article 4) |
| **August 2025** | General-purpose AI model obligations (Article 53+) and governance structure requirements |
| **Late 2027 – 2028** | High-risk AI system obligations (Articles 9–15) — note: the European Commission's Digital Omnibus proposal may extend original August 2026 deadlines to allow harmonised standards to be finalised |

Organisations should not wait for high-risk deadlines to begin building governance infrastructure. The prohibited practices and AI literacy requirements are already enforceable, and building governance incrementally is significantly less disruptive than a deadline-driven scramble.

## Practical implication for SMEs

For SMEs, the key takeaway is that governance should be designed to satisfy multiple regimes simultaneously. An AI system that processes personal data, operates in financial services, and is classified as high-risk under the AI Act may need to satisfy the AI Act, GDPR, SOx, and DORA — all at once.

The controls map and templates in this repo are built with this multi-regulatory reality in mind. Where a single control satisfies requirements from multiple regulations, this is noted. The goal is one governance system that covers multiple obligations, not separate compliance workstreams per regulation.
