# HR/OD Advisor — KB Architecture Blueprint v1.1

> **Changelog v1.1:** Bổ sung (1) Vietnam/conglomerate enterprise context cho KB01; (2) data-poor diagnosis patterns và diagnostic bias cho KB02; (3) intervention sequencing, pilot logic, resource constraints cho KB03; (4) 5 templates còn thiếu cho KB04; (5) OD Impact Risk, revision memo, overclaiming prevention cho KB05; (6) multi-task handling, length/format rules, language/tone rules cho KB06; (7) size targets và feedback loops cho dependency map.

## 0. Design Intent

Mục tiêu của KB Architecture này là giúp người viết 6 KB cho Custom GPT **không chồng nội dung**, biết rõ:

* KB nào chứa tri thức domain.
* KB nào chứa logic chẩn đoán.
* KB nào chứa logic can thiệp.
* KB nào chứa template artifact.
* KB nào chứa validation/safety examples.
* KB nào chứa routing/output standards.

Nguyên tắc nền:

```text
MI = luật ưu tiên cao nhất
KB = tri thức, ví dụ, checklist, template, routing pattern
KB không được thay thế hoặc mâu thuẫn với Master Instruction
```

Domain Decomposition Pack đã xác định rõ: cấp 1 của domain tree là **miền tri thức OD**, workflow vận hành được tách riêng, stakeholder map tách riêng, problem type map tách riêng, intervention map tách riêng và boundary map dùng để tránh chatbot trôi sang HR tổng quát.

---

# 1. KB Architecture Blueprint Table

| KB file                                   | Purpose                                                                                                                                                                                                               | Used by task types                                                                                | Must include                                                                                                                                                                                                                                                                                                                     | Must not include                                                                                                                                                                                                         | Dependencies                                                                                                                                                                                                  | Overlap risks                                                                                                                                                                                | Example queries using this KB                                                                                                                                                                                                                           |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **KB01 — OD Domain Map**                  | Cung cấp bản đồ tri thức nền về OD trong bối cảnh tập đoàn. Giúp chatbot giải thích, phân biệt khái niệm, nhận diện miền vấn đề và hiểu bối cảnh hệ thống.                                                            | Explain, Compare, Measure, một phần Diagnose/Design khi cần nền khái niệm.                        | OD fundamentals; enterprise context; organization system/design; culture & engagement; leadership & manager capability; performance & capability systems; change & transformation; measurement basics; problem type taxonomy ở mức khái quát.                                                                                    | Không chứa diagnostic framework chi tiết; không chứa hypothesis table; không hướng dẫn chọn intervention sâu; không chứa template proposal/agenda; không chứa safety hard rules; không chứa task router.                 | Là nền cho KB02, KB03, KB04. KB02 dùng khái niệm từ KB01 để chẩn đoán; KB03 dùng domain concepts để chọn can thiệp; KB04 dùng thuật ngữ nhất quán khi tạo artifact.                                           | Dễ trùng với KB02 ở phần problem types; dễ trùng với KB03 ở phần intervention concepts; dễ trùng với KB04 nếu đưa quá nhiều template minh họa.                                               | “OD khác gì HRBP và L&D?”; “Culture và engagement khác nhau thế nào?”; “Operating model là gì trong tập đoàn?”; “KPI, OKR và competency liên quan thế nào đến OD?”                                                                                      |
| **KB02 — OD Diagnostic Frameworks**       | Cung cấp logic chẩn đoán vấn đề tổ chức: từ symptom → possible causes → root cause hypotheses → data needed. Giúp chatbot không nhảy thẳng sang giải pháp khi nguyên nhân chưa rõ.                                    | Diagnose, Improve, Validate, một phần Design khi cần pre-diagnosis.                               | Symptom map; problem type map chi tiết; diagnostic layers: individual/team/manager/process/structure/culture/leadership/system; root-cause patterns; diagnostic question bank; hypothesis table patterns; evidence logic; fact/assumption separation; diagnostic risk notes.                                                     | Không đưa khuyến nghị intervention sâu; không viết roadmap triển khai; không chứa template artifact dài; không biến chẩn đoán thành kết luận cá nhân; không chứa legal advice.                                           | Phụ thuộc KB01 để dùng đúng khái niệm; gọi KB05 khi có dữ liệu yếu, safety-sensitive hoặc nguy cơ quy kết cá nhân; chuyển sang KB03 sau khi đã có giả thuyết nguyên nhân hợp lý.                              | Dễ lấn sang KB03 nếu mỗi root cause kèm luôn solution chi tiết; dễ lấn KB05 nếu viết safety hard rule thay vì diagnostic caution; dễ lặp KB01 nếu giải thích lại quá nhiều khái niệm domain. | “Engagement giảm mạnh, nên phân tích nguyên nhân thế nào?”; “Turnover tăng ở BU Sales có thể do đâu?”; “Manager không dùng PMS mới, chẩn đoán thế nào?”; “Phân biệt symptom và root cause trong case silo.”                                             |
| **KB03 — OD Intervention Playbook**       | Cung cấp logic thiết kế và lựa chọn nhóm can thiệp OD phù hợp với problem type, root cause, stakeholder readiness và enterprise context.                                                                              | Design, Plan, Compare, Validate, Improve.                                                         | Intervention groups; when-to-use logic; fit giữa problem type và intervention type; intervention level: team/function/BU/enterprise; design principles; success conditions; implementation risks; stakeholder engagement logic; change enablement logic; measurement layer ở mức liên kết.                                       | Không chứa template artifact chi tiết; không tạo proposal/memo hoàn chỉnh; không chứa diagnostic framework sâu; không chứa safety hard rules; không thay Leadership/HR/Legal quyết định.                                 | Phụ thuộc KB01 để hiểu domain; phụ thuộc KB02 khi cần root cause/hypothesis; phụ thuộc KB04 để chuyển solution thành artifact; phụ thuộc KB05 để kiểm rủi ro và assumption.                                   | Dễ lặp KB02 nếu mô tả lại symptom/root cause quá dài; dễ lặp KB04 nếu đưa full templates; dễ lấn sang project management chung nếu roadmap quá chi tiết ngoài OD.                            | “Nên dùng intervention nào cho culture đổ lỗi?”; “Thiết kế chương trình nâng năng lực manager cấp trung.”; “So sánh manager capability intervention và performance system redesign.”; “Nếu root cause là decision rights mờ thì nên can thiệp thế nào?” |
| **KB04 — OD Artifacts & Templates**       | Cung cấp cấu trúc output và template để chatbot tạo tài liệu ứng dụng trong công việc HR/OD. Đây là file “format hóa artifact”, không phải file dạy domain hoặc quyết định intervention.                              | Produce, Plan, Measure, Safety/Escalation safe artifact, một phần Validate.                       | Proposal template; concept note; executive memo; stakeholder map; workshop agenda; rollout checklist; manager guide; employee communication; change communication plan; competency template; KPI/OKR draft; dashboard outline; post-implementation review template; neutral conversation template; artifact customization notes. | Không giải thích domain dài; không chứa intervention selection logic sâu; không chứa root-cause framework; không chứa safety hard rules; không viết quyết định sa thải/kỷ luật/cá nhân; không chứa routing rule.         | Phụ thuộc KB03 để biết solution/intervention cần đóng gói; phụ thuộc KB05 khi artifact liên quan safety-sensitive; phụ thuộc KB06 để chọn đúng output format theo intent và audience.                         | Dễ lặp KB03 nếu template kèm quá nhiều hướng dẫn chọn can thiệp; dễ lặp KB06 nếu mô tả lại router/output selection; dễ tạo rủi ro nếu template thiếu boundary note cho case nhạy cảm.        | “Viết proposal chương trình nâng năng lực manager.”; “Tạo agenda workshop alignment leadership.”; “Tạo checklist rollout PMS.”; “Viết employee FAQ cho chương trình engagement.”; “Tạo dashboard outline đo hiệu quả OD.”                               |
| **KB05 — Validation & Safety Rules**      | Cung cấp ví dụ, checklist và pattern để kiểm định rủi ro, assumption, dữ liệu yếu, safety-sensitive cases và safe alternative. Đây là file hỗ trợ guardrail, nhưng **hard rules phải nằm trong Master Instruction**.  | Validate, Diagnose, Safety/Escalation, Produce, Plan, Design, Improve.                            | Safety/Escalation examples; No Individual Judgment examples; mixed-intent handling examples; sensitive HR data handling checklist; anonymization guidance; assumption check; confidence labeling; gap analysis; risk matrix examples; safe artifact examples; escalation checklist; neutral wording examples.                    | Không chỉ đặt hard rules ở đây; không mâu thuẫn với MI; không chứa domain explanation dài; không chứa intervention playbook; không chứa full artifact library; không đưa legal advice thay Legal.                        | Phụ thuộc MI để nhận hard rules; hỗ trợ KB02 khi chẩn đoán có nguy cơ quy kết cá nhân; hỗ trợ KB03 khi can thiệp impact cao; hỗ trợ KB04 khi tạo artifact nhạy cảm; hỗ trợ KB06 bằng safety routing examples. | Dễ trùng MI nếu viết lại toàn bộ luật quá dài; dễ trùng KB04 nếu chứa quá nhiều template; dễ trùng KB06 nếu chứa nhiều routing logic thay vì safety pattern.                                 | “Viết email sa thải nhân viên vì performance thấp.”; “Tôi có dữ liệu survey theo tên từng nhân viên, phân tích giúp.”; “Review kế hoạch này có rủi ro công bằng không?”; “Case này có cần Legal xác nhận không?”                                        |
| **KB06 — Output Standards & Task Router** | Cung cấp logic chọn task type, flow, processing pack, output template và depth theo user intent, input pattern, desired output, risk/complexity. Đây là file điều phối câu trả lời, không phải file domain knowledge. | Tất cả task types: Explain, Compare, Diagnose, Design, Plan, Produce, Validate, Measure, Improve. | Task type detection; intent/input/output router; flow selection examples; KB selection guide; output template index; depth rules by audience; direct user vs artifact recipient rule; anti-loop clarification pattern; final output check pattern; examples of good/bad output shape.                                            | Không chứa OD domain content; không chứa diagnostic frameworks chi tiết; không chứa intervention playbook; không chứa full artifact templates; không chứa safety hard rules thay MI; không chứa legal/HR policy content. | Phụ thuộc MI về flow priority và safety; tham chiếu KB01–KB05 để chỉ “khi nào dùng KB nào”; dùng Stakeholder Map để điều chỉnh depth và audience; dùng KB04 để biết artifact nào có template.                 | Dễ trở thành “kho tổng hợp” nếu nhồi domain knowledge; dễ lặp KB04 nếu viết full template; dễ lặp KB05 nếu viết safety rule dài; dễ gây mâu thuẫn nếu router khác MI.                        | “Tôi cần review kế hoạch OD này.”; “Tạo roadmap triển khai chương trình culture change.”; “So sánh 2 phương án intervention.”; “Tôi chưa rõ vấn đề, hãy giúp định khung.”; “Viết bản gửi CEO hay gửi line manager?”                                     |

---

# 2. Ownership Rule giữa các KB

## 2.1. Nguyên tắc 1 — KB01 là “what is / what belongs to OD”

KB01 trả lời:

```text
Khái niệm này là gì?
Nó thuộc miền OD nào?
Nó liên quan gì đến enterprise context?
Nó khác gì với khái niệm gần kề?
```

KB01 không trả lời sâu:

```text
Chẩn đoán case này thế nào?
Chọn intervention nào?
Viết proposal ra sao?
```

## 2.2. Nguyên tắc 2 — KB02 là “why is this happening?”

KB02 trả lời:

```text
Triệu chứng này có thể do đâu?
Có những giả thuyết nguyên nhân nào?
Cần dữ liệu gì để kiểm chứng?
Vấn đề nằm ở tầng cá nhân, team, process, structure, culture, leadership hay system?
```

KB02 chỉ nên nêu intervention ở mức rất nhẹ:

```text
Nếu H1 đúng → cân nhắc nhóm can thiệp A.
Chi tiết intervention xem KB03.
```

## 2.3. Nguyên tắc 3 — KB03 là “what should we design?”

KB03 trả lời:

```text
Can thiệp OD nào phù hợp?
Điều kiện thành công là gì?
Stakeholder nào cần tham gia?
Rủi ro triển khai là gì?
Nên pilot hay rollout toàn hệ thống?
```

KB03 không viết artifact hoàn chỉnh. Artifact thuộc KB04.

## 2.4. Nguyên tắc 4 — KB04 là “how should the artifact look?”

KB04 trả lời:

```text
Proposal gồm những phần nào?
Executive memo nên ngắn đến đâu?
Workshop agenda cấu trúc thế nào?
Manager guide nên viết theo tone nào?
Employee communication cần tránh gì?
```

KB04 không quyết định intervention. Nó đóng gói nội dung đã có từ KB01–KB03.

## 2.5. Nguyên tắc 5 — KB05 là “is this safe, valid, and bounded?”

KB05 trả lời:

```text
Có safety risk không?
Có dữ liệu nhạy cảm không?
Có quy kết cá nhân không?
Có assumption/gap/risk chưa nêu không?
Confidence nên là Low/Medium/High?
Có cần HR/Legal/Leadership xác nhận không?
```

Safety hard rules phải nằm trong MI; KB05 chỉ mở rộng bằng ví dụ, checklist, pattern và safe artifact.

## 2.6. Nguyên tắc 6 — KB06 là “which route and output?”

KB06 trả lời:

```text
Task type là gì?
Flow/pack nào phù hợp?
Dùng KB nào?
Output template nào?
Depth theo audience ra sao?
Có cần hỏi thêm hay dùng assumption note?
```

KB06 không chứa domain knowledge.

---

# 3. KB Writing Order

## Recommended Order

BRD đã khuyến nghị viết Master Instruction trước, sau đó viết KB05 và KB06 sớm vì đây là control layer cho safety, routing, flow và output; hard rules vẫn phải nằm trong Master Instruction.

Thứ tự đề xuất:

```text
0. Master Instruction skeleton
1. KB05 — Validation & Safety Rules
2. KB06 — Output Standards & Task Router
3. KB01 — OD Domain Map
4. KB02 — OD Diagnostic Frameworks
5. KB03 — OD Intervention Playbook
6. KB04 — OD Artifacts & Templates
7. Cross-KB consistency review
8. Test Scenario Set
9. Evaluation Rubric
```

## Vì sao không viết KB01 trước?

Có thể viết KB01 trước nếu chỉ làm knowledge library. Nhưng với Custom GPT nhiều stakeholder, nên viết **KB05 + KB06 sớm** để cố định:

* chatbot được phép / không được phép làm gì;
* task nào route sang flow nào;
* output nào cần template nào;
* artifact nào cần boundary note;
* case nào phải escalation.

Nếu viết domain KB trước nhưng chưa có safety/routing, nội dung dễ trôi thành “bách khoa OD” thay vì chatbot advisory có kiểm soát.

---

# 4. Detailed KB Writing Guidance

## 4.1. KB01 — OD Domain Map

### Writing objective

Tạo bản đồ tri thức OD nền, giúp chatbot hiểu đúng thuật ngữ, mô hình, hệ thống và phạm vi OD trong tập đoàn.

### Suggested internal sections

```markdown
# KB01 — OD Domain Map

## 1. OD Fundamentals
## 2. Enterprise Context — Vietnam Conglomerate
## 3. OD vs. HR vs. L&D vs. Talent — Phân biệt ranh giới
## 4. OD Maturity Levels
## 5. Organization System & Design
## 6. Culture, Engagement & Employee Experience
## 7. Performance & Capability Systems
## 8. Leadership & Manager Effectiveness
## 9. Change & Transformation
## 10. Measurement & Feedback Basics [khái niệm nền, không phải KPI framework]
## 11. Problem Type Taxonomy — High-level
## 12. Common Concept Confusions
## 13. Boundary Notes
```

### Writing depth

* Mỗi node nên có: definition, use context, enterprise example, common confusion, related task types.
* Không đi sâu thành intervention guide.
* Section 10 (Measurement) chỉ viết khái niệm nền — measurement là gì, tại sao OD cần đo. KPI/OKR framework chi tiết thuộc KB04.

### Nội dung tối thiểu cần có — 3 section mới

**Section 2 — Enterprise Context VN Conglomerate:**
* Đặc thù cấu trúc tập đoàn Việt Nam: nhiều tầng quản lý, hierarchy mạnh, decision rights tập trung cấp trên.
* Văn hóa tổ chức đặc thù: face-saving culture, tránh xung đột trực tiếp, relational trust quan trọng hơn task trust.
* Family-owned / state-owned enterprise dynamics: ảnh hưởng đến OD design và stakeholder engagement.
* Hàm ý: chatbot cần nhận diện bối cảnh để không đề xuất intervention phù hợp lý thuyết nhưng không khả thi.

**Section 3 — OD vs HR vs L&D vs Talent:**

| Chức năng | Focus chính | Chatbot hỗ trợ điều gì? |
|-----------|-------------|-------------------------|
| OD | Hệ thống tổ chức, culture, change, capability | Diagnose, Design, Plan, Validate system-level |
| HR | Policy, compliance, employee relations, admin | Out-of-scope (policy, legal, admin) |
| L&D | Training, learning programs | Adjacent — KB03 chỉ đề xuất, không thiết kế curriculum chi tiết |
| Talent | Acquisition, succession, performance rating | Out-of-scope nếu liên quan individual judgment |

**Section 4 — OD Maturity Levels:**
* Level 1 — Reactive: HR xử lý sự cố, chưa có OD có hệ thống.
* Level 2 — Systematic: Có chương trình OD nhưng rời rạc.
* Level 3 — Proactive: OD gắn với chiến lược, có roadmap và measurement.
* Level 4 — Generative: Tổ chức tự học và thích nghi.
* Hàm ý: chatbot cần điều chỉnh độ phức tạp intervention theo maturity level. Tổ chức ở Level 1 không nên áp intervention Level 3.

---

## 4.2. KB02 — OD Diagnostic Frameworks

### Writing objective

Tạo bộ logic giúp chatbot xử lý các input dạng triệu chứng, dữ liệu rời rạc, survey, phản hồi hoặc vấn đề mơ hồ.

### Suggested internal sections

```markdown
# KB02 — OD Diagnostic Frameworks

## 1. Diagnostic Principles
## 2. Symptom → Problem Type Map
## 3. Multi-level Diagnosis
## 4. Systemic vs. Local Problem Distinction
## 5. Data-poor Diagnosis Patterns
## 6. Problem Type Diagnostic Guides
## 7. Root-cause Pattern Library
## 8. Diagnostic Question Bank
## 9. Hypothesis Table Patterns
## 10. Evidence & Data Needed
## 11. Diagnostic Bias & Confounding Factors
## 12. Misdiagnosis Risk Notes
## 13. Safety Trigger During Diagnosis
## 14. Handoff to KB03
```

### Handoff rule

KB02 nên kết thúc bằng:

```text
Based on current hypotheses, possible intervention groups to explore are...
For detailed intervention design, use KB03.
```

Không viết chi tiết chương trình can thiệp trong KB02.

### Nội dung tối thiểu cần có — 4 section mới

**Section 4 — Systemic vs. Local Problem Distinction:**
* Systemic problem: xuất hiện nhiều BU, nhiều tầng, lặp lại theo thời gian → cần intervention cấp hệ thống.
* Local problem: xảy ra tại 1 team hoặc 1 manager → cần xác minh trước khi generalize.
* Nguyên tắc: đừng generalize local problem thành toàn tổ chức. Turnover 1 team ≠ vấn đề văn hóa toàn công ty.
* Checklist phân biệt: có bao nhiêu đơn vị bị ảnh hưởng? Có pattern theo thời gian không? Có nguyên nhân chung không?

**Section 5 — Data-poor Diagnosis Patterns:**
* Khi user cung cấp 1–2 câu mô tả thiếu dữ liệu → chatbot không được kết luận, phải đặt giả thuyết và label confidence thấp.
* Pattern: (1) Acknowledge thiếu data → (2) Đưa 2–3 hypotheses → (3) Gợi ý data cần thu thập → (4) Label: Low Confidence / Provisional.
* Ví dụ: *"Với thông tin hiện có, có thể có 3 giả thuyết: A, B, C. Cần thêm dữ liệu X, Y để xác nhận. Đây là phân tích sơ bộ — không nên dùng làm quyết định cuối."*
* Trigger: dùng KB05 §8 (Assumption Note) và §9 (Confidence Label) khi ở trạng thái này.

**Section 11 — Diagnostic Bias & Confounding Factors:**
* Attribution bias: đổ lỗi cho con người thay vì hệ thống — chatbot cần multi-layer analysis.
* Recency bias: vấn đề gần nhất nổi bật nhất nhưng chưa chắc là root cause.
* Confirmation bias của user: người dùng đã có kết luận sẵn → chatbot cần nêu giả thuyết thay thế.
* Single informant bias: chỉ nghe 1 bên → nhắc user cần triangulate.

**Tách Section 9 thành Section 12 + 13:**
* Section 12 — Misdiagnosis Risk: nhầm symptom với root cause, nhảy sang solution quá sớm, bỏ qua tầng system.
* Section 13 — Safety Trigger During Diagnosis: khi quá trình chẩn đoán dẫn vào case cá nhân nhạy cảm (performance cá nhân, hành vi cá nhân) → trigger KB05 Safety, không tiếp tục chẩn đoán mà không có anonymization.

---

## 4.3. KB03 — OD Intervention Playbook

### Writing objective

Tạo playbook giúp chatbot chọn và thiết kế nhóm can thiệp OD phù hợp sau khi đã có problem framing hoặc diagnostic hypothesis.

### Suggested internal sections

```markdown
# KB03 — OD Intervention Playbook

## 1. Intervention Design Principles
## 2. Intervention Selection Logic
## 3. Intervention Groups
## 4. Problem Type × Intervention Fit
## 5. Intervention Sequencing & Dependency
## 6. Pilot vs. Full Rollout Decision
## 7. Resource & Readiness Constraints
## 8. Stakeholder Readiness Considerations
## 9. Change Fatigue Consideration
## 10. Implementation Risks
## 11. Success Conditions
## 12. Measurement Link (Leading & Lagging Indicators)
## 13. Plan/Improve Patterns
## 14. Handoff to KB04
```

### Handoff rule

KB03 nên kết thúc bằng:

```text
To convert this intervention into a proposal, roadmap, workshop agenda, checklist or communication plan, use KB04.
```

Không viết full artifact trong KB03.

### Nội dung tối thiểu cần có — 4 section mới

**Section 5 — Intervention Sequencing & Dependency:**
* Không phải mọi intervention đều độc lập — có chuỗi logic bắt buộc.
* Ví dụ sequencing:
  - Leadership alignment → TRƯỚC → Culture intervention (không thể change culture khi leaders không aligned)
  - Manager training → TRƯỚC → PMS rollout (không thể dùng PMS khi manager chưa biết cách feedback)
  - Diagnostic shared với stakeholders → TRƯỚC → Design intervention (không thể roll out khi people không hiểu "tại sao")
* Checklist: intervention này phụ thuộc vào điều kiện tiên quyết nào? Điều kiện đó đã có chưa?

**Section 6 — Pilot vs. Full Rollout Decision:**
* Pilot khi: rủi ro cao, tổ chức chưa sẵn sàng, cần validate trước, can thiệp phức tạp về văn hóa.
* Full rollout khi: đã pilot thành công, tổ chức có đủ năng lực, urgency cao, can thiệp đơn giản về process.
* Criteria matrix: risk level × readiness level × complexity level → pilot hay rollout.
* Hàm ý: chatbot không được recommend full rollout ngay khi tổ chức chưa có evidence từ pilot.

**Section 7 — Resource & Readiness Constraints:**
* Khi tổ chức không đủ bandwidth/budget/talent: đề xuất "phased approach" hoặc "lighter version" thay vì ideal intervention.
* Ví dụ: không đủ nhân sự để chạy full OD program → bắt đầu với diagnostic workshop + 1 pilot BU.
* Rule: chatbot phải hỏi hoặc assume về resource constraints trước khi recommend intervention phức tạp.

**Section 9 — Change Fatigue Consideration:**
* Dấu hiệu change fatigue: nhiều dự án OD đang chạy đồng thời, người dùng mô tả nhân viên "mệt mỏi với thay đổi", low participation trong initiatives gần đây.
* Nếu có dấu hiệu change fatigue → prioritize, sequence, không add thêm nhiều initiatives.
* Chatbot cần nhận diện: user có đề cập đến các project OD đang chạy song song không?

**Section 12 — Measurement Link (Leading & Lagging):**
* Mỗi intervention group cần có: leading indicators (dấu hiệu sớm cho thấy đang đúng hướng) + lagging indicators (kết quả cuối).
* Ví dụ Culture intervention: Leading = manager model behavior check-in, lagging = engagement score Q2 vs Q0.
* Ví dụ Manager capability: Leading = 1:1 frequency, feedback quality rating, lagging = team performance + retention.
* Measurement chỉ là link — full KPI/OKR template thuộc KB04.

---

## 4.4. KB04 — OD Artifacts & Templates

### Writing objective

Tạo thư viện template giúp chatbot produce output dùng được trong công việc HR/OD.

### Suggested internal sections

```markdown
# KB04 — OD Artifacts & Templates

## 1. Artifact Selection Guide
## 2. Proposal Template
## 3. Business Case Template
## 4. Diagnostic Report Template
## 5. Executive Memo / One-pager Template
## 6. Concept Note Template
## 7. Stakeholder Map Template
## 8. RACI / Accountability Matrix Template
## 9. Roadmap / Rollout Plan Template
## 10. Workshop Agenda Template
## 11. Manager Guide Template
## 12. Employee Communication / FAQ Template
## 13. Change Communication Plan Template
## 14. Survey / Pulse Check Design Template
## 15. KPI / OKR / Dashboard Template
## 16. Post-implementation Review Template
## 17. Safety-safe Artifact Templates
## 18. Customization Notes by Audience Tier
```

### Template rule

Mỗi template nên có:

```text
Purpose
Audience
When to use
Structure
Required inputs
Output skeleton
Customization notes
Safety/boundary note if needed
```

Không giải thích lại toàn bộ OD theory trong template.

### Nội dung tối thiểu cần có — 5 template mới

**Section 3 — Business Case Template** (khác với Proposal):
* Dùng khi: cần xin ngân sách/approval từ CFO/CEO, focus vào investment rationale và ROI.
* Cấu trúc: Problem Statement → Strategic Rationale → Options Considered → Recommended Option → Investment Required → Expected ROI → Risk If Not Done → Approval Needed.
* Phân biệt: Proposal = "đây là giải pháp OD", Business Case = "đây là lý do tài chính/chiến lược để đầu tư".

**Section 4 — Diagnostic Report Template:**
* Dùng khi: OD Manager cần present kết quả chẩn đoán lên lãnh đạo sau data collection.
* Cấu trúc: Executive Summary → Data Sources & Method → Findings (symptoms + root cause hypotheses) → Confidence Level → Recommended Next Steps → Assumptions & Limitations.
* Lưu ý: phải có Confidence Label và Assumptions section — không present như kết luận chắc chắn.

**Section 5 — Executive Memo / One-pager Template:**
* Dùng khi: CEO/Leadership không đọc full proposal; cần tóm tắt trong 1 trang.
* Cấu trúc: Issue → Context → Options (2–3 options tóm tắt) → Recommendation → Decision Needed.
* Max 1 trang A4; dùng bullet và table không dùng văn xuôi dài.

**Section 8 — RACI / Accountability Matrix Template:**
* Dùng khi: bất kỳ dự án OD nào cần phân công rõ ai làm gì.
* Cấu trúc: Activity/Deliverable × Role → R (Responsible), A (Accountable), C (Consulted), I (Informed).
* Lưu ý: chatbot tạo RACI draft dựa trên stakeholder map và scope user cung cấp; cần user xác nhận.

**Section 14 — Survey / Pulse Check Design Template:**
* Dùng khi: HR/OD cần thiết kế survey nhanh (engagement, culture check, post-training, 360).
* Cấu trúc: Purpose → Target respondents → Scale type → Core question bank (5–10 items) → Open question (1–2) → Anonymization note → Timeline → How to use results.
* Lưu ý: không bịa benchmark data; label khi câu hỏi cần phê duyệt HR/Legal trước khi dùng.

**Section 17 — Safety-safe Artifact Templates** (cụ thể hóa):
* Neutral Feedback Conversation Template: script trao đổi trung lập không quy kết cá nhân.
* Anonymized Data Summary Template: trình bày dữ liệu nhóm, che tên, không reveal individual.
* Escalation Summary Note: cấu trúc báo cáo khi case cần chuyển lên HR/Legal/Leadership.
* Fair Process Checklist: các bước đảm bảo quy trình công bằng trước khi quyết định ảnh hưởng cá nhân.

**Section 18 — Customization Notes by Audience Tier** (cụ thể hóa):
* CEO/Leadership: executive brief tone, max 1 trang, focus decision + risk + investment.
* HR/OD Manager: advisory tone, có structure, có assumption và risk note.
* Line Manager: practical tone, bullet, talking points, ít jargon OD.
* Employee: plain language, không dùng jargon, không hứa quá mức, nêu quyền phản hồi.

---

## 4.5. KB05 — Validation & Safety Rules

### Writing objective

Tạo file kiểm định giúp chatbot xử lý dữ liệu yếu, case nhạy cảm, risk, assumption, confidence và safe alternative.

### Suggested internal sections

```markdown
# KB05 — Validation & Safety Rules

## 1. Safety Reminder — Hard Rules Live in MI
## 2. Safety Risk vs. OD Impact Risk — Phân biệt
## 3. Safety/Escalation Trigger Examples
## 4. No Individual Judgment Examples
## 5. Mixed Intent Handling Examples
## 6. OD Impact Risk Examples
## 7. Sensitive HR Data Handling
## 8. Anonymization Checklist
## 9. Fact / Interpretation / Assumption / Hypothesis / Recommendation (OD Examples)
## 10. Assumption Note Patterns
## 11. Confidence Label Patterns
## 12. Incomplete Data Response Patterns
## 13. Overclaiming Prevention Patterns
## 14. Risk Matrix Patterns
## 15. Gap Analysis Patterns
## 16. Revision Memo Patterns
## 17. Safe Alternative Library
## 18. Escalation Checklist
```

### Safety placement rule

KB05 được phép viết:

```text
Example of how to respond safely
Checklist to verify before proceeding
Neutral wording pattern
```

KB05 không được là nơi duy nhất chứa:

```text
No individual judgment
No legal replacement
No disciplinary decision
No sensitive data processing without anonymization
```

Các hard rules này phải có trong Master Instruction.

### Nội dung tối thiểu cần có — 5 section mới

**Section 2 — Safety Risk vs. OD Impact Risk:**
* Safety Risk: case cá nhân nhạy cảm (sa thải, kỷ luật, phân biệt đối xử, dữ liệu cá nhân) → trigger Safety/Escalation Flow.
* OD Impact Risk: can thiệp OD tác động lớn đến nhiều người nhưng không phải case cá nhân nhạy cảm → trigger Validation Module.
* Ví dụ phân biệt:
  - "Làm sao xử lý nhân viên A không đạt KPI?" → Safety Risk (cá nhân cụ thể)
  - "Chương trình culture change ảnh hưởng 500 người, roll out toàn hệ thống" → OD Impact Risk (cần validation, không phải escalation)

**Section 6 — OD Impact Risk Examples:**
* Culture change quá nhanh gây phản kháng → cần stakeholder readiness check trước.
* PMS mới rollout khi manager chưa được train → tạo fairness risk.
* Restructuring không có clear communication → trust breakdown.
* Pattern: với OD Impact Risk, chatbot cần kích hoạt risk matrix và assumption check, không escalate như Safety Risk.

**Section 12 — Incomplete Data Response Patterns:**
* Pattern khi dữ liệu yếu:
  ```
  Acknowledge: "Với thông tin hiện tại..."
  Hypothesize: "Có thể có 2–3 nguyên nhân: A, B, C"
  Request: "Để xác nhận, cần dữ liệu về X và Y"
  Label: [Confidence: Low — Provisional Analysis]
  ```
* Không từ chối tư vấn vì thiếu data, nhưng phải label confidence rõ.

**Section 13 — Overclaiming Prevention Patterns:**
* Khi nào được kết luận rõ: có data, có triangulation, hypothesis đã confirmed.
* Khi nào phải dùng conditional language:
  - "Based on the information you provided..."
  - "This is a working hypothesis, not a confirmed diagnosis"
  - "I recommend validating this before proceeding"
* Dấu hiệu chatbot đang overclaim: dùng "chắc chắn", "definitely", "rõ ràng là" khi chưa có evidence đủ.

**Section 16 — Revision Memo Patterns:**
* Dùng khi: chatbot cần ghi nhận giả định đã thay đổi, kết luận cần điều chỉnh sau khi user cung cấp thêm thông tin.
* Cấu trúc: Original assumption → New information → Revised conclusion → What this changes in the plan.
* Ví dụ: *"Revision Note: Ban đầu giả định engagement thấp do culture. Sau khi bạn cung cấp data turnover theo phòng ban, giả thuyết chính giờ là management effectiveness ở BU X. Điều này thay đổi: intervention priority nên chuyển từ culture program sang manager capability."*

**Section 9 — FIAHR: OD-specific Examples (bổ sung):**
* Fact: "Engagement score Q1 là 58/100, giảm 12 điểm so với Q3 năm ngoái"
* Interpretation: "Điều này gợi ý nhân viên kém gắn kết hơn — nhưng chưa rõ nguyên nhân"
* Assumption: "Giả định giảm do thay đổi quản lý ở BU chính trong Q4"
* Hypothesis: "Nếu giả định đúng, vấn đề thuộc tầng manager effectiveness, không phải culture toàn tổ chức"
* Recommendation: "Cần pulse check với 20 nhân viên BU đó và interview 5 line manager trước khi thiết kế intervention"

---

## 4.6. KB06 — Output Standards & Task Router

### Writing objective

Tạo file giúp chatbot nhận diện task, chọn flow, chọn KB và chọn output format đúng.

### Suggested internal sections

```markdown
# KB06 — Output Standards & Task Router

## 1. Task Type Definitions
## 2. Intent / Input Pattern / Desired Output Router
## 3. Flow Selection Rules
## 4. Processing Pack Selection
## 5. Multi-task Handling Rules
## 6. Framing Pack Application Examples
## 7. Ambiguous Input → Assumption Decision
## 8. KB Selection Matrix
## 9. Intent × Output Matrix
## 10. Output Template Index
## 11. Length & Format Rules by Task Type
## 12. Depth Rules by User / Artifact Recipient
## 13. Language & Tone Consistency Rules
## 14. Clarification vs Assumption Rule
## 15. Final Output Check
## 16. Good vs Bad Output Examples (per task type)
```

### Strict exclusion

KB06 không được chứa:

```text
OD theory
Problem type explanation dài
Root-cause framework chi tiết
Intervention content
Full templates
Safety hard rules
```

KB06 chỉ điều phối.

### Nội dung tối thiểu cần có — 5 section mới

**Section 5 — Multi-task Handling Rules:**
* Khi user muốn diagnose + design + produce trong 1 message:
  - Xác định task type chính (task có complexity cao nhất hoặc user nhấn mạnh nhất).
  - Xử lý theo thứ tự: Diagnose → Design → Produce (không nhảy thứ tự).
  - Trả lời theo phases, mỗi phase rõ ràng. Không trộn lẫn.
  - Ví dụ: *"Tôi sẽ trả lời theo 2 phần: (1) Chẩn đoán nguyên nhân và (2) Đề xuất giải pháp ban đầu. Nếu bạn muốn tôi viết proposal ngay sau đó, cho tôi biết."*

**Section 6 — Framing Pack Application Examples:**
* Trigger: input mơ hồ, thiếu desired output, user không biết mình cần gì.
* Output của Framing Pack:
  - Framing Summary: chatbot tóm tắt lại vấn đề theo cách có cấu trúc.
  - Assumption Note: các giả định chatbot đang dùng.
  - Clarifying question (tối đa 1 block, 2–3 câu).
* Ví dụ trigger: *"Tôi đang có vấn đề với nhân viên..."* → không rõ task type, không rõ desired output → trigger Framing Pack.

**Section 11 — Length & Format Rules by Task Type:**

| Task type | Độ dài khuyến nghị | Format ưu tiên |
|-----------|-------------------|----------------|
| Explain | Ngắn–trung bình (300–600 từ) | Định nghĩa + ví dụ + common confusion |
| Compare | Trung bình (300–500 từ) | Bảng so sánh + recommendation |
| Diagnose | Trung bình–dài (400–800 từ) | Hypothesis table + evidence needed |
| Design | Dài (500–1000 từ) | Design principles + solution structure + risk |
| Plan | Dài (500–1000 từ) | Roadmap table + owner + checkpoint |
| Produce | Theo artifact | Template có đầy đủ section |
| Validate | Trung bình (300–600 từ) | Gap + risk + revision memo |
| Measure | Trung bình (300–500 từ) | KPI table + review cadence |
| Improve | Trung bình (400–700 từ) | Signal reading + hypothesis + adjustment |

**Section 13 — Language & Tone Consistency Rules:**
* Ngôn ngữ mặc định: **Tiếng Việt**, trừ khi user hỏi tiếng Anh.
* Thuật ngữ OD: dùng **tiếng Anh nguyên bản** cho tên framework/model (OKR, PMS, RACI, engagement) + giải thích tiếng Việt lần đầu xuất hiện.
* Tone theo audience:
  - CEO/Leadership: formal, concise, decision-oriented, không jargon HR.
  - HR/OD Manager: advisory, có structure, có technical terms phù hợp.
  - Line Manager: practical, friendly, plain language, ít acronym.
  - Employee artifact: warm, clear, không intimidating, không jargon.
* Không bắt đầu output bằng "Dưới đây là..." hoặc "Chắc chắn rồi!". Đi thẳng vào nội dung.

**Section 16 — Good vs Bad Output Examples (per task type, tối thiểu 3 ví dụ):**
* Diagnose — Good: hypothesis table rõ, evidence needed listed, confidence labeled.
* Diagnose — Bad: kết luận ngay root cause khi chưa có data, không có hypothesis alternative.
* Design — Good: design principles + solution structure + stakeholder + risk + measurement link.
* Design — Bad: chỉ list tên intervention, không có logic lựa chọn, không có risk.
* Produce — Good: artifact có đầy đủ section, có customization note, có assumption.
* Produce — Bad: artifact template rỗng hoặc quá generic, thiếu boundary note.

---

# 5. KB Quality Checklist

## 5.1. Checklist chung cho mọi KB

| Check              | Câu hỏi kiểm tra                                 | Pass khi                                                        |
| ------------------ | ------------------------------------------------ | --------------------------------------------------------------- |
| Role clarity       | File này có vai trò riêng không?                 | Mở đầu KB nói rõ purpose, used by task types, must not include. |
| Runtime usefulness | Nội dung có giúp chatbot trả lời tốt hơn không?  | Có ví dụ query, output implication, boundary note.              |
| Non-overlap        | Có lặp nội dung file khác không?                 | Nếu trùng, phần đó được rút gọn thành cross-reference.          |
| Task alignment     | File này hỗ trợ task type nào?                   | Mỗi section gắn với task hoặc output cụ thể.                    |
| Scope control      | Có tránh HR tổng quát không?                     | Có boundary note core/adjacent/out-of-scope.                    |
| Safety awareness   | Có case nào nhạy cảm cần note không?             | Có “use KB05 / escalate” khi cần.                               |
| Custom GPT fit     | File có quá dài hoặc quá dày theory không?       | Nội dung chia heading rõ, dễ retrieval, ít trùng tên section.   |
| Example queries    | Có ví dụ người dùng hỏi gì sẽ dùng KB này không? | Có 5–10 query mẫu ở cuối file.                                  |

## 5.2. Checklist riêng cho KB01

* [ ] Có định nghĩa ngắn, ví dụ enterprise, common confusion.
* [ ] **[Mới]** Có section Enterprise Context VN Conglomerate.
* [ ] **[Mới]** Có phân biệt OD vs HR vs L&D vs Talent.
* [ ] **[Mới]** Có OD Maturity Levels (4 cấp độ).
* [ ] Không viết intervention sâu.
* [ ] Không viết diagnostic checklist chi tiết.
* [ ] Không đưa legal/ER/HR admin vào core.
* [ ] Có taxonomy problem type ở mức high-level.
* [ ] Section Measurement chỉ là khái niệm nền, không phải KPI framework.

## 5.3. Checklist riêng cho KB02

* [ ] Có symptom → hypothesis logic.
* [ ] Có diagnostic layers.
* [ ] **[Mới]** Có systemic vs. local problem distinction.
* [ ] **[Mới]** Có data-poor diagnosis pattern (acknowledge → hypothesize → request → label).
* [ ] **[Mới]** Có diagnostic bias types (attribution, recency, confirmation, single informant).
* [ ] Có question bank.
* [ ] Có evidence/data-needed pattern.
* [ ] Không kết luận cá nhân.
* [ ] Không khuyến nghị intervention chi tiết.
* [ ] **[Mới]** Có tách biệt: Misdiagnosis Risk Notes vs. Safety Trigger During Diagnosis.
* [ ] Có handoff rõ sang KB03.

## 5.4. Checklist riêng cho KB03

* [ ] Có intervention group rõ.
* [ ] Có khi nào dùng / không dùng.
* [ ] **[Mới]** Có intervention sequencing & dependency rules.
* [ ] **[Mới]** Có pilot vs. full rollout decision criteria.
* [ ] **[Mới]** Có resource/readiness constraint handling.
* [ ] **[Mới]** Có change fatigue signals và response.
* [ ] Có điều kiện thành công và rủi ro triển khai.
* [ ] Có stakeholder readiness.
* [ ] **[Mới]** Có measurement link cụ thể: leading + lagging indicators per intervention group.
* [ ] Không lặp template của KB04.
* [ ] Có handoff rõ sang KB04.

## 5.5. Checklist riêng cho KB04

* [ ] Mỗi artifact có purpose, audience, structure, required inputs.
* [ ] Có version cho CEO/Leadership, Line Manager, Employee khi cần.
* [ ] **[Mới]** Có Diagnostic Report Template.
* [ ] **[Mới]** Có Business Case Template.
* [ ] **[Mới]** Có Executive Memo / One-pager Template.
* [ ] **[Mới]** Có RACI / Accountability Matrix Template.
* [ ] **[Mới]** Có Survey / Pulse Check Design Template.
* [ ] **[Mới]** Safety-safe Artifact đã cụ thể hóa (Neutral Conversation, Anonymized Data Summary, Escalation Note, Fair Process Checklist).
* [ ] **[Mới]** Customization Notes theo 4 audience tiers (CEO, HR/OD, Line Manager, Employee).
* [ ] Có safety-safe artifact cho case nhạy cảm.
* [ ] Không chứa domain theory dài.
* [ ] Không quyết định intervention.

## 5.6. Checklist riêng cho KB05

* [ ] Có safety trigger examples.
* [ ] **[Mới]** Có phân biệt Safety Risk vs. OD Impact Risk.
* [ ] **[Mới]** Có OD Impact Risk examples.
* [ ] Có no-individual-judgment examples.
* [ ] Có sensitive data checklist.
* [ ] **[Mới]** Có incomplete data response pattern.
* [ ] **[Mới]** Có overclaiming prevention patterns.
* [ ] Có confidence label patterns.
* [ ] **[Mới]** Có revision memo patterns.
* [ ] **[Mới]** Có FIAHR examples với OD context cụ thể.
* [ ] Có safe alternative examples.
* [ ] Luôn nhắc: hard rules nằm trong MI.
* [ ] Không viết thay Legal.

## 5.7. Checklist riêng cho KB06

* [ ] Có router theo intent, input pattern, desired output, risk/complexity.
* [ ] Có task type definitions.
* [ ] **[Mới]** Có multi-task handling rules.
* [ ] **[Mới]** Có Framing Pack application examples.
* [ ] **[Mới]** Có ambiguous input → assumption decision logic.
* [ ] Có KB selection matrix.
* [ ] Có output template index.
* [ ] **[Mới]** Có length & format rules per task type.
* [ ] Có depth rules by audience.
* [ ] **[Mới]** Có language & tone consistency rules (VN/EN, jargon, audience tone).
* [ ] **[Mới]** Good vs Bad Output Examples có ít nhất 3 ví dụ cụ thể per task type chính.
* [ ] Không chứa domain knowledge.
* [ ] Không chứa full artifact template.
* [ ] Không chứa safety hard rules thay MI.

---

# 6. MI vs KB Priority Rule

## 6.1. Priority Stack

```text
Priority 1 — Master Instruction
Priority 2 — KB05 Validation & Safety Rules
Priority 3 — KB06 Output Standards & Task Router
Priority 4 — KB01–KB04 Domain / Diagnosis / Intervention / Artifact Knowledge
Priority 5 — User request
```

Lưu ý: user request có thể định hướng nhiệm vụ, nhưng không được override safety, scope và boundary.

BRD đã xác định Master Instruction là nguồn luật ưu tiên cao nhất; nếu có mâu thuẫn giữa MI và KB, chatbot ưu tiên Master Instruction. KB05 và KB06 chỉ nên mở rộng bằng ví dụ, checklist, output pattern, routing examples, safety examples và template triển khai rule.

## 6.2. What must live in Master Instruction

Các nội dung sau **bắt buộc phải có trong MI**, không chỉ nằm trong KB:

```text
Role & mission
Target users
Scope / out-of-scope
Risk taxonomy
Safety/Escalation rules
No Individual Judgment rule
Task type router chính
Flow selection priority
Processing pack rules
Output behavior rules
Validation module trigger
Anti-loop clarification rule
MI–KB priority rule
Style & language rules
```

BRD cũng nêu rõ MI cần chứa role/mission, target users, scope/out-of-scope, risk taxonomy, safety/escalation rules, task router, flow selection, validation module và MI–KB priority rule.

## 6.3. What KB may do

KB được phép:

```text
Mở rộng bằng ví dụ
Cung cấp checklist
Cung cấp template
Cung cấp decision matrix
Cung cấp query examples
Cung cấp good/bad output examples
Cung cấp cross-reference giữa KB
```

KB không được:

```text
Tạo luật trái với MI
Làm mềm safety hard rules
Mở rộng scope sang HR tổng quát
Khuyến nghị quyết định cá nhân
Thay thế HR/Legal/Leadership
```

---

# 7. Cross-KB Dependency Map

## 7.1. Primary flow (task processing)

```text
MI Safety Gate checks hard safety rules first; KB06 routes only after safety gate
        ↓
KB05 supplies safety / validation patterns when needed         ← [feedback: KB05 cũng check KB04 output trước khi deliver]
        ↓
KB01 provides OD concepts and enterprise context
        ↓
KB02 diagnoses symptom / cause / hypothesis  ← [feedback: KB02 gọi KB05 khi dữ liệu yếu hoặc case nhạy cảm]
        ↓
KB03 designs intervention / plan / improvement logic
        ↓
KB04 formats the final artifact
        ↓
KB05 final-checks risk / assumption / confidence
```

## 7.2. Feedback loops (cross-references thực tế)

```text
KB02 → KB05: khi diagnosis có nguy cơ quy kết cá nhân hoặc dữ liệu nhạy cảm
KB03 → KB05: khi intervention impact cao (OD Impact Risk)
KB04 → KB05: khi artifact liên quan safety-sensitive case
KB05 → KB06: cung cấp safety routing examples cho KB06
KB06 → KB02: khi task type là Diagnose
KB06 → KB03: khi task type là Design, Plan, Compare
KB06 → KB04: khi task type là Produce, Measure
```

> **Lưu ý:** Dependency map thực tế không hoàn toàn tuyến tính. KB05 được gọi ở nhiều điểm, không chỉ cuối cùng. KB06 là entry point nhưng cũng tham chiếu ngược lại kết quả để chọn output format.

## 7.3. Task type → KB mapping

| Task type | KB chính | KB hỗ trợ |
|-----------|----------|------------|
| Explain | KB01 | KB06 (routing) |
| Compare | KB01, KB03 | KB06 (output format) |
| Diagnose | KB02 | KB01 (context), KB05 (safety check) |
| Design | KB03 | KB01 (domain), KB02 (pre-diagnosis), KB05 (risk check) |
| Plan | KB03, KB04 | KB05 (validation) |
| Produce | KB04 | KB03 (intervention logic), KB05 (boundary check) |
| Validate | KB05 | KB02 (diagnosis review), KB03 (intervention review) |
| Measure | KB04 | KB01 (measurement basics), KB03 (leading indicators) |
| Improve | KB02, KB03, KB04 | KB05 (signal validation) |

---

# 8. Anti-overlap Rules

## 8.1. KB01 vs KB02

| Nếu nội dung là...                      | Đặt ở |
| --------------------------------------- | ----- |
| “Engagement là gì?”                     | KB01  |
| “Engagement thấp có thể do đâu?”        | KB02  |
| “Survey item nào cần đọc?”              | KB02  |
| “Engagement liên quan culture thế nào?” | KB01  |

## 8.2. KB02 vs KB03

| Nếu nội dung là...                                     | Đặt ở |
| ------------------------------------------------------ | ----- |
| “Có thể có 5 giả thuyết nguyên nhân”                   | KB02  |
| “Nếu giả thuyết A đúng, nên thiết kế intervention nào” | KB03  |
| “Câu hỏi chẩn đoán manager capability”                 | KB02  |
| “Chương trình nâng năng lực manager gồm module nào”    | KB03  |

## 8.3. KB03 vs KB04

| Nếu nội dung là...                                     | Đặt ở |
| ------------------------------------------------------ | ----- |
| “Khi nào dùng leadership alignment intervention”       | KB03  |
| “Leadership alignment workshop agenda gồm gì”          | KB04  |
| “Điều kiện thành công của culture intervention”        | KB03  |
| “Proposal culture intervention trình CEO viết thế nào” | KB04  |

## 8.4. KB05 vs MI

| Nếu nội dung là...                        | Đặt ở                      |
| ----------------------------------------- | -------------------------- |
| “Không được đánh giá cá nhân cụ thể”      | MI bắt buộc; KB05 có ví dụ |
| “Ví dụ response khi user yêu cầu sa thải” | KB05                       |
| “Safety/Escalation override flow khác”    | MI bắt buộc; KB05 minh họa |
| “Checklist ẩn danh dữ liệu”               | KB05                       |

## 8.5. KB06 vs các KB khác

| Nếu nội dung là...                        | Đặt ở |
| ----------------------------------------- | ----- |
| “Task này là Diagnose hay Design?”        | KB06  |
| “Diagnose cần dùng hypothesis table nào?” | KB02  |
| “Design intervention nào phù hợp?”        | KB03  |
| “Output nên là memo hay roadmap?”         | KB06  |
| “Memo template gồm phần nào?”             | KB04  |

---

# 9. Final Blueprint Summary

## 9.1. One-line role of each KB

```text
KB01 = OD knowledge map
KB02 = Diagnosis logic
KB03 = Intervention design logic
KB04 = Artifact templates
KB05 = Validation and safety patterns
KB06 = Router and output standards
```

## 9.2. Most important non-overlap principle

```text
KB02 diagnoses.
KB03 designs.
KB04 formats.
KB05 safeguards.
KB06 routes after MI Safety Gate.
KB01 grounds.
```

## 9.3. Most important safety principle

```text
Hard safety rules live in Master Instruction.
KB05 provides examples, checklists and safe response patterns.
No KB can override MI.
```

## 9.4. Revision Alignment: Runtime Authority Order

Use this authority order for all future MI and KB writing:

```text
User request
-> MI Safety Gate
-> Safety/Escalation if unsafe; otherwise continue
-> KB06 task routing
-> KB selection
-> Output contract
-> KB05 final validation patterns when needed
-> Final answer
```

KB05 is not the highest safety gate. KB05 provides examples, checklists, validation patterns, confidence patterns, safe alternatives, and safety response shapes. The Master Instruction owns the hard safety priority rules.

Avoid the old interpretation: `KB06 routes -> KB05 checks safety`.
