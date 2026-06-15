# Research Workflow

This document describes how to conduct structured research using this harness.
Research tasks invoke dedicated Claude Code skills rather than the generic
implementation loop. Read this file before any research-type intake.

## Research Skills

| Skill | Command | Use when |
| --- | --- | --- |
| `deep-research` | `/deep-research` | Open research questions, literature reviews, systematic reviews, fact-checking, Socratic guided research |
| `academic-paper` | `/academic-paper` | Writing or revising an academic paper (10 modes) |
| `academic-paper-reviewer` | `/academic-paper-reviewer` | Peer-reviewing a manuscript (5 reviewer personas) |
| `academic-pipeline` | `/academic-pipeline` | Full research-to-paper pipeline (10 stages, end-to-end) |

### When to use each skill

```text
Research question exists, need evidence
  -> /deep-research

Evidence gathered, need paper draft
  -> /academic-paper

Draft exists, need peer review
  -> /academic-paper-reviewer

Starting from scratch, need full pipeline
  -> /academic-pipeline
```

## Research Intake Types

Use the standard `docs/FEATURE_INTAKE.md` intake gate, with these additional
input types for research work:

| Input type | Use when | Typical artifact |
| --- | --- | --- |
| Research question | A new research question needing investigation | Deep-research run + summary doc |
| Literature review | Systematic review of existing literature | Lit-review report under `docs/research/` |
| Paper draft | Writing or revising an academic paper | Paper file under `docs/papers/` |
| Paper review | Peer-review of an existing manuscript | Review report under `docs/reviews/` |
| Fact check | Verifying specific claims or data | Fact-check report under `docs/research/` |
| Full pipeline | End-to-end from question to published-ready paper | All artifacts under `docs/papers/<slug>/` |

## Research Lanes

Overlay these on top of the standard tiny/normal/high-risk lanes:

| Research lane | Use when | Extra requirements |
| --- | --- | --- |
| Quick brief | Narrow factual question, <1 hour | Single skill run; record output in `docs/research/` |
| Systematic review | Multi-source literature review | `/deep-research` full mode; PRISMA-style report |
| Paper authoring | Writing a complete paper | `/academic-paper`; version paper in `docs/papers/` |
| End-to-end pipeline | Research question → publication-ready paper | `/academic-pipeline`; create story packet |

## Research Directory Structure

```text
docs/
  research/          # ad-hoc research outputs, fact-checks, literature notes
  papers/            # paper drafts and final versions
    <slug>/          # one folder per paper project
      draft.md
      review-*.md
      final.md
  reviews/           # standalone peer-review reports
  product/
    research.md      # research product contract
```

## Research Task Loop

For every research task:

1. Classify request type using `docs/FEATURE_INTAKE.md` + research intake types above.
2. Record intake with `scripts/bin/harness-cli intake` (when CLI is available).
3. Choose the right skill:
   - `/deep-research` for investigation
   - `/academic-paper` for writing
   - `/academic-paper-reviewer` for review
   - `/academic-pipeline` for full pipeline
4. Run the skill with the appropriate mode (see skill help for modes).
5. Save output artifacts to the correct directory under `docs/`.
6. Record a trace (when CLI is available).
7. Update the story packet if one exists.

## Skill Modes Quick Reference

### `/deep-research` modes
- `full research` — complete 13-agent pipeline
- `quick brief` — fast factual answer
- `lit-review` — literature review only
- `systematic review` — PRISMA-style systematic review with optional meta-analysis
- `fact-check` — verify specific claims
- `Socratic guided` — interactive research dialogue

### `/academic-paper` modes
- `full` — complete paper
- `plan` — outline and structure
- `outline` — section outline only
- `revision` — revise an existing draft
- `revision-coach` — guided revision feedback
- `abstract` — abstract only
- `lit-review` — literature review section
- `format-convert` — convert between formats (LaTeX/DOCX/PDF)
- `citation-check` — validate citations
- `disclosure` — AI disclosure statement

### `/academic-paper-reviewer` modes
- Full review — EIC + 3 peer reviewers + Devil's Advocate
- Re-review — verify revisions against original review
- Quick assessment — fast high-level opinion
- Methodology focus — deep methods critique
- Socratic guided — interactive review dialogue

### `/academic-pipeline` stages (automated)
1. Research
2. Write
3. Integrity check
4. Review
5. Revise
6. Re-review
7. Re-revise
8. Final integrity check
9. Finalize

## Validation for Research Tasks

| Proof type | When required | How to satisfy |
| --- | --- | --- |
| Source citations | All research outputs | Include cited sources in output |
| Methodology statement | Systematic reviews | PRISMA checklist or equivalent |
| Peer review record | Papers going to submission | `/academic-paper-reviewer` report saved |
| Integrity check | All papers | Built into `/academic-pipeline`; run `/academic-paper citation-check` standalone |
| Human approval | High-risk claims or submissions | Pause and ask before finalizing |

## Research Risk Flags

Apply standard risk flags from `docs/FEATURE_INTAKE.md`, plus:

| Research flag | Applies when |
| --- | --- |
| Sensitive data | Research involves personal, proprietary, or embargoed data |
| External submission | Output will be submitted to a journal, conference, or public venue |
| Contested claims | Research area has significant disagreement or replication issues |
| Multi-author | More than one human author must approve the output |

Any of these flags escalates to at minimum the normal lane with human approval
before final output.
