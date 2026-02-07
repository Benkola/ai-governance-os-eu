# Moat boundary — what is public vs private

## Public (this repo)
This public repo contains **reference artefacts** that demonstrate operational AI governance:
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
The commercial implementation is intentionally excluded from this public repo, including:
- Production automation logic and workflows
- Proprietary scoring weights, thresholds, and calibration
- Benchmark datasets and heuristics derived from customer usage
- Customer-ready export pack formats and styling
- Integrations (M365/SharePoint/Teams/Jira/Cloud logs)
- Any customer-specific governance pack content

## Why this boundary exists
- Public artefacts build credibility and distribution.
- The commercial moat is **automation + integration + benchmarking + export packs**.

## What will never be open-sourced here
- The rules/heuristics engine that generates evidence packs at scale
- Benchmark data and calibrated scoring models
- Production-grade templates that embed proprietary defaults
