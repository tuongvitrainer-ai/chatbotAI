# HR/OD Advisor — Information Architecture Pack v1.0

> Mục đích: thiết kế cấu trúc thông tin cho Knowledge Base của Custom GPT HR/OD Advisor.  
> Phạm vi: IA blueprint để viết KB01–KB06, không viết nội dung KB chi tiết, không viết Master Instruction.

---

## 0. IA Design Principles

1. **Taxonomy dùng một tiêu chí chính:** vai trò runtime của tri thức trong Custom GPT.
2. **Hierarchy dùng để tổ chức file KB:** mỗi KB có vai trò riêng, tránh biến một file thành “kho tổng hợp”.
3. **Matrix phải giúp ra quyết định:** task nào dùng KB nào, intent nào trả output nào.
4. **Entity Relationship Map dùng để kiểm soát logic tư vấn:** problem → symptom → root cause → intervention → artifact → metric → improvement.
5. **Stakeholder không trộn vào domain knowledge:** stakeholder dùng để điều chỉnh output, depth và safety boundary.
6. **Validation & Safety tách riêng:** tránh để safety rule rải rác trong mọi KB.
7. **Output Standards tách riêng:** tránh template bị lặp trong KB domain/intervention.

---

# 1. Knowledge Taxonomy

## 1.1. Tiêu chí phân loại

Taxonomy này phân loại tri thức theo **vai trò runtime khi chatbot xử lý yêu cầu**.

```text
Knowledge role = tri thức này giúp chatbot làm gì tại thời điểm trả lời?
```

Không phân loại theo stakeholder, không phân loại theo artifact, không phân loại theo workflow. Các yếu tố đó được đặt ở các map riêng để tránh trùng cấp.

## 1.2. Taxonomy Table

| Taxonomy group | Vai trò runtime | Nội dung thuộc nhóm | Không chứa | KB chính |
|---|---|---|---|---|
| **Domain Knowledge** | Giúp chatbot hiểu khái niệm, mô hình, miền OD | OD foundations, enterprise context, org design, culture, engagement, leadership, performance, capability, change, measurement concept | Diagnostic template, intervention playbook chi tiết, output template | **KB01** |
| **Diagnostic Knowledge** | Giúp chatbot đọc vấn đề, triệu chứng, dữ liệu và tạo giả thuyết | Symptom patterns, diagnostic layers, root-cause patterns, evidence logic, diagnostic questions, hypothesis structure | Giải pháp can thiệp chi tiết, proposal template | **KB02** |
| **Intervention Knowledge** | Giúp chatbot chọn và thiết kế nhóm can thiệp OD | Intervention groups, fit logic, success conditions, implementation risks, stakeholder engagement logic, change enablement | Diagnostic theory nền, full artifact template | **KB03** |
| **Artifact Knowledge** | Giúp chatbot tạo tài liệu ứng dụng | Proposal, memo, roadmap, workshop agenda, stakeholder map, communication plan, KPI/OKR draft, dashboard outline | Lý thuyết OD dài, safety hard rules | **KB04** |
| **Validation & Safety Knowledge** | Giúp chatbot kiểm soát rủi ro, giả định, thiếu dữ liệu, safety | Safety triggers, no individual judgment, escalation, assumption check, gap analysis, risk matrix, confidence label | Domain explanation chi tiết, intervention catalog | **KB05** |
| **Routing & Output Knowledge** | Giúp chatbot chọn đúng task, flow, depth và output template | Task router, intent pattern, KB selection guide, output contract, depth rules, good/bad output examples | Nội dung chuyên môn dài, safety examples quá chi tiết | **KB06** |

## 1.3. Taxonomy Decision Rule

```text
Nếu tri thức trả lời “đây là gì?” → KB01.
Nếu tri thức trả lời “vấn đề có thể do đâu?” → KB02.
Nếu tri thức trả lời “nên can thiệp bằng gì?” → KB03.
Nếu tri thức trả lời “tạo tài liệu nào / theo format nào?” → KB04 hoặc KB06.
Nếu tri thức trả lời “có rủi ro gì / có được làm không?” → KB05.
Nếu tri thức trả lời “nên dùng flow/output nào?” → KB06.
```

---

# 2. Knowledge Hierarchy

## 2.1. Hierarchy cấp hệ thống

```text
HR/OD Advisor Knowledge System
├── KB01 — OD Domain Map
│   ├── OD foundations & enterprise context
│   ├── Organization system & design
│   ├── Culture, engagement & employee experience
│   ├── Performance & capability systems
│   ├── Leadership & manager effectiveness
│   ├── Change & transformation
│   └── Measurement concepts
│
├── KB02 — Diagnostic Frameworks
│   ├── Diagnostic input types
│   ├── Symptom taxonomy
│   ├── Problem type map
│   ├── Diagnostic layers
│   ├── Root-cause patterns
│   ├── Hypothesis logic
│   └── Diagnostic question bank structure
│
├── KB03 — Intervention Playbook
│   ├── Intervention selection logic
│   ├── Intervention groups
│   ├── Intervention components
│   ├── Implementation conditions
│   ├── Stakeholder engagement logic
│   ├── Risks by intervention type
│   └── Improve / redesign logic
│
├── KB04 — Artifacts & Templates
│   ├── Advisory artifacts
│   ├── Executive artifacts
│   ├── Manager-facing artifacts
│   ├── Employee-facing artifacts
│   ├── Implementation artifacts
│   ├── Measurement artifacts
│   └── Safe alternative artifacts
│
├── KB05 — Validation & Safety
│   ├── Safety / escalation rules
│   ├── No individual judgment boundary
│   ├── Sensitive data handling
│   ├── Epistemic validation
│   ├── Assumption / gap / contradiction checks
│   ├── Risk taxonomy
│   └── Confidence labeling
│
└── KB06 — Output Standards & Task Router
    ├── Intent detection
    ├── Task type router
    ├── Flow / pack selection
    ├── KB selection guide
    ├── Output template selection
    ├── Depth by stakeholder
    └── Final answer quality checklist
```

## 2.2. Hierarchy theo tầng sử dụng runtime

| Runtime layer | Chatbot cần quyết định | KB hỗ trợ chính |
|---|---|---|
| **Layer 1 — Safety gate** | Có safety risk không? Có cần escalation không? | KB05 |
| **Layer 2 — Intent routing** | User muốn Explain, Diagnose, Design, Plan, Produce, Validate, Measure hay Improve? | KB06 |
| **Layer 3 — Knowledge selection** | Cần domain concept, diagnostic logic, intervention logic hay template? | KB01–KB04 |
| **Layer 4 — Output construction** | Output nên là concept note, hypothesis table, roadmap, proposal, risk matrix hay dashboard? | KB04 + KB06 |
| **Layer 5 — Validation add-on** | Có cần assumption note, confidence label, gap check, risk matrix không? | KB05 |
| **Layer 6 — Stakeholder adaptation** | Output gửi cho HR/OD, Leadership, Line Manager hay Employee? | KB06 + KB04 + KB05 |

---

# 3. Entity Relationship Map

## 3.1. Core entities

| Entity | Định nghĩa trong chatbot | Thuộc tính cần lưu/nhận diện | KB chính |
|---|---|---|---|
| **Problem** | Vấn đề tổ chức cần xử lý | Problem type, scope, affected group, business impact, urgency, uncertainty | KB02 |
| **Symptom** | Dấu hiệu bề mặt người dùng quan sát được | Metric/signal, nơi xuất hiện, thời điểm, nhóm bị ảnh hưởng, độ tin cậy dữ liệu | KB02 |
| **Root cause** | Nguyên nhân sâu hoặc pattern hệ thống tạo ra symptom | Layer: individual/team/manager/process/structure/culture/leadership/system; evidence; confidence | KB02 |
| **Stakeholder** | Bên dùng chatbot, nhận artifact, quyết định hoặc chịu ảnh hưởng | Role, quyền quyết định, nhu cầu, risk, depth requirement | KB06 + KB04 |
| **Intervention** | Nhóm can thiệp OD được thiết kế để xử lý root cause/problem | Intervention group, level, target group, owner, activities, success condition, risk | KB03 |
| **Artifact** | Output cụ thể chatbot tạo ra | Artifact type, audience, purpose, format, required sections, boundary note | KB04 + KB06 |
| **Metric** | Chỉ số dùng để đo problem hoặc hiệu quả intervention | Leading/lagging, data source, cadence, owner, baseline, target | KB01 + KB04 |
| **Risk** | Rủi ro safety, uncertainty hoặc OD impact | Risk type, severity, trigger, mitigation, escalation point | KB05 |

## 3.2. Relationship graph dạng text

```text
Problem
├── is indicated by → Symptom
├── affects → Stakeholder
├── belongs to → Problem Type
├── may be caused by → Root Cause
├── creates → Risk
├── requires → Diagnostic Questions
├── is addressed by → Intervention
├── is communicated through → Artifact
├── is measured by → Metric
└── may trigger → Validation / Safety

Symptom
├── suggests → possible Problem Type
├── may be misread as → Root Cause
├── requires → Evidence Check
└── informs → Hypothesis

Root Cause
├── belongs to → Diagnostic Layer
├── supports selection of → Intervention
├── determines → Measurement Focus
└── changes confidence of → Recommendation

Stakeholder
├── shapes → Output Depth
├── receives → Artifact
├── owns / approves → Decision
├── creates / reduces → Risk
└── participates in → Intervention

Intervention
├── addresses → Root Cause / Problem Type
├── requires → Stakeholder Readiness
├── produces → Implementation Artifact
├── creates → OD Impact Risk
├── is measured by → Metric
└── is revised by → Improvement Loop

Artifact
├── serves → Stakeholder
├── expresses → Recommendation
├── must include → Assumption / Boundary when needed
├── may require → HR / Legal / Leadership review
└── supports → Decision / Implementation

Metric
├── measures → Problem / Intervention / Adoption / Experience / Outcome
├── depends on → Data Source
├── informs → Improve
└── changes → Confidence Label

Risk
├── constrains → Output
├── triggers → Validation Module
├── may trigger → Safety / Escalation Flow
└── requires → Mitigation / Escalation
```

## 3.3. ER decision rules

| Nếu chatbot nhận diện | Thì cần hỏi/kiểm tra | Output nên ưu tiên |
|---|---|---|
| Symptom nhưng chưa rõ problem | Scope, affected group, data source, timing | Problem framing + hypothesis table |
| Problem nhưng chưa rõ root cause | Diagnostic layer, competing hypotheses, evidence | Diagnostic report / question bank |
| Root cause có vẻ thuộc structure/process | Decision rights, role clarity, operating model | Org design options / RACI / governance note |
| Root cause có vẻ thuộc culture/leadership | Behavior norms, leadership alignment, trust signals | Culture/leadership intervention options |
| Intervention đã được chọn | Owner, phase, stakeholder, risk, metric | Roadmap / rollout plan |
| Artifact gửi cho Leadership | Business impact, options, decision needed | Executive memo / decision brief |
| Artifact gửi cho Line Manager | Action steps, talking points, HR boundary | Manager guide / checklist |
| Artifact gửi cho Employee | Clarity, fairness, voice channel | Employee communication / FAQ |
| Risk là safety-sensitive | Legal/HR review, individual judgment, data privacy | Safety checklist / neutral template |

---

# 4. Task Type × Knowledge Matrix

## 4.1. Decision purpose

Matrix này giúp Custom GPT chọn **KB ưu tiên** theo task type. Ký hiệu:

- **P = Primary KB**: bắt buộc ưu tiên.
- **S = Supporting KB**: dùng khi cần.
- **V = Validation/Safety add-on**: dùng nếu có rủi ro, dữ liệu yếu hoặc case nhạy cảm.

| Task type | KB01 OD Domain | KB02 Diagnostic | KB03 Intervention | KB04 Artifacts | KB05 Validation & Safety | KB06 Router & Output | Decision rule |
|---|---:|---:|---:|---:|---:|---:|---|
| **Explain** | P |  | S | S | V | S | Dùng KB01 để giải thích; KB06 chọn template concept note. |
| **Compare** | P |  | P | S | V | S | So sánh mô hình/can thiệp cần KB01 + KB03; KB05 nếu có risk. |
| **Diagnose** | S | P |  | S | V | S | Triệu chứng/vấn đề → KB02; thêm KB05 nếu thiếu dữ liệu hoặc safety-sensitive. |
| **Design** | S | S | P | S | V | S | Design solution → KB03; không bỏ qua diagnostic assumption. |
| **Plan** | S |  | P | P | V | S | Roadmap/rollout cần KB03 + KB04. |
| **Produce** |  |  | S | P | V | P | Tạo artifact cần KB04 + KB06; KB05 nếu artifact có risk. |
| **Validate** | S | S | S | S | P | S | Review/gap/risk → KB05; kéo KB liên quan theo nội dung được review. |
| **Measure** | P | S | S | P | V | S | Metric/dashboard cần measurement concepts + dashboard template. |
| **Improve** | S | P | P | S | V | S | Sau triển khai chưa đạt → re-diagnosis + revised intervention. |

## 4.2. Matrix routing notes

```text
Explain không nên kéo toàn bộ KB03 nếu user chỉ hỏi khái niệm.
Diagnose không nên nhảy sang KB03 nếu root cause chưa rõ.
Produce không nên chỉ dùng KB04; phải dùng KB06 để chọn đúng audience/depth.
Validate luôn dùng KB05, nhưng không có nghĩa mọi câu trả lời đều thành Safety Flow.
Improve cần quay lại KB02 trước khi chỉnh KB03.
```

---

# 5. Intent × Output Matrix

## 5.1. Decision purpose

Matrix này giúp chatbot chọn output artifact dựa trên **intent thực tế**, không chỉ dựa vào từ khóa user dùng.

| Intent pattern | Dấu hiệu trong input | Output mặc định | Output phụ nếu cần | Audience/depth rule | Safety/validation add-on |
|---|---|---|---|---|---|
| **Muốn hiểu** | “là gì”, “khác gì”, “giải thích”, “ví dụ” | Concept note | Checklist áp dụng, comparison mini-table | Ngắn nếu HRBP/Manager; sâu hơn nếu OD Manager | Thêm caveat nếu khái niệm dễ bị dùng sai |
| **Muốn chọn giữa phương án** | “nên dùng A hay B”, “so sánh”, “ưu nhược” | Comparison table | Trade-off summary, recommendation | Leadership: decision brief; OD: tiêu chí sâu | Confidence label nếu thiếu bối cảnh |
| **Muốn phân tích vấn đề** | “vì sao”, “nguyên nhân”, “đang xảy ra”, “survey thấp” | Hypothesis table | Root-cause map, diagnostic questions | HR/OD: sâu; HRBP: practical questions | Assumption note + data needed |
| **Muốn thiết kế giải pháp** | “thiết kế chương trình”, “framework”, “intervention” | Solution structure | Intervention options, design principles | OD Manager: deep advisory; Leadership: option summary | Risk matrix nếu tác động rộng |
| **Muốn triển khai** | “roadmap”, “rollout”, “phase”, “owner” | Implementation roadmap | RACI/owner table, stakeholder plan | Project owner: execution-ready | Dependency/risk checkpoint |
| **Muốn tạo tài liệu** | “viết proposal”, “tạo memo”, “agenda”, “checklist” | Requested artifact | Usage note, customization note | Theo người nhận artifact | Boundary note nếu gửi Leadership/Manager/Employee |
| **Muốn phản biện** | “review”, “có thiếu gì”, “rủi ro gì”, “đánh giá” | Gap analysis | Revision memo, risk matrix | HR/OD: cụ thể; Leadership: concise risk summary | Confidence + assumption check |
| **Muốn đo lường** | “KPI”, “OKR”, “dashboard”, “success metrics” | KPI/OKR table | Dashboard outline, feedback loop | Leadership: outcome; OD: indicator logic | Data source caveat |
| **Muốn cải tiến sau triển khai** | “đã triển khai nhưng”, “không hiệu quả”, “feedback cho thấy” | Signal reading + improvement hypotheses | Revised action plan | OD/Project Owner: detailed; Leadership: next decision | Re-diagnosis + confidence label |
| **Có yếu tố cá nhân/pháp lý** | Sa thải, kỷ luật, tố cáo, quấy rối, dữ liệu nhạy cảm | Safety response | Neutral checklist, escalation questions | Safety-first, không quy kết | Safety/Escalation override |

---

# 6. Draft KB Architecture

## 6.1. KB01 — OD Domain Map

| Thành phần | Thiết kế IA |
|---|---|
| **Vai trò** | Cung cấp nền khái niệm và domain map cho Explain, Compare, Measure ở mức khái niệm. |
| **Nội dung nên chứa** | OD foundations; enterprise context; organization design; culture & engagement; performance & capability systems; leadership & manager effectiveness; change & transformation; measurement concepts. |
| **Không chứa** | Diagnostic question bank chi tiết; full intervention playbook; artifact templates; safety examples dài. |
| **Cấu trúc đề xuất** | 1. OD foundations 2. Enterprise context 3. Core OD domains 4. Problem type overview 5. Measurement concepts 6. Common misconceptions. |
| **Dùng cho task** | Explain, Compare, Measure, hỗ trợ Design/Validate. |
| **Output liên quan** | Concept note, explanation, comparison criteria, glossary, measurement concept note. |
| **Dependency** | Gọi KB03 khi cần so sánh intervention; gọi KB04 khi cần tạo artifact. |

## 6.2. KB02 — Diagnostic Frameworks

| Thành phần | Thiết kế IA |
|---|---|
| **Vai trò** | Giúp chatbot chẩn đoán vấn đề tổ chức theo triệu chứng, tầng nguyên nhân và giả thuyết. |
| **Nội dung nên chứa** | Symptom taxonomy; problem type map; diagnostic input types; diagnostic layers; root-cause patterns; hypothesis logic; diagnostic question bank structure; evidence risks. |
| **Không chứa** | Danh mục intervention chi tiết; proposal/roadmap template; lý thuyết OD nền quá dài. |
| **Cấu trúc đề xuất** | 1. Diagnostic principles 2. Input types 3. Symptom → problem map 4. Diagnostic layers 5. Hypothesis table pattern 6. Data needed checklist 7. Diagnostic errors. |
| **Dùng cho task** | Diagnose, Improve, hỗ trợ Design/Validate. |
| **Output liên quan** | Problem framing, hypothesis table, root-cause map, diagnostic questions, confidence note. |
| **Dependency** | Gọi KB05 khi dữ liệu yếu/safety-sensitive; gọi KB03 sau khi có giả thuyết can thiệp. |

## 6.3. KB03 — Intervention Playbook

| Thành phần | Thiết kế IA |
|---|---|
| **Vai trò** | Giúp chatbot chọn và thiết kế intervention phù hợp problem/root cause. |
| **Nội dung nên chứa** | Intervention selection logic; intervention groups; fit by problem type; components; success conditions; stakeholder readiness; implementation risks; improve/redesign logic. |
| **Không chứa** | Diagnostic taxonomy chi tiết; artifact template đầy đủ; safety hard rules. |
| **Cấu trúc đề xuất** | 1. Intervention principles 2. Intervention selection tree 3. Intervention groups 4. Fit matrix by problem type 5. Implementation conditions 6. Risks/anti-patterns 7. Improvement logic. |
| **Dùng cho task** | Compare, Design, Plan, Improve, hỗ trợ Validate. |
| **Output liên quan** | Intervention options, solution structure, program design, roadmap input, risk note. |
| **Dependency** | Gọi KB02 nếu nguyên nhân chưa rõ; gọi KB04 để tạo roadmap/proposal; gọi KB05 nếu impact cao. |

## 6.4. KB04 — Artifacts & Templates

| Thành phần | Thiết kế IA |
|---|---|
| **Vai trò** | Chuẩn hóa các output cụ thể mà chatbot tạo ra. |
| **Nội dung nên chứa** | Proposal, memo, executive brief, stakeholder map, workshop agenda, rollout checklist, change communication plan, manager guide, employee FAQ, KPI/OKR draft, dashboard outline, PIR template, safe artifact templates. |
| **Không chứa** | Domain explanation dài; intervention theory; full safety rule logic. |
| **Cấu trúc đề xuất** | 1. Artifact families 2. Template schema 3. Required fields 4. Audience adaptation 5. Boundary note patterns 6. Good/bad artifact examples. |
| **Dùng cho task** | Produce, Plan, Measure, hỗ trợ Design/Validate/Safety. |
| **Output liên quan** | Tất cả artifact runtime. |
| **Dependency** | Gọi KB06 để chọn đúng template; gọi KB05 để thêm boundary/safety note. |

## 6.5. KB05 — Validation & Safety

| Thành phần | Thiết kế IA |
|---|---|
| **Vai trò** | Kiểm soát safety, dữ liệu nhạy cảm, cá nhân cụ thể, uncertainty và OD impact risk. |
| **Nội dung nên chứa** | Safety triggers; no individual judgment; mixed intent severity; sensitive data handling; safe alternatives; risk taxonomy; epistemic labels; assumption/gap/contradiction checks; confidence label; escalation patterns. |
| **Không chứa** | Domain knowledge dài; artifact templates đầy đủ; routing logic chính. |
| **Cấu trúc đề xuất** | 1. Safety boundary 2. Escalation triggers 3. Safe alternatives 4. Validation module 5. Epistemic labels 6. Confidence labels 7. Risk matrix pattern 8. Safety examples. |
| **Dùng cho task** | Validate, Safety/Escalation, hỗ trợ mọi task khi có risk/uncertainty. |
| **Output liên quan** | Safety response, risk matrix, assumption note, confidence label, gap analysis, neutral checklist. |
| **Dependency** | Ưu tiên cao hơn KB domain; KB04 dùng để tạo safe artifacts. |

## 6.6. KB06 — Output Standards & Task Router

| Thành phần | Thiết kế IA |
|---|---|
| **Vai trò** | Giúp chatbot route đúng task, chọn KB, chọn output template và điều chỉnh độ sâu theo stakeholder. |
| **Nội dung nên chứa** | Intent detection; input pattern; desired output; flow/pack selection; task type × KB map; intent × output map; output contracts; depth rules; final answer checklist; examples of good/bad routing. |
| **Không chứa** | Nội dung OD chi tiết; intervention playbook; safety examples dài. |
| **Cấu trúc đề xuất** | 1. Task router 2. Input pattern recognition 3. Flow/pack selection 4. KB selection guide 5. Output template selection 6. Depth by stakeholder 7. Final response standard. |
| **Dùng cho task** | Tất cả task. |
| **Output liên quan** | Routing decision, output contract, answer structure, user-facing response format. |
| **Dependency** | Gọi KB01–KB05 theo task; không tự thay thế tri thức chuyên môn. |

---

# 7. Trùng lặp cần tránh giữa các KB

## 7.1. Duplication risk table

| Nội dung dễ trùng | Không nên lặp ở | Nên đặt chính ở | Cách xử lý |
|---|---|---|---|
| Problem type map | KB01, KB02, KB03 | KB02 là bản chi tiết; KB01 chỉ overview | KB01 chỉ nêu taxonomy; KB02 chứa symptom/root cause; KB03 chỉ dùng để map intervention. |
| Intervention list | KB01, KB03, KB04 | KB03 | KB01 chỉ định nghĩa intervention ở mức khái niệm; KB04 chỉ template để viết intervention artifact. |
| Output templates | KB03, KB04, KB06 | KB04 | KB06 chỉ chứa selection rule; KB04 chứa schema chi tiết. |
| Task router | MI, KB06, KB01–KB05 | MI + KB06 | MI nêu rule ngắn; KB06 nêu map và ví dụ; KB khác không lặp router. |
| Safety rules | KB05, KB04, KB06 | MI + KB05 | KB04 chỉ chứa boundary note pattern; KB06 chỉ gọi KB05 khi có trigger. |
| Stakeholder adaptation | KB04, KB05, KB06 | KB06 + KB04 | KB06 quyết định depth; KB04 triển khai template theo audience; KB05 chỉ khi safety-sensitive. |
| Measurement | KB01, KB03, KB04 | KB01 concept + KB04 template | KB03 chỉ nói intervention cần measurement layer; không viết dashboard template. |
| Change management | KB01, KB03, KB04 | KB01 concept + KB03 intervention | KB04 chỉ chứa communication/rollout template. |
| Diagnostic questions | KB02, KB06 | KB02 | KB06 chỉ quyết định khi nào cần diagnostic output. |
| Validation tools | KB05, KB06 | KB05 | KB06 chỉ trigger; KB05 chứa method/pattern. |

## 7.2. File ownership rules

```text
KB01 owns: “OD concept / domain meaning”.
KB02 owns: “Problem diagnosis / evidence / hypotheses”.
KB03 owns: “Intervention choice / design / implementation logic”.
KB04 owns: “Artifact schema / template fields / audience variants”.
KB05 owns: “Safety / validation / risk / confidence”.
KB06 owns: “Routing / output selection / response standard”.
```

## 7.3. Cross-reference rules

| Từ KB | Được cross-reference sang | Khi nào |
|---|---|---|
| KB01 | KB02 | Khi concept được dùng để chẩn đoán problem. |
| KB01 | KB03 | Khi concept được so sánh như intervention option. |
| KB02 | KB03 | Khi giả thuyết nguyên nhân đã đủ rõ để thiết kế intervention. |
| KB03 | KB04 | Khi cần biến solution thành roadmap/proposal/template. |
| KB04 | KB05 | Khi artifact có risk, cá nhân, legal, dữ liệu nhạy cảm. |
| KB06 | KB01–KB05 | Luôn dùng để chọn KB theo task và output. |
| KB05 | KB04 | Khi cần tạo safe artifact như checklist, neutral wording, escalation questions. |

---

# 8. Recommended KB File Set

| File name đề xuất | Mục đích | Ghi chú đặt tên |
|---|---|---|
| `KB01_OD_Domain_Map.md` | OD concepts và domain overview | Dùng cho Explain/Compare. |
| `KB02_OD_Diagnostic_Frameworks.md` | Symptom, problem, root cause, diagnostic logic | Dùng cho Diagnose/Improve. |
| `KB03_OD_Intervention_Playbook.md` | Intervention groups và selection/design logic | Dùng cho Design/Plan/Improve. |
| `KB04_OD_Artifacts_and_Templates.md` | Template và artifact schema | Dùng cho Produce/Plan/Measure. |
| `KB05_Validation_and_Safety_Rules.md` | Safety, risk, validation, confidence | Dùng cho Safety/Validate. |
| `KB06_Output_Standards_and_Task_Router.md` | Router, KB selection, output standards, depth | Dùng cho mọi task. |

---

# 9. IA Quality Check

| Tiêu chí | Kết quả |
|---|---|
| Taxonomy dùng một tiêu chí rõ? | Có. Tiêu chí là vai trò runtime của tri thức trong Custom GPT. |
| Hierarchy có dùng được để viết KB01–KB06? | Có. Mỗi KB có vai trò, scope và boundary riêng. |
| Matrix có giúp ra quyết định? | Có. Task × Knowledge chọn KB; Intent × Output chọn artifact/depth. |
| Có tránh trộn stakeholder với domain knowledge? | Có. Stakeholder được dùng để điều chỉnh output và safety, không làm cấp taxonomy chính. |
| Có tránh biến HR/OD Advisor thành HR chatbot tổng quát? | Có. Boundary và KB ownership loại payroll, HR admin, legal, ER investigation, recruitment scoring. |
| Có dùng được để viết Output Contract? | Có. KB04 + KB06 + Stakeholder depth rules là nền cho Output Contract. |
| Có dùng được để viết Safety Rules? | Có. KB05 ownership rõ và gắn với artifact boundary. |

---

# 10. Next Step Recommendation

Nên tiếp tục theo thứ tự:

```text
IA Pack
→ KB01 Outline
→ KB02 Outline
→ KB03 Outline
→ KB04 Output Contract
→ KB05 Safety Rules
→ KB06 Task Router & Output Standards
```

Không nên viết Master Instruction ngay sau IA Pack. Nên hoàn thiện ít nhất KB01–KB06 outline trước để MI không bị ôm quá nhiều nội dung chi tiết.
