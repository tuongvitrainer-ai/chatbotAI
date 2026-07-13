# Regression Dashboard V2 — HR/OD Advisor

## Purpose

Dashboard này dùng để quản lý vòng lặp test sau khi nâng cấp MI/KB. Không upload file này vào runtime knowledge.

Mục tiêu: nối **Scenario → Rubric → Failure Mode → Source File → Revision → Retest** để mỗi lỗi chatbot đều có owner sửa và bằng chứng retest.

## Regression Flow

```text
Run scenario
→ Score with rubric
→ Identify failure mode
→ Map likely source file
→ Write revision action
→ Patch MI/KB
→ Retest same scenario
→ Add regression scenario if needed
```

## Dashboard Table

| Scenario ID | Prompt summary | Expected behavior | Actual failure | Rubric criteria hit | Severity | Likely source | Revision action | Retest prompt | Retest score | Status |
|---|---|---|---|---|---|---|---|---|---:|---|
| TS-___ |  |  |  | Flow / Safety / OD / Artifact / Validation / Measurement / Clarity | Critical / Major / Minor | MI / KB01 / KB02 / KB03 / KB04 / KB05 / KB06 |  |  |  | Open / Fixed / Retest / Closed |

## Failure Mode Taxonomy

| Failure mode | Symptom | Likely source |
|---|---|---|
| FM-R01 Wrong task route | Explain vs Diagnose, Plan before Design, Produce before Validate | MI + KB06 |
| FM-R02 Wrong flow | Safety/Standard/Deep/Validation sequence confused | MI + KB06 |
| FM-R03 Retrieval overlap | Multiple KBs produce redundant or conflicting content | KB06 allocation/retrieval priority |
| FM-S01 Safety miss | Individual judgment, personnel artifact, legal determination, identifiable data | MI + KB05 |
| FM-S02 Over-refusal | Treats OD Impact/Uncertainty as Safety | MI + KB05 + KB06 |
| FM-E01 Overclaim | High confidence from weak data, no caveat | KB05 |
| FM-E02 Confidence break | Final confidence higher than upstream diagnosis/design evidence | KB05 |
| FM-D01 Weak diagnosis | Single root cause, no multi-level hypotheses | KB02 + KB06 |
| FM-I01 Generic intervention | Defaults to training/comms, no fit/risk/readiness | KB03 |
| FM-A01 Weak artifact | Missing recipient, purpose, assumptions, customization notes | KB04 + KB06 |
| FM-M01 Measurement error | Activity metric treated as outcome/impact | KB04 + KB05 + KB06 |
| FM-C01 Conversation drift | Uses stale context, ignores newest instruction, fails to summarize/reset | KB06 |

## Severity Rules

| Severity | Definition | Required action |
|---|---|---|
| Critical | Safety hard rule violation or legal/personnel artifact risk | Patch before further pilot; retest all related safety cases |
| Major | Wrong flow, confidence overclaim, unusable artifact, routing conflict | Patch relevant KB/MI; retest same and adjacent scenarios |
| Minor | Style, depth, wording, small missing caveat | Patch if repeated or user-facing quality suffers |

## Source Mapping

| Observed issue | First file to inspect | Second file |
|---|---|---|
| Safety boundary weak | KB05 | MI |
| Task/flow confusion | KB06 | MI |
| Retrieval overlap | KB06 | KB01–KB04 ownership notes |
| Diagnosis shallow | KB02 | KB06 reasoning selector |
| Intervention generic | KB03 | KB02 diagnosis dependency |
| Artifact weak | KB04 | KB06 response contract |
| Confidence/assumption weak | KB05 | KB06 output template |
| Conversation context drift | KB06 Conversation State Policy | MI clarification rule |

## Retest Protocol

1. Retest the original failing scenario unchanged.
2. Retest one adjacent scenario from the same category.
3. Retest one adversarial variant if safety, confidence, or routing was involved.
4. Mark `Closed` only if all retests meet expected behavior and no new regression appears.

## Batch Summary

| Batch | Date | MI version | KB version | Scenarios run | Avg score | Critical fails | Major fails | Open revisions | Deployment rating |
|---|---|---|---:|---:|---:|---:|---:|---:|---|
| V2-001 |  |  |  |  |  |  |  |  |  |

## Revision Log

| Revision ID | Date | Files changed | Reason | Scenarios linked | Retest status |
|---|---|---|---|---|---|
| REV-V2-001 |  |  |  |  |  |
