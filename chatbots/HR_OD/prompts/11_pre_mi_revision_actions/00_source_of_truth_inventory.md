# Source-of-Truth & Runtime Load Inventory

## Purpose

This artifact defines which files are authoritative for the pre-MI revision cycle and which files should or should not be loaded into the Custom GPT runtime.

It prevents three common failures:

1. Draft or old files being used as if they were current design sources.
2. Design artifacts being uploaded into runtime knowledge files.
3. MI writers extracting hard rules from the wrong layer.

## Status Legend

| Status | Meaning |
|---|---|
| Active | Current source for revision work. |
| Active / Patch needed | Current source, but must be corrected before MI. |
| Active / Revision needed | Current source, but incomplete or flagged with major gaps. |
| Reference | Useful background, not a source of runtime rules. |
| Archive | Historical or superseded material. Do not use for MI/KB writing unless explicitly compared. |
| Runtime KB | Final knowledge file intended for Custom GPT upload. Not yet produced in this revision layer. |

## Runtime Load Legend

| Runtime load? | Meaning |
|---|---|
| Yes | Upload or paste into Custom GPT runtime after final QA. |
| No | Do not upload. Use only during design/writing. |
| Extract only | Do not upload the full file. Extract selected rules, tables, or examples into MI/KB. |

## Inventory

| File / Folder | Status | Design use | Runtime load? | Extract only? | Notes |
|---|---|---|---|---|---|
| `01 Framing Brief & Runtime Requirement Checklist.md` | Active | Role, scope, runtime requirements, safety priority, task surface | No | Yes | Extract role/scope/runtime constraints and hard priority principles. Do not upload full design artifact. |
| `02_domain_decomposition_pack.md` | Active / Patch needed | Domain map, functional map, initial KB mapping | No | Yes | Mapping section still emphasizes KB01-KB03; must be reconciled with KB01-KB06 architecture. |
| `03 Stakeholder & Use-case Map.md` | Active | Direct users, artifact recipients, authority boundary, depth cues | No | Yes | Extract audience/recipient rules into KB06/KB04 and safety boundaries into MI/KB05. |
| `04_information_architecture_pack.md` | Active | KB taxonomy, hierarchy, ownership, task x knowledge matrix | No | Yes | Strong source for KB ownership. Use with updated runtime authority flow. |
| `05_kb_architecture_blueprint.md` | Active / Patched | KB blueprint and dependency map | No | Yes | Dependency map patched: MI Safety Gate precedes KB06 routing. KB05 remains pattern/checklist support, not MI replacement. |
| `06_intent_workflow_route_map.md` | Active | Task routing, flow selection, safety override examples | No | Yes | Main source for KB06 route examples after safety gate. |
| `07_output_contract_pack.md` | Active / Patch needed | Output structures, required/conditional sections, examples | No | Yes | Needs Produce routing, input sufficiency alignment, multi-task and final output gate tightening. |
| `08_research_knowledge_expansion_pack/` | Active / Revision needed | Research material for KB01-KB04 | No | Yes | Senior review flags major gaps: allocation matrix, boundary trigger table, verification register, test cases. |
| `09_reasoning_design_pack/` | Active / Patched | Reasoning principles, mode matrix, observable artifacts | No | Yes | Use patched PR4/PR5/PR6/PR7 as current source. Treat `revision reasoning.md` as historical review context after this revision pass. |
| `10_safety pack/` | Active | Safety taxonomy, hard rules, triggers, sensitive data, final check | No | Yes | Extract compact hard rules into MI Safety Priority Block; examples/patterns go to KB05. |
| `BRD2.md` | Reference | Background BRD and requirements trace | No | No | Do not upload. Use only to resolve unclear intent or trace original requirements. |
| `playbook.md` | Reference | Build sequence and prompt process | No | No | Do not upload. Process guide only. |
| `Framing brief.md` | Archive / Superseded | Older short framing | No | No | Superseded by `01 Framing Brief & Runtime Requirement Checklist.md`. |
| `KB05_validation_safety_rules.md` | Draft / Superseded pending review | Earlier KB05 draft | No | No | Do not treat as final KB05. Can be compared after MI Safety Block and Boundary Trigger Table are locked. |
| `09_reasoning_design_pack/[old] reasoning_design_pack.md` | Archive | Historical reasoning design | No | No | Do not use for MI except to identify superseded rules. |
| Final `KB01_OD_Domain_Map.md` | Runtime KB / Written | OD domain knowledge | Yes | No | Current final KB01 file exists. It supports Explain, Compare and Measure with OD concepts, domain boundaries, enterprise examples, misconceptions and quick comparison tables. |
| Final `KB02_OD_Diagnostic_Frameworks.md` | Runtime KB / Written | Diagnosis/evidence/hypothesis knowledge | Yes | No | Current final KB02 file exists. It supports Diagnose and Improve with symptom/root-cause logic, multi-level hypotheses, data-needed tables, and safe diagnostic examples. |
| Final `KB03_OD_Intervention_Playbook.md` | Runtime KB / Written | Intervention design and implementation logic | Yes | No | Current final KB03 file exists. It supports Design, Compare, Plan and Improve with intervention fit logic, conditions, risks, stakeholder logic, change enablement, validation checks and safe examples. |
| Final `KB04_OD_Artifacts_and_Templates.md` | Runtime KB / Written | Artifact schemas and templates | Yes | No | Current final KB04 file exists. It supports Produce, Plan and Measure with copy-ready templates, assumption/customization notes, safety boundaries and no-fake-data controls. |
| Final `KB05_Validation_and_Safety_Rules.md` | Runtime KB / Written | Safety examples, validation patterns, assumption/confidence library | Yes | No | Current final KB05 file exists. It supports MI hard rules with examples, checklists, templates, and test cases. |
| Final `KB06_Output_Standards_and_Task_Router.md` | Runtime KB / Written | Router, output selection, depth rules, multi-task handling | Yes | No | Current final KB06 file exists. Routes after MI Safety Gate and uses Validation Checkpoint as sequential support, not a standalone flow. |

## Runtime Loading Rule

Only final MI and final KB01-KB06 should be loaded into Custom GPT runtime.

Design artifacts, research packs, reviews, playbooks, and revision planning files should not be uploaded as knowledge files. They are writing inputs only.

## Extraction Rule

When a file is marked `Extract only`, the writer must extract only the relevant rule, table, example, or pattern into the correct destination:

| Extracted content | Destination |
|---|---|
| Hard safety rule | Master Instruction |
| Safety example/checklist/pattern | KB05 |
| Task routing / depth / output selection | KB06 |
| Artifact schema | KB04 |
| Domain concept | KB01 |
| Diagnostic logic | KB02 |
| Intervention fit logic | KB03 |
| Test prompt / pass criteria | Test scenario set only |

## Definition of Done

- Every known artifact has a status.
- Every known artifact has a runtime load decision.
- No design artifact is marked for direct runtime upload.
- Old, draft, reference, and archive files are blocked from MI/KB writing unless explicitly used for comparison.
