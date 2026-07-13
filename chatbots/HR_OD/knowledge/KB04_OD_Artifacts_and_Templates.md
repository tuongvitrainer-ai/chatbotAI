# KB04 — OD Artifacts & Templates

## 1. Purpose

KB04 là knowledge file dùng để tạo **artifact công việc HR/OD** cho các task **Produce, Plan, Measure** và hỗ trợ **Design**.

KB04 trả lời câu hỏi: **artifact nên có cấu trúc như thế nào?**  
KB04 không quyết định intervention, không chẩn đoán root cause, không viết safety hard rules và không thay thế KB02/KB03/KB05/KB06.

Use KB04 when the user asks for:

- Proposal, concept note, executive one-pager.
- Stakeholder map, OD roadmap, rollout plan.
- Workshop agenda, change communication plan.
- Competency framework, KPI/OKR draft, dashboard outline.
- Diagnostic checklist, risk matrix, post-implementation review.
- Manager guide or safe manager-facing enablement artifact.

Runtime dependencies:

- Use **KB02** if the artifact depends on diagnosis or root-cause hypotheses.
- Use **KB03** if the artifact depends on intervention choice or solution structure.
- Use **KB05** if artifact touches safety, sensitive data, individual judgment, OD Impact Risk, weak evidence or approval risk.
- Use **KB06** to choose task type, output depth, audience and staged response.

Global template rules:

- Every artifact should state **Purpose, Recipient, Required Inputs, Assumptions, Draft, Customization Notes** when relevant.
- Do not invent data, benchmarks, KPIs, targets, cost, ROI, dates, headcount, survey results or legal requirements.
- Use placeholders such as `[insert baseline]`, `[insert owner]`, `[insert data source]` when information is missing.
- If missing information changes the nature of the artifact, ask one clarification block and stop, following MI/KB06.
- Do not create personnel-action artifacts: termination, discipline, transfer, rating, promotion/rejection, PIP for a named person, or individual judgment.
- For manager/employee-facing artifacts, use neutral, plain, non-blaming language.

Reusable artifact header:

```markdown
## Artifact
[Artifact name]

## Purpose
[What this artifact will be used for]

## Recipient
[CEO/Leadership / HR-OD / Line Manager / Employee / Cross-functional team]

## Assumption Note
- [Assumption 1]
- [Assumption 2]
- [Data/user input still needed]

## Draft
[Artifact content]

## Customization Notes
- Replace placeholders with real company data.
- Confirm owner, timeline, scope and approval path before use.
- Add KB05 review if sensitive, high-impact or low-data.
```

## 2. Proposal Template

Purpose: propose an OD initiative, intervention or program for approval or alignment.

Use when:

- User asks for proposal, project proposal, program proposal or initiative proposal.
- There is at least a problem statement, target group and intended intervention direction.
- If intervention direction is unclear, use KB02/KB03 first or label the proposal as provisional.

Required inputs:

- Problem / opportunity.
- Target population or scope.
- Proposed intervention or options.
- Sponsor / owner if known.
- Desired decision or approval.
- Available evidence, baseline or assumptions.

Output skeleton:

```markdown
# Proposal: [Initiative Name]

## 1. Executive Summary
[1 short paragraph: problem, proposed direction, expected value, decision needed.]

## 2. Problem / Opportunity
- Current situation: [facts/symptoms]
- Business or OD impact: [impact]
- Evidence available: [data source]
- Evidence still missing: [missing data]

## 3. Objectives
| Objective | Expected behavior / system change | Success signal |
|---|---|---|
| [Objective 1] | [Behavior/process/outcome] | [Signal, not invented target] |

## 4. Proposed Intervention
| Component | Purpose | Target group | Owner | Notes |
|---|---|---|---|---|
| [Component] | [Why it exists] | [Group] | [Owner/TBD] | [Assumption] |

## 5. Options Considered
| Option | Fit with diagnosis | Pros | Risks | Data needed |
|---|---|---|---|---|
| Option A | [High/Medium/Low] | [...] | [...] | [...] |
| Option B | [High/Medium/Low] | [...] | [...] | [...] |

## 6. Implementation Approach
- Phase 1: [Discovery / alignment / design]
- Phase 2: [Pilot / enablement]
- Phase 3: [Scale / sustain]

## 7. Stakeholders
| Stakeholder | Role | Needed from them |
|---|---|---|
| [Sponsor] | [Decision/resource] | [Ask] |

## 8. Risks and Mitigations
| Risk | Impact | Mitigation |
|---|---|---|
| [Risk] | [Impact] | [Mitigation] |

## 9. Measurement
| Metric type | Indicator | Data source | Cadence |
|---|---|---|---|
| Outcome | [Indicator] | [Source] | [Cadence] |
| Leading | [Indicator] | [Source] | [Cadence] |
| Adoption | [Indicator] | [Source] | [Cadence] |
| Experience | [Indicator] | [Source] | [Cadence] |

## 10. Decision Needed
- Approval requested: [approval]
- Open decisions: [decision list]
- Next step: [next action]

## Assumption Note
- [What is assumed because user did not provide full data]

## Customization Notes
- Replace [baseline], [target], [cost], [timeline] only with confirmed data.
- For CEO/CFO version, add investment rationale and approval ask.
- For HR/OD version, add diagnostic logic and implementation detail.
```

Business case variant:

```markdown
## Investment / Business Rationale
- Strategic rationale: [why invest]
- Options considered: [option summary]
- Investment required: [only if provided]
- Expected value: [qualitative or user-provided quantitative value]
- Risk if not done: [risk]
- Approval needed: [decision]
```

Boundary note: Do not write proposal content that recommends action against a named person. Reframe to system/process/role/capability intervention.

## 3. Concept Note Template

Purpose: describe an early OD idea before full proposal or roadmap.

Use when:

- User wants a short concept note, initiative outline or one-page idea.
- The initiative is not yet fully designed.
- Leadership or HR/OD needs alignment before deeper work.

Required inputs:

- Working title.
- Problem/opportunity.
- Intended audience/beneficiaries.
- Initial intervention idea.
- Why now.

Output skeleton:

```markdown
# Concept Note: [Working Title]

## 1. Background
[Brief context. Use facts only if provided.]

## 2. Problem / Opportunity
- What is happening:
- Why it matters:
- What is unknown:

## 3. Concept
[Describe the proposed idea in 3-5 bullets.]

## 4. Intended Outcomes
| Outcome | Type | Early signal |
|---|---|---|
| [Outcome] | Business / OD / experience | [Signal] |

## 5. Target Group
- Primary group:
- Secondary group:
- Stakeholders affected:

## 6. Initial Design Principles
1. [Principle]
2. [Principle]
3. [Principle]

## 7. Possible Components
| Component | Purpose | Notes |
|---|---|---|
| [Component] | [Purpose] | [TBD] |

## 8. Open Questions
- [Question 1]
- [Question 2]
- [Question 3]

## 9. Proposed Next Step
[Diagnostic review / sponsor alignment / pilot design / proposal development]

## Assumption Note
- This concept is provisional until [data/approval/context] is confirmed.

## Customization Notes
- For executive one-pager, compress sections 1-9 into Issue / Options / Decision Needed.
- For HR/OD working note, keep open questions and data needs visible.
```

Executive one-pager variant:

```markdown
# One-pager: [Topic]

## Issue
[1-2 bullets]

## Context
[2-3 bullets]

## Options
| Option | Benefit | Risk | Decision implication |
|---|---|---|---|

## Recommendation
[Conditional recommendation, not absolute if evidence is weak.]

## Decision Needed
[Specific decision / approval / direction]
```

## 4. Stakeholder Map Template

Purpose: identify who sponsors, owns, influences, implements and is affected by an OD initiative.

Use when:

- User needs stakeholder map, engagement plan or change planning input.
- Initiative has multiple functions, managers or employee groups.
- Roadmap depends on alignment and adoption.

Required inputs:

- Initiative / intervention.
- Scope.
- Known stakeholder groups.
- Decision owner if known.

Output skeleton:

```markdown
# Stakeholder Map: [Initiative]

## 1. Scope
- Initiative:
- Target group:
- Decision context:

## 2. Stakeholder Overview
| Stakeholder group | Role | Influence | Impacted by change | Current readiness | Engagement need |
|---|---|---|---|---|---|
| Sponsor / Leadership | Decision/resource | High/Medium/Low | High/Medium/Low | [Known/TBD] | [Align/approve/model] |
| HR/OD owner | Design/coordinate | ... | ... | ... | ... |
| Line managers | Adoption/translation | ... | ... | ... | ... |
| Employees / affected groups | Experience/feedback | ... | ... | ... | ... |
| Process owners | Operational change | ... | ... | ... | ... |

## 3. Stakeholder Needs
| Stakeholder | What they need to understand | What they need to do | Risk if not engaged |
|---|---|---|---|
| [Group] | [Message/clarity] | [Action] | [Risk] |

## 4. Engagement Approach
| Stakeholder | Engagement method | Timing | Owner | Feedback channel |
|---|---|---|---|---|
| [Group] | [Meeting/comms/listening/pilot] | [Timing] | [Owner] | [Channel] |

## 5. Alignment Risks
- [Risk]
- [Risk]

## Assumption Note
- Readiness and influence levels are placeholders unless confirmed by stakeholder data.

## Customization Notes
- Do not list named employees unless user has a legitimate and safe reason.
- For sensitive cases, use stakeholder groups and roles, not identifiable individuals.
```

## 5. OD Roadmap Template

Purpose: turn a chosen OD solution direction into a phased implementation view.

Use when:

- User has a solution direction or wants a provisional roadmap.
- Work requires phases, owner, checkpoint, risks and measurement.
- If root cause or solution is unclear, use KB02/KB03 first or label roadmap provisional.

Required inputs:

- Intervention/solution direction.
- Scope and target group.
- Timeline or constraints.
- Owner/sponsor if known.
- Key milestones or desired launch date if known.

Output skeleton:

```markdown
# OD Roadmap: [Initiative]

## 1. Planning Basis
- Solution direction:
- Scope:
- Target group:
- Sponsor / owner:
- Key assumptions:
- Not ready for rollout until: [conditions]

## 2. Roadmap by Phase
| Phase | Objective | Key activities | Owner | Deliverable | Checkpoint | Risk |
|---|---|---|---|---|---|---|
| Phase 1: Diagnose / Align | [Objective] | [Activities] | [Owner/TBD] | [Deliverable] | [Checkpoint] | [Risk] |
| Phase 2: Design / Pilot | [Objective] | [Activities] | [Owner/TBD] | [Deliverable] | [Checkpoint] | [Risk] |
| Phase 3: Rollout / Enable | [Objective] | [Activities] | [Owner/TBD] | [Deliverable] | [Checkpoint] | [Risk] |
| Phase 4: Sustain / Improve | [Objective] | [Activities] | [Owner/TBD] | [Deliverable] | [Checkpoint] | [Risk] |

## 3. Decision Gates
| Gate | Decision | Evidence needed | Decision owner |
|---|---|---|---|
| Gate 1 | Proceed to pilot? | [Evidence] | [Owner] |
| Gate 2 | Scale / adjust / stop? | [Evidence] | [Owner] |

## 4. Stakeholder Engagement
| Stakeholder | Engagement action | Timing | Owner |
|---|---|---|---|

## 5. Measurement Cadence
| Review point | What to review | Data source | Action if signal is weak |
|---|---|---|---|

## 6. Key Risks
| Risk | Severity | Mitigation | Owner |
|---|---|---|---|

## Assumption Note
- Timeline, owner and checkpoint are draft placeholders unless user provided them.

## Customization Notes
- Do not produce a detailed rollout plan when diagnosis confidence is Low.
- For enterprise-wide rollout, add KB05 validation: readiness, workload, fairness, adoption and approval gates.
```

## 6. Workshop Agenda Template

Purpose: structure an OD workshop for alignment, diagnosis, design, readiness or learning.

Use when:

- User asks for workshop agenda, session plan or alignment meeting.
- The workshop supports an OD intervention, not personal evaluation.

Required inputs:

- Workshop purpose.
- Participants.
- Duration.
- Desired output.
- Context/intervention.

Output skeleton:

```markdown
# Workshop Agenda: [Workshop Name]

## 1. Purpose
[What the workshop should achieve]

## 2. Participants
- Required:
- Optional:
- Facilitator:

## 3. Pre-work
- [Data/readings/questions participants should prepare]

## 4. Agenda
| Time | Segment | Purpose | Activity | Output |
|---|---|---|---|---|
| [Time] | Opening/context | Align purpose | [Activity] | Shared objective |
| [Time] | Current state | Understand facts and assumptions | [Activity] | Issue list |
| [Time] | Root cause / design discussion | Identify hypotheses/options | [Activity] | Hypothesis/option table |
| [Time] | Decision / prioritization | Select next step | [Activity] | Decision or shortlist |
| [Time] | Action planning | Confirm owners/checkpoints | [Activity] | Action list |

## 5. Facilitation Notes
- Keep discussion system/process-focused.
- Separate facts, assumptions and opinions.
- Capture unresolved decisions.

## 6. Expected Outputs
- [Output 1]
- [Output 2]
- [Output 3]

## 7. Follow-up
| Action | Owner | Due date | Checkpoint |
|---|---|---|---|

## Assumption Note
- Agenda assumes [duration] and [participant group]. Adjust if different.

## Customization Notes
- For leadership workshop: emphasize decisions, trade-offs and sponsor commitments.
- For manager workshop: use practical language and avoid OD jargon.
- Do not design workshops to judge or rank individual employees/managers.
```

## 7. Change Communication Plan Template

Purpose: plan communication for an OD change or rollout.

Use when:

- User needs communication plan, cascade plan or change narrative.
- There is a defined change/intervention.
- If intervention is not clear, use KB03 first.

Required inputs:

- Change/intervention.
- Audience groups.
- Timing.
- Desired action or understanding.
- Known concerns.

Output skeleton:

```markdown
# Change Communication Plan: [Change / Initiative]

## 1. Communication Objective
- What people need to understand:
- What people need to do:
- What concerns must be addressed:

## 2. Audience Map
| Audience | What changes for them | Likely concerns | Message focus | Channel |
|---|---|---|---|---|
| Leadership | [Change] | [Concern] | [Message] | [Channel] |
| Line managers | [Change] | [Concern] | [Message] | [Channel] |
| Employees | [Change] | [Concern] | [Message] | [Channel] |

## 3. Core Narrative
- Why this change:
- What will change:
- What will not change:
- What support is available:
- How feedback will be heard:

## 4. Message Calendar
| Timing | Audience | Message | Channel | Owner | Feedback mechanism |
|---|---|---|---|---|---|

## 5. Manager Cascade
| Manager need | Support material | Timing | Owner |
|---|---|---|---|

## 6. Feedback and Listening
- Feedback channels:
- How feedback will be reviewed:
- How actions will be communicated back:

## 7. Risk and Mitigation
| Communication risk | Impact | Mitigation |
|---|---|---|

## Assumption Note
- Messages are draft placeholders until final leadership decision and policy/legal review if needed.

## Customization Notes
- Employee-facing text must be plain, respectful and non-blaming.
- Do not promise outcomes that are not approved.
- Do not disclose sensitive HR data or identify groups too small to protect privacy.
```

## 8. Competency Framework Template

Purpose: structure a role/group-level competency framework for OD, leadership, manager capability or capability building.

Use when:

- User asks for competency framework, capability model or role-based capability structure.
- The framework is for group/role development, not judging a named person.

Required inputs:

- Role/group.
- Strategic or role context.
- Critical work outcomes.
- Intended use: development, hiring input, performance conversation support, learning pathway.

Output skeleton:

```markdown
# Competency Framework: [Role / Group]

## 1. Purpose and Use
- Purpose:
- Intended use:
- Not intended for:

## 2. Scope
- Role/group covered:
- Business context:
- Assumptions:

## 3. Competency Overview
| Competency cluster | Why it matters | Observable behaviors |
|---|---|---|
| [Cluster 1] | [Rationale] | [Behavior examples] |
| [Cluster 2] | [Rationale] | [Behavior examples] |

## 4. Proficiency Levels
| Level | Description | Observable evidence |
|---|---|---|
| Foundational | [Description] | [Evidence] |
| Proficient | [Description] | [Evidence] |
| Advanced | [Description] | [Evidence] |

## 5. Development Link
| Competency | Development approach | Practice opportunity | Manager reinforcement |
|---|---|---|---|

## 6. Measurement / Review
| Signal | Data source | Cadence | Caution |
|---|---|---|---|

## 7. Governance and Fairness Notes
- Use at role/group level unless formal governance allows individual application.
- Do not use this draft to make individual employment decisions.
- Validate language for bias and job relevance.

## Assumption Note
- Competency clusters are provisional until validated with role analysis and business stakeholders.

## Customization Notes
- Keep the model short enough for managers to use.
- Replace generic behaviors with real critical tasks from the company.
```

## 9. KPI/OKR Draft Template

Purpose: draft measurement logic for an OD initiative or system-level improvement.

Use when:

- User asks for KPI, OKR, success metrics or measurement draft.
- There is a defined outcome or intervention.

Required inputs:

- Initiative/intervention.
- Desired outcome.
- Target group/scope.
- Available data sources.
- Baseline if available.

Output skeleton:

```markdown
# KPI / OKR Draft: [Initiative]

## 1. Measurement Goal
[What decision these metrics should support]

## 2. Outcome Statement
[Desired organizational / behavior / experience outcome]

## 3. OKR Draft
| Objective | Key Result | Metric type | Data source | Baseline | Target | Cadence | Caution |
|---|---|---|---|---|---|---|---|
| [Objective] | [KR] | Outcome / Leading / Adoption / Experience | [Source] | [TBD] | [TBD] | [Cadence] | [Caution] |

## 4. KPI Set
| KPI | Definition | Data source | Owner | Review cadence | Interpretation note |
|---|---|---|---|---|---|

## 5. Balanced Indicator Check
| Indicator type | Included? | Notes |
|---|---|---|
| Outcome | Yes/No | [Note] |
| Leading | Yes/No | [Note] |
| Adoption | Yes/No | [Note] |
| Experience | Yes/No | [Note] |

## 6. Data Gaps
- Missing baseline:
- Missing data source:
- Risk of misinterpretation:

## Assumption Note
- Targets and benchmarks are not invented. Use [TBD] until confirmed by company data.

## Customization Notes
- Do not use individual KPIs unless governance, fairness and privacy rules are confirmed.
- Do not claim intervention impact from activity metrics alone.
```

## 10. Dashboard Outline Template

Purpose: outline a dashboard for monitoring an OD initiative, not building a technical BI dashboard.

Use when:

- User asks for dashboard outline, measurement dashboard or tracking view.
- Need to define sections, indicators, sources and cadence.

Required inputs:

- Initiative/intervention.
- Audience of dashboard.
- Decision the dashboard supports.
- Data sources.

Output skeleton:

```markdown
# Dashboard Outline: [Initiative]

## 1. Dashboard Purpose
- Audience:
- Decision supported:
- Review cadence:

## 2. Top Summary
| Item | Display |
|---|---|
| Status | [Green/Amber/Red or narrative status, if criteria defined] |
| Key movement | [What changed] |
| Decision needed | [Decision] |

## 3. Indicator Sections
| Section | Indicators | Data source | Update cadence | Interpretation caution |
|---|---|---|---|---|
| Outcome | [Indicators] | [Source] | [Cadence] | [Caution] |
| Leading | [Indicators] | [Source] | [Cadence] | [Caution] |
| Adoption | [Indicators] | [Source] | [Cadence] | [Caution] |
| Experience | [Indicators] | [Source] | [Cadence] | [Caution] |
| Risk / readiness | [Indicators] | [Source] | [Cadence] | [Caution] |

## 4. Segment View
| Segment | Why review | Privacy note |
|---|---|---|
| [BU/function/location/role group] | [Reason] | Use aggregate groups only |

## 5. Decision Rules
| Signal | Interpretation | Action |
|---|---|---|
| [Signal] | [Meaning] | Continue / adjust / investigate |

## 6. Data Quality Notes
- Baseline availability:
- Missing data:
- Privacy/anonymization:
- Small group caution:

## Assumption Note
- Dashboard fields are placeholders until data sources and governance are confirmed.

## Customization Notes
- Keep dashboard simple enough for review meetings.
- Do not include identifiable employee-level data.
- Do not present correlation as causation.
```

## 11. Diagnostic Checklist Template

Purpose: help HR/OD collect and organize information before diagnosis, design or proposal.

Use when:

- User needs checklist to diagnose a problem.
- User wants to prepare for stakeholder discussion.
- Output should remain a checklist, not a final diagnosis.

Required inputs:

- Problem/symptom.
- Scope.
- Intended decision.

Output skeleton:

```markdown
# Diagnostic Checklist: [Problem / Symptom]

## 1. Problem Framing
- Symptom:
- Scope:
- When it started:
- Affected groups:
- Decision this diagnosis will support:

## 2. Fact / Interpretation / Assumption
| Item | Type | Source | Confidence |
|---|---|---|---|
| [Item] | Fact / Interpretation / Assumption | [Source] | Low/Medium/High |

## 3. Data to Collect
| Data needed | Why needed | Source | Owner | Privacy note |
|---|---|---|---|---|

## 4. Root-cause Lenses
| Lens | Questions |
|---|---|
| Individual/role condition | Are role expectations, skill, workload and authority clear? |
| Team/manager system | Are norms, manager cadence and team climate supporting the work? |
| Process | Are handoffs, workflow and escalation clear? |
| Structure | Are decision rights, spans and interfaces clear? |
| Culture/system | Are incentives, trust, leadership behavior and governance aligned? |

## 5. Safety and Boundary Check
- Any named individuals?
- Any sensitive HR data?
- Any legal/compliance/personnel-action risk?
- Any small group that may be identifiable?

## 6. Diagnostic Output Needed
- Hypothesis table:
- Root-cause map:
- Stakeholder interview guide:
- Data review:

## Assumption Note
- Checklist does not conclude root cause. It prepares evidence for KB02 diagnosis.

## Customization Notes
- Use anonymized and aggregate data.
- For sensitive cases, use KB05 before analysis.
```

## 12. Risk Matrix Template

Purpose: identify and prioritize risks in an OD plan, intervention, artifact or rollout.

Use when:

- User asks for risk matrix, gap/risk review or readiness check.
- Artifact has OD Impact Risk, Uncertainty Risk or safety sensitivity.

Required inputs:

- Initiative/artifact being reviewed.
- Scope.
- Known risks or constraints.
- Decision context.

Output skeleton:

```markdown
# Risk Matrix: [Initiative / Artifact]

## 1. Risk Summary
- Overall risk level: [Low/Medium/High]
- Main risk type: Safety / OD Impact / Uncertainty / Execution / Measurement
- Decision implication:

## 2. Risk Matrix
| Risk | Risk type | Likelihood | Impact | Severity | Evidence / assumption | Mitigation | Owner |
|---|---|---|---|---|---|---|---|
| [Risk] | [Type] | Low/Medium/High | Low/Medium/High | Low/Medium/High | [Evidence/assumption] | [Mitigation] | [Owner/TBD] |

## 3. OD Impact Risks
- Scale / affected groups:
- Workload / change fatigue:
- Fairness perception:
- Adoption risk:
- Sponsor/readiness risk:

## 4. Uncertainty Risks
- Missing data:
- Weak baseline:
- Competing hypotheses:
- Assumptions that could change decision:

## 5. Safety Boundary
- Individual judgment risk:
- Personnel-action artifact risk:
- Sensitive data risk:
- Legal/compliance boundary:

## 6. Recommended Controls
| Control | When needed | Notes |
|---|---|---|
| Pilot | [Condition] | [Notes] |
| Approval gate | [Condition] | [Notes] |
| Data validation | [Condition] | [Notes] |
| Communication review | [Condition] | [Notes] |
| KB05 safety review | [Condition] | [Notes] |

## Assumption Note
- Risk levels are provisional unless likelihood/impact criteria are defined by the organization.

## Customization Notes
- Do not mark Safety Risk as resolved without appropriate HR/Legal/Compliance review.
- Do not use this matrix to justify action against a named individual.
```

## 13. Post-implementation Review Template

Purpose: review what happened after an OD intervention and decide continue, adjust, scale, pause or redesign.

Use when:

- User asks for PIR, after-action review, learning memo or improvement review.
- There is an implemented intervention or pilot.

Required inputs:

- Intervention.
- Baseline or pre-implementation assumptions.
- Timeline.
- Available signals: adoption, outcome, experience, feedback.

Output skeleton:

```markdown
# Post-implementation Review: [Initiative]

## 1. Review Purpose
- Intervention reviewed:
- Review period:
- Decision needed:

## 2. Original Intent
| Objective | Intended outcome | Success signal |
|---|---|---|

## 3. Implementation Summary
| Component | Planned | Actual | Variance |
|---|---|---|---|

## 4. Evidence Review
| Signal type | Evidence | Interpretation | Confidence | Caveat |
|---|---|---|---|---|
| Outcome | [Evidence] | [Interpretation] | Low/Medium/High | [Caveat] |
| Leading | [Evidence] | [Interpretation] | ... | ... |
| Adoption | [Evidence] | [Interpretation] | ... | ... |
| Experience | [Evidence] | [Interpretation] | ... | ... |

## 5. What Worked
- [Learning]
- [Learning]

## 6. What Did Not Work / Open Issues
- [Issue]
- [Issue]

## 7. Improvement Hypotheses
| Hypothesis | Evidence | Alternative explanation | Data needed | Next action |
|---|---|---|---|---|

## 8. Decision Recommendation
- Continue:
- Adjust:
- Scale:
- Pause:
- Redesign:

## 9. Next Review
- Owner:
- Date/cadence:
- Evidence to collect:

## Assumption Note
- Do not conclude impact if baseline, comparison or sufficient data is missing.

## Customization Notes
- Use KB02/KB03 Improve logic if outcome is weak.
- Do not blame managers or employees; identify design, adoption, measurement and context factors.
```

## 14. Manager Guide Template

Purpose: help line managers explain, enable or support an OD initiative safely and consistently.

Use when:

- User asks for manager guide, manager checklist, manager talking points or implementation guide.
- The topic is a system/process/OD change, not a personnel-action case against an individual.

Required inputs:

- Initiative/change.
- Manager role.
- Employee audience.
- Key message and expected action.
- Boundaries or approval notes.

Output skeleton:

```markdown
# Manager Guide: [Initiative / Change]

## 1. Purpose of This Guide
[What managers should use this guide for]

## 2. What Is Changing
- [Change 1]
- [Change 2]
- What is not changing:

## 3. Why It Matters
[Plain-language explanation linked to team/work/system outcome]

## 4. Manager Role
| Manager responsibility | What to do | What to avoid |
|---|---|---|
| Explain | [Action] | [Avoid jargon/blame] |
| Listen | [Action] | [Avoid defensiveness] |
| Support | [Action] | [Avoid promises not approved] |
| Escalate | [Action] | [Avoid handling sensitive cases alone] |

## 5. Team Conversation Guide
### Opening
[Neutral opening statement]

### Key messages
1. [Message]
2. [Message]
3. [Message]

### Questions to ask
- What is clear?
- What feels difficult or risky?
- What support would help the team adopt this?

### Questions managers may receive
| Employee question | Suggested response principle |
|---|---|
| [Question] | [Neutral response principle] |

## 6. Do / Do Not
| Do | Do not |
|---|---|
| Use facts and approved messages | Blame employees or other teams |
| Invite feedback | Force disclosure of sensitive personal information |
| Escalate concerns appropriately | Make legal/HR promises without approval |
| Focus on role/process/team support | Judge individual performance/personality |

## 7. Follow-up Actions
| Action | Timing | Owner | Evidence / feedback |
|---|---|---|---|

## 8. Escalation Cues
Escalate to HR/OD/Legal/Compliance if the conversation involves:
- Discrimination, harassment, retaliation or grievance.
- Health/clinical/wellbeing crisis.
- Personnel action, discipline, termination or individual rating.
- Sensitive or identifiable HR data.

## Assumption Note
- This guide assumes the initiative and key messages have been approved.

## Customization Notes
- Use manager-friendly language.
- Keep talking points neutral and non-accusatory.
- For individual performance or discipline matters, do not use this template; use KB05 safe alternatives and internal HR process.
```

## 15. Usage Notes and Customization Rules

### 15.1. Choose the Template

| User asks for | Use template |
|---|---|
| “Viết proposal / đề xuất chương trình” | Proposal Template |
| “Tạo concept / phác thảo ý tưởng” | Concept Note Template |
| “Ai liên quan / stakeholder plan” | Stakeholder Map Template |
| “Roadmap / rollout / kế hoạch triển khai” | OD Roadmap Template |
| “Agenda workshop” | Workshop Agenda Template |
| “Kế hoạch truyền thông thay đổi” | Change Communication Plan Template |
| “Competency / capability framework” | Competency Framework Template |
| “KPI / OKR / đo thành công” | KPI/OKR Draft Template |
| “Dashboard outline” | Dashboard Outline Template |
| “Checklist chẩn đoán” | Diagnostic Checklist Template |
| “Risk matrix / rà rủi ro” | Risk Matrix Template |
| “PIR / review sau triển khai” | Post-implementation Review Template |
| “Guide cho line manager” | Manager Guide Template |

### 15.2. Required Customization by Recipient

| Artifact recipient | Style | Must include | Avoid |
|---|---|---|---|
| CEO / Leadership | Executive, concise, decision-oriented | Decision needed, risk, trade-off, investment/impact | Long OD theory, operational detail |
| HR / OD Manager | Structured advisory, enough detail | Assumptions, risks, owner, measurement, next step | Over-simple generic tips |
| HRBP | Practical advisory, business-facing | Talking points, stakeholder tension, safe escalation | Acting as legal/ER decision maker |
| Line Manager | Plain, practical, action-focused | What to say/do, what to avoid, escalation cues | Jargon, blame, performance judgment |
| Employee | Plain, respectful, non-blaming | What changes, why, support, feedback channel | Overpromising, sensitive data, internal politics |

### 15.3. Assumption Rules

Include **Assumption Note** when:

- User did not provide scope, audience, owner, timeline, baseline, target group or data source.
- Artifact depends on unverified diagnosis or intervention choice.
- User asks for KPI/OKR/dashboard but baseline or target is missing.
- User asks for roadmap but solution direction is incomplete.
- User asks for proposal but decision owner or approval ask is unclear.

Assumption note pattern:

```markdown
## Assumption Note
- I am assuming [assumption] because [missing input].
- Replace this with confirmed data before use.
- This output should be treated as provisional until [validation needed].
```

### 15.4. Data and KPI Rules

- Do not invent baseline, benchmark, target, ROI, cost, headcount, survey score or productivity number.
- Use `[TBD]`, `[insert actual data]` or qualitative direction when data is missing.
- Do not claim causality from a single metric.
- Do not call training attendance, workshop completion or communication sent a final outcome.
- Use outcome + leading + adoption + experience indicators when measuring OD work.

### 15.5. Safety and Boundary Rules for Artifacts

Do not create:

- Termination email or termination memo.
- Disciplinary warning, PIP or individual performance action.
- Promotion/rejection/rating decision for a named person.
- Legal/compliance determination.
- Artifact that judges a named employee/manager’s ability, motive, character or mental state.
- Analysis of identifiable employee data, named survey comments or small-group data.

Safe alternatives:

| Unsafe request | Safe artifact alternative |
|---|---|
| Termination/discipline email | Fair process checklist + HR/Legal questions + neutral meeting preparation |
| Judge a named manager/employee | Role criteria checklist + evidence needed + system-level diagnostic questions |
| Analyze named survey data | Anonymization instruction + aggregate theme summary template |
| Legal/compliance conclusion | Issues-to-confirm list for HR/Legal/Compliance |
| Blaming communication | Neutral change communication or manager guide |

### 15.6. Quality Check Before Output

Before finalizing any KB04 artifact, verify:

- Artifact type is correct.
- Recipient is clear.
- Purpose is clear.
- Required inputs are either provided or listed as assumptions.
- No fake data, KPI, benchmark, target or date is invented.
- No individual judgment or personnel-action artifact appears.
- Risk/boundary note is included when needed.
- Customization notes tell the user what to replace or approve.
- If artifact is high-impact, sensitive or low-data, KB05 validation is attached.

## Runtime Reminder

KB04 formats artifacts. It does not decide the intervention, diagnose root cause, write unsafe personnel documents, invent data or replace internal approval. Use placeholders and assumptions when data is missing. Use KB05 for safety and validation. Use KB06 for routing, depth and recipient adaptation.
