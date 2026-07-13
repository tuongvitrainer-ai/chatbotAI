# Canonical Runtime Flow

## Purpose

This artifact locks the runtime authority order before Master Instruction writing.

The core correction is:

`User request -> MI Safety Gate -> Safety/Escalation or continue -> KB06 router`

KB05 is not the highest safety gate. KB05 provides examples, checklists, validation patterns, confidence patterns, safe alternatives, and safety response shapes. The Master Instruction owns the hard safety priority rules.

## Canonical Flow

```text
1. User request
2. MI Safety Gate
3. Risk classification
   3.1 Safety Risk
   3.2 OD Impact Risk
   3.3 Uncertainty Risk
4. If Safety Risk is present
   -> Safety/Escalation response
   -> refuse unsafe part
   -> provide safe alternative
   -> stop normal advisory for unsafe part
5. If no Safety Risk blocks the request
   -> KB06 task routing
6. Processing pack selection
7. KB selection
8. Output contract selection
9. Audience / artifact recipient adaptation
10. Final Output Gate
```

## Runtime Authority Stack

| Priority | Layer | Owns | Must not do |
|---|---|---|---|
| 1 | Master Instruction | Role, scope, hard safety rules, flow priority, out-of-scope, compact output behavior | Contain long examples, full templates, detailed frameworks |
| 2 | KB05 | Safety examples, validation patterns, assumption/confidence library, safe alternatives | Replace MI hard rules or contradict MI |
| 3 | KB06 | Task routing, flow selection after safety, output selection, depth, multi-task composition | Route before MI Safety Gate or contain safety hard rules as sole authority |
| 4 | KB01-KB04 | Domain, diagnosis, intervention, artifacts | Override safety, router, or output constraints |
| 5 | User request | Desired task, data, preferred format | Override safety, legal, privacy, or individual judgment constraints |

## Risk Classification

| Risk type | Runtime implication | Output control |
|---|---|---|
| Safety Risk | Safety/Escalation overrides normal advisory | Boundary, refusal of unsafe part, safe alternative, escalation point |
| OD Impact Risk | Continue, but add validation/deep advisory controls | Risk matrix, stakeholder readiness, pilot/checkpoint, assumptions |
| Uncertainty Risk | Continue if safe, but control confidence | Assumption Note, Confidence Label, missing data, hypothesis table |

## Safety Gate Rule

The MI Safety Gate checks for:

- Individual judgment.
- Personnel-action artifact.
- Legal/compliance determination.
- Sensitive or identifiable HR data.
- Harassment, discrimination, complaint, retaliation, or ethics issue.
- Biased classification.
- Clinical or wellbeing signal needing expert support.
- Mixed intent containing any unsafe part.

If any high safety trigger is present, the chatbot must not proceed to normal KB06 routing for the unsafe part.

## Corrected Dependency Language

Use this wording in architecture artifacts:

> The Master Instruction runs the hard Safety Gate before normal task routing. KB05 supplies examples, checklists, safe alternatives, and validation patterns used when safety or uncertainty controls are needed. KB06 routes the task only after the request is safe to continue.

Avoid this wording:

> KB06 routes the task, then KB05 checks safety.

## Validation Module

Validation is a module, not a standalone flow.

It can attach to:

- Standard Task Flow.
- Deep OD Advisory Flow.
- Produce outputs.
- Plan outputs.
- Measure/Improve outputs.
- Safety-safe alternatives.

Validation does not automatically mean Safety/Escalation. Safety/Escalation requires a safety trigger.

## Final Output Gate

Before final response, the chatbot checks:

1. Did I pass MI Safety Gate?
2. Did I classify Safety / OD Impact / Uncertainty correctly?
3. Did I route the task after safety, not before?
4. Did I use the right KB owner?
5. Did I add Assumption Note or Confidence Label when needed?
6. Did I adapt output to the artifact recipient?
7. Did I avoid overclaiming or hidden individual judgment?
8. Did I provide a clear next step?

## Definition of Done

- No artifact implies KB06 routes before the MI Safety Gate.
- KB05 is described as safety/validation pattern library, not the highest authority.
- Validation Module is defined as attachable, not a separate default flow.
- Risk classification separates Safety Risk, OD Impact Risk, and Uncertainty Risk.

