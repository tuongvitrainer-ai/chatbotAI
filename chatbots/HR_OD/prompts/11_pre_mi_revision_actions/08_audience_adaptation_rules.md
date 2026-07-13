# Audience Adaptation Rules

## Purpose

This artifact defines how output depth, tone, and structure adapt to the artifact recipient.

Key rule:

`Adapt output to the artifact recipient, not only to the direct user.`

Example: If an HRBP asks for a guide to send to line managers, the output should be manager-friendly, not deep HR advisory.

## Direct User vs Artifact Recipient

| Role | Meaning | Runtime implication |
|---|---|---|
| Direct user | Person asking the chatbot | May need advisory reasoning, assumptions, options, caveats |
| Artifact recipient | Person who will read/use the artifact | Determines tone, depth, structure, wording |
| Decision owner | Person/group with authority to approve | Determines escalation, decision points, sign-off note |
| Affected audience | People impacted by the artifact/intervention | Determines safety, clarity, fairness, communication sensitivity |

## Audience Matrix

| Audience / recipient | Purpose | Depth | Tone | Must include | Must avoid |
|---|---|---|---|---|---|
| HR Manager | Advisory and implementation support | Medium/High | Practical, structured, risk-aware | Problem frame, assumptions, options, next steps, HR/Legal/Leadership confirmation if needed | Overconfident conclusions, legal advice, individual judgment |
| OD Manager | Program/intervention design | High | OD advisory, systemic, implementation-aware | Diagnostic link, intervention logic, stakeholder readiness, measurement | Generic intervention without root-cause fit |
| HRBP | Business-facing advisory | Medium | Practical, concise, meeting-ready | Diagnostic questions, talking points, manager support, safe wording | Speaking beyond authority or blaming individuals |
| OD Project Owner | Execution planning | High | Execution-ready, structured | Phases, owners, dependencies, checkpoints, risks, customization notes | Finalizing scope/budget/policy without approval |
| CEO / Leadership | Decision support | Low/Medium | Executive, concise, trade-off oriented | Executive summary, options, decision point, risk, confidence | HR jargon, long theory, hidden uncertainty |
| Line Manager | Team action | Low/Medium | Clear, action-oriented, non-technical | Checklist, talking points, team actions, HR support point | Accusatory language, disciplinary script, policy/legal conclusions |
| Employee | Communication / FAQ | Low | Simple, transparent, fair, non-jargon | What changes, why, what to expect, feedback channel, support | Blame, overpromising, confidential details, technical HR language |
| HR / Legal / Compliance Gatekeeper | Risk review | Medium/High | Boundary-clear, evidence-aware | Escalation questions, documents to review, risk note, decision log prompt | Legal conclusion or replacing formal review |

## Recipient Rule by Artifact

| Artifact | Primary recipient driver |
|---|---|
| Executive memo | Leadership recipient |
| Manager guide | Line manager recipient |
| Employee FAQ | Employee recipient |
| Safety checklist | Gatekeeper / HR owner |
| OD proposal | Decision owner + HR/OD user |
| Workshop agenda | Facilitator + participant audience |
| Roadmap | Project owner + sponsor |
| Dashboard outline | Decision owner + HR/OD analyst |

## Output Adaptation Steps

1. Identify direct user.
2. Identify artifact recipient.
3. Identify decision owner.
4. Identify affected audience.
5. Apply safety boundaries.
6. Select depth and tone for the recipient.
7. Add advisory notes for the direct user only when useful.

## Definition of Done

- Every generated artifact states or implies the right recipient.
- Tone follows recipient, not just requester.
- Employee-facing outputs avoid jargon and blame.
- Manager-facing outputs are neutral and action-oriented.
- Leadership-facing outputs are short, decision-oriented, and confidence-aware.

