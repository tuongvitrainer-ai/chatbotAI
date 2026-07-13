# Verification Register

## Purpose

This register controls how frameworks, models, and technical terms may be used in KB writing.

It prevents the chatbot from presenting unverified frameworks as universal best practice or using named models outside scope.

## Core Rule

The Master Instruction should not contain detailed professional frameworks by default.

Frameworks belong in KB files, usually KB01-KB04, and only with appropriate caveats. The MI may mention framework usage only generically, for example: "Use relevant OD concepts from knowledge files when helpful."

## Decision Types

| Decision | Meaning |
|---|---|
| Keep named | Use the named framework when source status is reliable and scope is appropriate. |
| Genericize | Use the underlying concept without naming the framework as authoritative. |
| Example only | Mention as one possible example, not a standard. |
| Remove | Do not use in MI/KB. |
| Needs external validation | Do not rely on it until a source check is done. |

## Register

| Term / framework | Current location / likely use | Source status | Decision | Runtime wording |
|---|---|---|---|---|
| Kirkpatrick | Training/program evaluation | Needs validation | Example only / Genericize | "evaluation across activity, learning/behavior, and outcome signals" unless sourced |
| 70-20-10 | Learning design | Needs validation | Example only | "mix formal learning, practice, coaching, and workplace application" |
| Mendelow / power-interest grid | Stakeholder mapping | Needs validation | Genericize | "stakeholder influence/interest mapping" |
| RACI | Role clarity / accountability | Common but context-dependent | Keep named in KB04 as template option | "RACI-style role clarity table" with caveat, not decision authority |
| RAPID | Decision rights | Needs validation and company fit | Example only / Genericize | "decision-rights model" unless user asks specifically |
| KPI | Measurement / performance | Common term | Keep named | Use as metric label; do not equate KPI with full impact proof |
| OKR | Goal-setting | Common term but methodology-specific | Keep named with caveat | "OKR-style objective/result draft" when requested or context fits |
| Psychological safety | Team climate / culture | Needs careful use | Keep with caveat | "psychological safety climate" at group level; no individual diagnosis |
| Engagement score | Survey/OD metric | Common but data-dependent | Keep with caveat | Treat as signal, not root cause |
| Culture assessment | OD diagnosis | Data-dependent | Genericize | "culture signals/patterns" unless using a validated assessment |
| Change management | Adjacent domain | Scope drift risk | Rename / constrain | Use "Change Enablement for OD" for readiness/adoption/communication in OD rollout |
| ADKAR / Kotter / Prosci | Change frameworks | Needs source/license/context validation | Example only / avoid by default | Prefer generic readiness/adoption language unless explicitly requested |
| Competency model | Capability system | Common HR construct | Keep generic | "competency framework" with role/context customization |
| Capability academy | L&D/OD program | Context-dependent | Genericize | "capability development program" |
| Data triangulation | Evidence logic | Common research principle | Keep generic | "triangulate across multiple data sources" |
| Correlation / causation | Analytics caution | Common statistical concept | Keep | "correlation does not prove cause" |
| Statistical significance | Analytics | Requires statistical expertise | Boundary | Do not calculate/claim unless user provides valid analysis; recommend analyst review |
| Adverse impact | Legal/fairness analytics | Legal-sensitive | Boundary / Legal review | Mention as "fairness/adverse impact review with qualified HR/Legal/analytics support" |
| Pay equity | Compensation/legal-sensitive | Legal-sensitive | Boundary | Use aggregate structural review only; escalate individual/legal conclusions |
| Heat map | Dashboard artifact | Common visualization | Keep generic | "risk/priority heat map" without pretending precision |
| Pulse survey | Engagement/listening | Common term | Keep | Include anonymity and interpretation caution |
| N<30 heuristic | Diagnosis/privacy caution | Practical heuristic, not law | Keep as caution only | "small samples may reduce reliability and privacy; aggregate where needed" |
| Response rate thresholds | Survey interpretation | Context-dependent | Use as heuristic only | "response rate affects confidence; do not treat threshold as statistical law" |

## Framework Placement

| Content | Placement |
|---|---|
| Named OD/HR framework detail | KB01-KB04 only when useful |
| Hard safety control | MI |
| Framework caution / uncertainty | KB05 |
| Framework selection by task | KB06 |
| Full test of framework correctness | Test/evaluation artifacts, not runtime |

## Best-Practice Language Rule

Avoid "best practice" unless the source is verified and context-independent.

Prefer:

- "A practical pattern is..."
- "A common OD lens is..."
- "One useful way to structure this is..."
- "Given the current assumptions..."
- "This should be validated against your policy/context..."

Avoid:

- "The best practice is..."
- "This model proves..."
- "This is the correct framework..."
- "This will solve..."

## Definition of Done

- Every named framework has a decision.
- MI remains framework-light.
- KB wording avoids false authority.
- Legal, clinical, privacy, and analytics-sensitive terms have caveats or escalation.

