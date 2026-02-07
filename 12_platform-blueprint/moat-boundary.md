# Moat boundary — open foundation vs commercial execution

## Public (this repo)
This public repository intentionally exposes the decision logic, operating model, and governance structure — not just static documentation.
- EU AI Act controls maps and checklists
- Governance framework, operating model, RACI
- Templates (intake, risk register, model/system cards)
- Monitoring and incident playbooks
- Case studies showing end-to-end application

Purpose of public artefacts:
- Recruiter-readable proof
- Practitioner usefulness
- A clear “how to run governance” system for SMEs

## Private (commercial platform — NOT in this repo)
The commercial implementation is intentionally retained in the commercial platform and is not part of this public repository:
- Production automation logic and workflows
- Proprietary scoring weights, thresholds, and calibration
- Benchmark datasets and heuristics derived from customer usage
- Customer-ready export pack formats and styling
- Integrations (M365/SharePoint/Teams/Jira/Cloud logs)
- Any customer-specific governance pack content

## Why this boundary exists
- Public artefacts enable credibility, learning, and distribution.
- Commercial value is created through automation, integration, benchmarking, and repeatable evidence generation at scale.
- This split allows the framework to remain open and inspectable while preserving defensibility and long-term viability as a product.

## What will never be open-sourced here
- The rules/heuristics engine that generates evidence packs at scale
- Benchmark data and calibrated scoring models
- Production-grade templates that embed proprietary defaults

This repository represents the open foundation of a larger governance platform, designed to evolve into a production-grade system supporting regulated AI adoption in Europe.
