# E04 Research Epic

## Goal

Enable structured, traceable research workflows within this harness repository
using the four research skills: `deep-research`, `academic-paper`,
`academic-paper-reviewer`, and `academic-pipeline`.

## Affected Product Docs

- `docs/product/research.md`
- `docs/RESEARCH_WORKFLOW.md`

## Candidate Stories

| ID | Title | Status | Skill |
| --- | --- | --- | --- |
| RS-001 | First research question investigation | planned | `/deep-research` |
| RS-002 | First literature review | planned | `/deep-research` |
| RS-003 | First paper draft | planned | `/academic-paper` |
| RS-004 | First peer review | planned | `/academic-paper-reviewer` |

## Validation Shape

Each story in this epic requires:
- Output artifact saved to `docs/research/`, `docs/papers/`, or `docs/reviews/`.
- Source citations present in output.
- Human approval if `External submission` or `Contested claims` flags apply.

## Exit Criteria

- At least one complete research cycle (question → investigation → output) traced.
- Research workflow documented and validated in `docs/RESEARCH_WORKFLOW.md`.
- Research templates confirmed usable via at least one completed story.

## Open Decisions

- Citation format standard (APA 7 default from `/academic-paper`; confirm per project).
- Output file format (Markdown default; LaTeX/DOCX via `/academic-paper format-convert`).
