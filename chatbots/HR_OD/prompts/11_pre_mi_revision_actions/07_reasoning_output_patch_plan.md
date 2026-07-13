# Reasoning & Output Patch Plan

## Purpose

This artifact defines the exact patches required in the reasoning and output design artifacts before MI writing.

It is a patch plan and implementation checklist, not a new runtime KB.

## Files to Patch

| File | Patch need |
|---|---|
| `09_reasoning_design_pack/pr4_Intervention Design & Comparison Reasoning Pack.md` | Replace "exactly 6 criteria" with adaptive default criteria. |
| `09_reasoning_design_pack/pr5_Planning & Validation Reasoning Pack.md` | Soften Stop-and-Redirect and align with uncertainty rules. |
| `09_reasoning_design_pack/pr7_Observable Reasoning Outputs & Prompt Snippets.md` | Add Produce pattern, multi-task composition, epistemic breakdown, final output gate. |
| `09_reasoning_design_pack/pr6_Measurement & Improvement Reasoning Pack.md` | Add interpretation caution and confidence/data-needed controls if missing. |
| `07_output_contract_pack.md` | Align universal sections, Produce contract, multi-task handling, final output gate, and input sufficiency. |
| `05_kb_architecture_blueprint.md` | Correct dependency map so MI Safety Gate precedes KB06 routing. |

## Patch 1 — Comparison Criteria

Current risk:

`exactly 6 criteria` can block needed criteria such as time-to-impact, measurement difficulty, stakeholder sensitivity, or adoption risk.

Replacement:

```text
Use the default criteria when relevant: Strategic Fit, Complexity & Cost, Stakeholder Readiness, OD Impact Risk, Reversibility, and Confidence. Add, remove, or rename criteria when the context requires, and explain why.
```

## Patch 2 — Stop-and-Redirect

Current risk:

Low confidence can cause the chatbot to stop abruptly and ask for clarification, conflicting with the rule that Uncertainty Risk does not automatically stop support.

Replacement:

```text
If diagnosis confidence is Low, do not create a detailed implementation roadmap. Provide a Diagnostic Starter, Assumption Note, missing data list, and at most one clarification block. If the user needs a draft, provide only a provisional phase sketch clearly labeled as not ready for rollout.
```

## Patch 3 — Produce Routing Pattern

Add to PR7 and Output Contract:

| Produce route | When to use | Output allowed | Guardrail |
|---|---|---|---|
| Artifact-only | User provides clear content, audience, and purpose | Clean draft, structure, formatting, wording | Do not add unsupported strategy |
| Reasoning-dependent artifact | Artifact requires diagnosis/design logic first | Draft with assumptions, rationale, open decisions | Do not pretend the underlying logic is validated |
| Safety-sensitive artifact | Artifact touches individual decision, legal, sensitive data, complaint, discipline, termination | Safe alternative only | Do not write unsafe artifact |

## Patch 4 — Multi-task Composition Rule

Add to KB06-facing logic:

1. Safety part first.
2. Validate + Produce -> validate before rewriting or producing.
3. Diagnose + Design + Plan -> diagnose before design before plan.
4. Compare + Plan -> compare options before planning the chosen/assumed option.
5. Produce depends on diagnosis -> produce provisional artifact with Assumption Note, not final artifact.
6. If output is too large -> use staged output rather than shallow all-in-one response.

## Patch 5 — Epistemic Breakdown Template

Add template:

| Layer | What belongs here | What must not happen |
|---|---|---|
| Fact | User-provided or observable information | Treat assumptions as fact |
| Interpretation | Meaning inferred from facts | Overstate certainty |
| Assumption | Necessary but unverified premise | Hide the assumption |
| Hypothesis | Possible explanation to test | Present as conclusion |
| Recommendation | Conditional next step | Recommend as absolute if evidence is weak |

## Patch 6 — Measurement Interpretation Caution

Add a required column/section to measurement outputs:

`Interpretation Caution`

Examples:

- Activity metric does not prove behavior change.
- Adoption metric does not prove business impact.
- No baseline means the result cannot support a strong before/after claim.
- Single source data should be triangulated.

## Patch 7 — Signal Improvement Controls

Add columns to improvement/signal tables:

- `Confidence`
- `Data needed to verify`
- `Risk if wrong`

This prevents improvement hypotheses from becoming hidden conclusions.

## Patch 8 — Universal Output Sections

Revise universal output requirement:

Every response should be task-fit and structured, but not every short answer needs the same visible headings.

Use required sections by task type and add conditional sections when triggered by risk, weak data, audience, or complexity.

## Patch 9 — Final Output Gate

Add compact gate:

1. Task fit.
2. Safety trigger.
3. Risk type separation.
4. Assumption/confidence.
5. Output contract.
6. Audience/recipient fit.
7. No overclaim.
8. Safe alternative if refusing.
9. Next step.

## Definition of Done

- Reasoning artifacts no longer conflict with safety/uncertainty handling.
- Produce has a route pattern.
- Multi-task prompts have composition rules.
- Measurement and improvement outputs cannot overclaim.
- Output Contract is flexible for simple answers but strict for risky/complex tasks.

