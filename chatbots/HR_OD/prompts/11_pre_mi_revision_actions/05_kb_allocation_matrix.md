# KB Allocation Matrix

## Purpose

This artifact assigns ownership across MI and KB01-KB06 so content is not duplicated or placed in the wrong authority layer.

This matrix is written after the MI Safety Priority Block and Input Sufficiency Rules because KB ownership must respect runtime authority.

## Ownership Principles

1. MI owns hard authority rules.
2. KB05 supports MI with safety examples and validation patterns.
3. KB06 routes after safety and selects output/depth.
4. KB04 contains artifact schemas, not routing authority.
5. KB02 diagnoses; KB03 designs interventions after sufficient diagnosis.
6. KB01 explains concepts without becoming the diagnostic or intervention playbook.

## Allocation Matrix

| Knowledge node | Owner | Section | Depth | Must not own | Cross-reference |
|---|---|---|---|---|---|
| Role, mission, primary users | MI | Role & Scope | Compact | Long stakeholder analysis | `03`, KB06 audience rules |
| Out-of-scope | MI | Scope Boundary | Compact | Detailed examples | KB05 examples |
| Hard safety rules | MI | Safety Priority | High but compact | Long trigger library | KB05 trigger table |
| Flow priority | MI | Runtime Order | Compact | Full route examples | KB06 |
| Task router summary | MI + KB06 | MI summary; KB06 detail | MI compact, KB06 high | Domain content | KB01-KB04 |
| OD concept map | KB01 | OD foundations | Medium | Diagnostic framework detail | KB02 |
| Enterprise OD context | KB01 | Enterprise context | Medium | Implementation roadmap templates | KB04 |
| Problem type taxonomy overview | KB01 | Problem overview | Low/Medium | Root-cause patterns | KB02 |
| Symptom-to-hypothesis logic | KB02 | Diagnostic logic | High | Intervention selection detail | KB03 |
| Evidence and confidence in diagnosis | KB02 + KB05 | Diagnostic evidence; validation controls | High | Hard safety rules | MI / KB05 |
| Diagnostic question bank | KB02 | Question bank | High | Router rules | KB06 |
| Root-cause layer map | KB02 | Diagnostic layers | High | Individual judgment | MI / KB05 |
| Intervention categories | KB03 | Intervention playbook | High | Full artifact templates | KB04 |
| Intervention fit criteria | KB03 | Fit logic | High | Diagnosis ownership | KB02 |
| Change enablement for OD | KB03 | Implementation logic | Medium/High | Enterprise transformation methodology | KB01 boundary / KB05 risk |
| Pilot, sequencing, readiness | KB03 | Implementation controls | High | Project management methodology deep dive | KB06 depth rules |
| Proposal schema | KB04 | Artifact templates | High | Intervention decision logic | KB03 |
| Roadmap schema | KB04 | Artifact templates | High | Permission to create roadmap under low input | Input sufficiency / KB06 |
| Manager guide / talking points | KB04 | Audience templates | High | Disciplinary script | MI / KB05 |
| Employee communication / FAQ | KB04 | Audience templates | High | Policy/legal determination | MI / KB05 |
| Measurement dashboard outline | KB04 | Artifact templates | High | Impact conclusion | KB05 confidence rules |
| Safety trigger examples | KB05 | Trigger library | High | Hard safety rules as sole authority | MI |
| Safe alternative patterns | KB05 | Safe support | High | Full artifact library | KB04 |
| Assumption Note / Confidence Label | KB05 | Epistemic validation | High | Domain diagnosis ownership | KB02 |
| Gap analysis / revision memo | KB05 | Validation module | High | Router ownership | KB06 |
| Task type detection | KB06 | Router | High | Domain explanation | KB01 |
| Flow selection after safety | KB06 | Flow selection | High | MI Safety Gate | MI |
| Output selection | KB06 | Output contract index | High | Full template content | KB04 |
| Multi-task composition | KB06 | Composition rules | High | Safety hard rules | MI / KB05 |
| Audience/recipient depth | KB06 + KB04 | Depth rules; template variants | High | Stakeholder governance decisions | MI / KB05 |
| Final Output Gate | MI + KB06 + KB05 | MI compact; KB06/K05 operational | Compact/High | Long test cases | Test set |
| Test scenario set | Test artifact | Evaluation only | High | Runtime knowledge | None |

## KB Non-Overlap Rules

| Boundary | Rule |
|---|---|
| MI vs KB05 | MI states hard rules. KB05 explains them with examples, checklists, and safe alternatives. |
| MI vs KB06 | MI states flow priority. KB06 implements routing examples after safety gate. |
| KB04 vs KB06 | KB06 selects template and depth. KB04 contains the template schema. |
| KB02 vs KB03 | KB02 explains likely causes. KB03 selects/designs interventions after diagnosis. |
| KB01 vs KB02 | KB01 defines concepts. KB02 applies concepts to diagnose symptoms and evidence. |
| KB03 vs KB04 | KB03 decides intervention logic. KB04 formats the chosen intervention into artifacts. |
| KB05 vs KB04 | KB05 gives safety constraints and safe patterns. KB04 turns safe pattern into artifact schema. |

## Definition of Done

- Every major knowledge node has one owner.
- MI hard rules are not assigned to KB05 or KB06.
- KB06 routes after safety and does not contain full templates.
- KB04 templates do not decide intervention fit or override safety.

