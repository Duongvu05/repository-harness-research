# Agent Instructions

This repository is configured as an **agent-ready research harness**. It supports
structured research workflows using dedicated Claude Code skills alongside the
standard harness discipline for software development.

<!-- HARNESS:BEGIN -->
## Harness

This repo uses Harness. Before work, read:

- `README.md`
- `docs/HARNESS.md`
- `docs/FEATURE_INTAKE.md`
- `docs/ARCHITECTURE.md`
- `docs/CONTEXT_RULES.md`
- `docs/TOOL_REGISTRY.md`
- `scripts/bin/harness-cli query matrix` on macOS/Linux, or `.\scripts\bin\harness-cli.exe query matrix` on Windows

Use the Rust Harness CLI at `scripts/bin/harness-cli` on macOS/Linux or
`scripts/bin/harness-cli.exe` on Windows as the main operational tool. Before a
step that could use an external tool, run `scripts/bin/harness-cli query tools
--capability <name> --status present` to see what is equipped; an absent
capability is a clean skip.
<!-- HARNESS:END -->

## Research Mode

When the task is research-oriented (investigation, literature review, paper writing,
peer review), read `docs/RESEARCH_WORKFLOW.md` before intake. Then choose the
appropriate skill:

| Task | Skill |
| --- | --- |
| Research question / literature review / fact-check | `/deep-research` |
| Write or revise an academic paper | `/academic-paper` |
| Peer-review a manuscript | `/academic-paper-reviewer` |
| Full research-to-paper pipeline | `/academic-pipeline` |

Research artifacts are saved under `docs/research/`, `docs/papers/`, and
`docs/reviews/`. The research product contract is at `docs/product/research.md`.

Research intake follows the standard feature intake gate (`docs/FEATURE_INTAKE.md`)
with the additional research input types defined in `docs/RESEARCH_WORKFLOW.md`.
