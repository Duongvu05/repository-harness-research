# RS-XXX Research Story Title

## Status

planned | in-progress | complete | blocked

## Lane

tiny | normal | high-risk

## Research Type

research-question | literature-review | paper-draft | paper-review | fact-check | full-pipeline

## Research Question

State the specific question or objective this research story addresses.

## Skill

Which skill will be invoked:
- `/deep-research` — mode: `full research | quick brief | lit-review | systematic review | fact-check | Socratic guided`
- `/academic-paper` — mode: `full | plan | outline | revision | revision-coach | abstract | lit-review | format-convert | citation-check | disclosure`
- `/academic-paper-reviewer` — mode: `full review | re-review | quick assessment | methodology focus | Socratic guided`
- `/academic-pipeline` — full 10-stage pipeline

## Scope

Define what is in scope and what is explicitly out of scope.

**In scope:**

**Out of scope:**

## Relevant Product Docs

- `docs/product/research.md`

## Acceptance Criteria

- [ ] Research question is answered with cited sources.
- [ ] Output is saved to the correct directory (`docs/research/`, `docs/papers/`, or `docs/reviews/`).
- [ ] Methodology used is stated in the output.
- [ ] Human approval obtained if `External submission` or `Contested claims` risk flag applies.

## Risk Flags

Mark any that apply:

- [ ] Sensitive data
- [ ] External submission
- [ ] Contested claims
- [ ] Multi-author

## Validation

| Layer | Expected proof |
| --- | --- |
| Source citations | All factual claims have cited sources |
| Methodology | Approach documented in output |
| Peer review | `/academic-paper-reviewer` report saved (if paper) |
| Integrity check | Citation check passed |
| Human approval | Approved by human (if flagged) |

## Output Artifacts

List the files produced:

- `docs/research/` or `docs/papers/<slug>/` or `docs/reviews/`

## Harness Delta

Document any harness updates made or proposed because of this story.

## Evidence

Add commands run, skill output summaries, or links to output files after completion.
