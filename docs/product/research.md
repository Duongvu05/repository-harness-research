# Research Product Contract

This document defines the research purpose and output standards for this repository.

## Purpose

This repository is configured as an **agent-ready research harness**. It helps
humans and agents conduct structured research, produce academic-quality outputs,
and maintain evidence trails — using the same harness discipline applied to
software development.

The research harness adds:
- Research intake classification on top of the standard feature intake.
- Dedicated skill invocations for investigation, writing, and peer review.
- A directory structure for research artifacts.
- Validation expectations for citations, methodology, and human approval gates.

## Research Output Types

| Output | Description | Directory |
| --- | --- | --- |
| Research brief | Concise answer to a research question with sources | `docs/research/` |
| Literature review | Systematic review of a topic with synthesis | `docs/research/` |
| Fact-check report | Verification of specific claims or data points | `docs/research/` |
| Paper draft | Academic paper in progress | `docs/papers/<slug>/` |
| Final paper | Submission-ready paper | `docs/papers/<slug>/final.md` |
| Peer review | Structured review of a manuscript | `docs/reviews/` |

## Quality Standards

All research outputs must meet:

1. **Source traceability** — every factual claim cites a source.
2. **Methodology transparency** — the approach used to gather evidence is stated.
3. **Scope clarity** — the question answered and the scope not covered are both explicit.
4. **Human approval gate** — outputs flagged as external-submission or contested-claims
   require human review before finalizing.

## Research Domains

No domain is restricted by default. When a research topic involves:
- **Sensitive data** (personal, proprietary, embargoed) → apply `Sensitive data` risk flag.
- **Contested or replication-crisis areas** → apply `Contested claims` risk flag and
  use `/deep-research systematic review` mode.
- **External submission** → apply `External submission` risk flag; require
  `/academic-paper-reviewer` pass before finalizing.

## Relationship to Harness

Research work enters through the standard intake gate in `docs/FEATURE_INTAKE.md`
with the additional research input types defined in `docs/RESEARCH_WORKFLOW.md`.

Research stories follow the same story packet format (`docs/templates/story.md`)
with the research-specific extension template at
`docs/templates/research-story.md`.

Decisions that change research methodology, quality standards, or output formats
must be recorded as durable decisions in `docs/decisions/`.
