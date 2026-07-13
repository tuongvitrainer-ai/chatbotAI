# HR/OD Advisor — Node Prioritization Table v1.0

## 1. Prioritization Criteria

### Scoring rule

Mỗi node được chấm theo thang **1–5** cho từng tiêu chí.

| Score | Ý nghĩa                                                  |
| ----: | -------------------------------------------------------- |
|     1 | Ít liên quan / chỉ cần nhắc nhẹ                          |
|     2 | Có liên quan nhưng không cần viết sâu ngay               |
|     3 | Quan trọng ở mức hỗ trợ                                  |
|     4 | Quan trọng, nên viết khá kỹ                              |
|     5 | Rất quan trọng, nếu thiếu sẽ làm chatbot yếu hoặc rủi ro |

### Criteria

| Criteria                              | Câu hỏi chấm điểm                                                                                       |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **1. Relevance to chatbot core task** | Node này có trực tiếp phục vụ Explain, Diagnose, Design, Plan, Produce, Measure, Improve không?         |
| **2. User impact**                    | Node này có giúp HR Manager, OD Manager, HRBP, OD Project Owner xử lý việc thực tế không?               |
| **3. Risk if shallow**                | Nếu viết nông, chatbot có dễ chẩn đoán sai, khuyến nghị sai, hoặc output vô dụng không?                 |
| **4. Dependency value**               | Node này có phải nền cho các node khác không?                                                           |
| **5. KB reuse potential**             | Node này có được dùng lặp lại trong nhiều KB/task/artifact không?                                       |
| **6. Boundary / safety importance**   | Node này có giúp tránh legal risk, individual judgment, privacy risk, overclaim hoặc scope drift không? |

### Priority rule

| Priority |                     Điểm tổng | Cách hiểu                           |
| -------- | ----------------------------: | ----------------------------------- |
| **P1**   | 27–30 hoặc strategic-critical | Cần viết sâu ngay                   |
| **P2**   |                         22–26 | Viết sau khi P1 ổn                  |
| **P3**   |                           ≤21 | Chỉ cần coverage nhẹ hoặc phase sau |

Lưu ý: Dù nhiều node điểm cao, **P1 bị giới hạn tối đa 8 node** để tránh ưu tiên quá rộng. Exploration Map cũng đã khuyến nghị ưu tiên các cụm Diagnosis, Problem Type, Intervention, Measurement và Artifact Schema vì ảnh hưởng trực tiếp nhất đến KB02–KB04.

---

## 2. Node Prioritization Table

| Node                                                      | Domain group         | Relevance score | User impact score | Risk if shallow score | Dependency score | Reuse potential score | Boundary / safety score | Total score | Priority | Recommended KB placement  | Reasoning note                                                                                                                                                                                                    |
| --------------------------------------------------------- | -------------------- | --------------: | ----------------: | --------------------: | ---------------: | --------------------: | ----------------------: | ----------: | -------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. OD Advisory Logic & Problem Framing**                | Core                 |               5 |                 5 |                     5 |                5 |                     4 |                       5 |      **29** | **P1**   | KB01 + KB02 + KB04        | Cần viết sâu vì chatbot phải chuyển câu hỏi mơ hồ thành framing, assumption, hypothesis và next step. Nếu thiếu, chatbot sẽ nhảy thẳng sang advice.                                                               |
| **2. Organization Diagnosis & Evidence Logic**            | Core                 |               5 |                 5 |                     5 |                5 |                     5 |                       5 |      **30** | **P1**   | KB02                      | Đây là xương sống của HR/OD Advisor. Synthesis xác định bài toán chính là chuyển từ câu hỏi mơ hồ sang framing, diagnostic hypotheses, OD solution, plan, artifact, risk, measurement và improvement.             |
| **3. Diagnostic Layers & Root-cause Patterns**            | Core                 |               5 |                 5 |                     5 |                5 |                     5 |                       5 |      **30** | **P1**   | KB02 + KB03 + KB04        | Cần viết sâu vì giúp phân biệt individual, team, manager, process, structure, culture, leadership, system. Nếu viết nông sẽ dễ quy kết cá nhân hoặc chọn intervention sai.                                        |
| **4. Problem Type Map + Symptom Library**                 | Core                 |               5 |                 5 |                     5 |                5 |                     5 |                       5 |      **30** | **P1**   | KB01 + KB02               | P1 vì đây là bộ phân loại Culture, Performance, Competency, Org Design, Change, Engagement, Leadership. Exploration Map xác định nếu thiếu symptom library thì KB02 sẽ chẩn đoán chung chung.                     |
| **5. Intervention Fit Matrix + Intervention Groups**      | Core                 |               5 |                 5 |                     5 |                5 |                     5 |                       4 |      **29** | **P1**   | KB03                      | P1 vì nối từ root cause sang intervention. Nếu viết nông, KB03 sẽ chọn can thiệp sai tầng hoặc “training hóa” mọi vấn đề.                                                                                         |
| **6. Measurement & Improvement Logic**                    | Core                 |               5 |                 5 |                     5 |                4 |                     5 |                       5 |      **29** | **P1**   | KB01 + KB03 + KB04        | P1 vì mọi intervention cần feedback loop. Measurement Library cũng quy định không dùng một metric duy nhất, không đo activity thay outcome, không dùng dữ liệu cá nhân chưa ẩn danh và không overclaim causality. |
| **7. Artifact Schema & Output Families**                  | Core                 |               5 |                 5 |                     5 |                4 |                     5 |                       5 |      **29** | **P1**   | KB04                      | P1 vì Produce là task trọng yếu. Nếu thiếu artifact schema, chatbot trả lời dài nhưng không tạo memo, roadmap, checklist, dashboard, FAQ dùng được.                                                               |
| **8. Boundary / Safety / No Individual Judgment Pattern** | Core / Near boundary |               5 |                 5 |                     5 |                5 |                     5 |                       5 |      **30** | **P1**   | KB04 + KB05 later         | P1 vì phải nhúng vào KB01–KB04 ngay, dù KB05 viết sau. Near Matrix xác định legal/compliance chỉ dùng làm boundary/risk check, không tư vấn luật hoặc viết văn bản xử lý cá nhân.                                 |
| **9. OD Foundations & Enterprise Context**                | Core                 |               4 |                 4 |                     3 |                5 |                     4 |                       3 |      **23** | **P2**   | KB01                      | Cần viết nhưng không nên quá sâu. Vai trò chính là nền khái niệm cho Explain/Compare và enterprise context.                                                                                                       |
| **10. Organization Design / Role / Operating Model**      | Core                 |               5 |                 5 |                     4 |                4 |                     4 |                       4 |      **26** | **P2**   | KB01 + KB02 + KB03 + KB04 | Rất quan trọng cho role clarity, decision rights, governance, silo. P2 vì nên viết sau khi Diagnostic Layer và Intervention Fit đã rõ.                                                                            |
| **11. Culture System & Trust**                            | Core                 |               5 |                 5 |                     4 |                4 |                     4 |                       5 |      **27** | **P2**   | KB01 + KB02 + KB03 + KB04 | Điểm cao nhưng không đưa P1 vì P1 đã giới hạn. Node này cần viết khá sâu, đặc biệt tránh slogan hóa văn hóa và tránh kết luận cá nhân.                                                                            |
| **12. Engagement Drivers & Employee Voice**               | Core / Near          |               5 |                 5 |                     4 |                4 |                     4 |                       5 |      **27** | **P2**   | KB01 + KB02 + KB03 + KB04 | Cần viết sau Problem Type Map để tránh nhầm engagement thấp với “nhân viên thiếu động lực”. Employee voice phải có closed-loop feedback và boundary với grievance/investigation.                                  |
| **13. Performance Management & Goal Alignment**           | Core                 |               5 |                 5 |                     5 |                4 |                     4 |                       5 |      **28** | **P2**   | KB01 + KB02 + KB03 + KB04 | Điểm cao nhưng xếp P2 để tránh P1 quá nhiều. Cần boundary mạnh: không rating, kỷ luật, PIP cá nhân; chỉ xử lý hệ thống mục tiêu/review/fairness.                                                                  |
| **14. Capability Architecture & L&D Interface**           | Core / Near          |               5 |                 5 |                     4 |                4 |                     4 |                       4 |      **26** | **P2**   | KB01 + KB02 + KB03 + KB04 | Cần viết sau Intervention Fit vì dễ bị biến thành L&D/course design. Trọng tâm là role-based capability, learning transfer, manager reinforcement.                                                                |
| **15. Leadership / Manager / Middle Management Layer**    | Core                 |               5 |                 5 |                     4 |                4 |                     5 |                       5 |      **28** | **P2**   | KB01 + KB02 + KB03 + KB04 | Điểm cao nhưng P2 vì cần dựa trên Diagnostic Layers và Boundary Pattern. Nếu viết nông dễ quy kết “manager yếu”.                                                                                                  |
| **16. Change Readiness & Change Enablement**              | Core / Near          |               5 |                 5 |                     4 |                4 |                     5 |                       4 |      **27** | **P2**   | KB01 + KB02 + KB03 + KB04 | Cần viết sâu sau P1 vì liên quan adoption, readiness, resistance, sponsor alignment. Không mở thành change consultant tổng quát.                                                                                  |
| **17. Stakeholder Engagement Logic**                      | Core                 |               5 |                 5 |                     4 |                5 |                     5 |                       4 |      **28** | **P2**   | KB03 + KB04               | Điểm cao nhưng không xếp P1 vì là dependency hỗ trợ intervention/artifact. Cần viết khá sớm sau Intervention Fit.                                                                                                 |
| **18. OD Risk & Impact Logic**                            | Core / Near boundary |               4 |                 4 |                     4 |                4 |                     5 |                       5 |      **26** | **P2**   | KB03 + KB04               | Dùng để gắn risk matrix, mitigation, confidence label. Nên viết sau Boundary Pattern để không trùng KB05.                                                                                                         |
| **19. HR Policy Interface**                               | Near                 |               3 |                 4 |                     4 |                3 |                     3 |                       5 |      **22** | **P2**   | KB03 + KB04               | Chỉ dùng khi intervention chạm policy. Không viết/chỉnh policy thay HR owner.                                                                                                                                     |
| **20. L&D Interface / Learning Transfer**                 | Near                 |               4 |                 4 |                     4 |                3 |                     4 |                       3 |      **22** | **P2**   | KB03 + KB04               | Cần vì capability intervention thường cần enablement. Nhưng không mở thành course design hoặc LMS.                                                                                                                |
| **21. HR Analytics / Workforce Analytics Interface**      | Near                 |               4 |                 4 |                     4 |                3 |                     4 |                       5 |      **24** | **P2**   | KB02 + KB04               | Nên viết như interface đọc tín hiệu và measurement. Không làm data science/BI.                                                                                                                                    |
| **22. Legal / Compliance Boundary**                       | Near                 |               3 |                 5 |                     5 |                4 |                     4 |                       5 |      **26** | **P2**   | KB04 + KB05 later         | Quan trọng về safety nhưng không viết sâu như legal KB. Chỉ viết escalation trigger, HR/Legal review questions, safe alternative.                                                                                 |
| **23. DEI / Fairness Interface**                          | Near                 |               4 |                 4 |                     4 |                3 |                     4 |                       5 |      **24** | **P2**   | KB02 + KB03 + KB04        | Cần vì Facet Matrix chỉ ra Ethical/Fairness là gap lớn. Chỉ dùng fairness lens, không điều tra/kết luận cáo buộc.                                                                                                 |
| **24. Internal Communication / Change Communication**     | Near                 |               4 |                 4 |                     3 |                3 |                     4 |                       4 |      **22** | **P2**   | KB03 + KB04               | Cần cho employee FAQ, manager cascade, change communication. Không biến thành PR/content bot.                                                                                                                     |
| **25. Project Management / Rollout Planning Interface**   | Near                 |               4 |                 4 |                     3 |                3 |                     4 |                       3 |      **21** | **P3**   | KB03 + KB04               | Cần coverage nhẹ: phase, owner, checkpoint, dependency. Không viết PMO methodology.                                                                                                                               |
| **26. Business Strategy Alignment Interface**             | Near                 |               4 |                 4 |                     3 |                3 |                     4 |                       3 |      **21** | **P3**   | KB01 + KB03 + KB04        | Chỉ dùng strategy làm context để align OD, không tư vấn business strategy tổng thể.                                                                                                                               |
| **27. Talent Management Interface**                       | Near                 |               3 |                 3 |                     3 |                2 |                     3 |                       4 |      **18** | **P3**   | KB01 + KB03               | Chỉ coverage nhẹ khi capability, role readiness, career/succession liên quan OD. Không mở talent suite.                                                                                                           |
| **28. Employee Experience Touchpoints**                   | Near                 |               3 |                 4 |                     3 |                3 |                     3 |                       4 |      **20** | **P3**   | KB01 + KB02 + KB04        | Dùng như source signal cho culture/engagement/change. Không mở thành EX service design.                                                                                                                           |
| **29. Organizational Psychology Reference**               | Extended             |               3 |                 3 |                     3 |                2 |                     3 |                       5 |      **19** | **P3**   | KB01 + KB02 reference     | Chỉ dùng như lens cấp nhóm/hệ thống: trust, team climate, psychological safety. Không chẩn đoán tâm lý cá nhân.                                                                                                   |
| **30. Group Dynamics / Team Effectiveness Reference**     | Extended             |               3 |                 3 |                     3 |                2 |                     3 |                       4 |      **18** | **P3**   | KB02 + KB03 reference     | Có ích cho collaboration/team trust nhưng không viết thành team coaching KB.                                                                                                                                      |
| **31. HRIS / Data Source Literacy**                       | Extended             |               2 |                 3 |                     3 |                2 |                     3 |                       4 |      **17** | **P3**   | KB04 reference            | Chỉ đủ để hiểu data source field trong measurement artifact. Không triển khai HRIS/BI.                                                                                                                            |
| **32. Conflict Handling Reference**                       | Extended             |               2 |                 3 |                     3 |                2 |                     3 |                       5 |      **18** | **P3**   | KB03 + KB04 reference     | Chỉ dùng trong manager guide ở mức neutral conversation/escalation cue. Không xử lý mediation/ER investigation.                                                                                                   |

---

## 3. Priority Summary

### P1: Cần viết sâu ngay

Chỉ chọn **8 node P1**:

| P1 Node                                                   | Vì sao viết sâu ngay                                                                                | KB placement       |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ------------------ |
| **1. OD Advisory Logic & Problem Framing**                | Giữ chatbot không nhảy thẳng sang advice; tạo logic framing/assumption/confidence.                  | KB01 + KB02 + KB04 |
| **2. Organization Diagnosis & Evidence Logic**            | Xương sống của Diagnose/Improve; quyết định chất lượng phân tích.                                   | KB02               |
| **3. Diagnostic Layers & Root-cause Patterns**            | Tránh quy kết cá nhân; nối symptom với root-cause layer.                                            | KB02 + KB03        |
| **4. Problem Type Map + Symptom Library**                 | Giúp chatbot nhận diện đúng Culture/Performance/Capability/Org Design/Change/Engagement/Leadership. | KB01 + KB02        |
| **5. Intervention Fit Matrix + Intervention Groups**      | Cầu nối từ diagnosis sang solution; tránh intervention sai tầng.                                    | KB03               |
| **6. Measurement & Improvement Logic**                    | Đảm bảo mọi intervention có metric, review cadence, learning loop.                                  | KB01 + KB03 + KB04 |
| **7. Artifact Schema & Output Families**                  | Giúp chatbot tạo output dùng được: memo, roadmap, checklist, dashboard, FAQ.                        | KB04               |
| **8. Boundary / Safety / No Individual Judgment Pattern** | Bảo vệ KB01–KB04 khỏi legal, privacy, individual judgment, scope drift.                             | KB04 + KB05 later  |

**Ghi chú:** P1 không có nghĩa là chỉ viết 8 file. P1 là 8 node phải được viết sâu trước, rồi phân bổ vào KB01–KB04.

---

### P2: Viết sau khi P1 ổn

P2 gồm các domain core/near quan trọng nhưng nên viết sau khi đã có xương sống chẩn đoán–can thiệp–artifact:

| P2 Node                                                           | Cách viết                                                                 |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------- |
| OD Foundations & Enterprise Context                               | Viết vừa đủ, tránh lý thuyết hóa.                                         |
| Organization Design / Role / Operating Model                      | Viết sâu vừa, gắn với symptom/intervention/artifact.                      |
| Culture System & Trust                                            | Viết theo behavior, reinforcement, trust/voice, measurement.              |
| Engagement Drivers & Employee Voice                               | Viết theo driver, listening, closed-loop action.                          |
| Performance Management & Goal Alignment                           | Viết cấp hệ thống, không xử lý cá nhân.                                   |
| Capability Architecture & L&D Interface                           | Viết ở mức capability/learning transfer, không thành course design.       |
| Leadership / Manager / Middle Management                          | Viết theo expectation, accountability, workload, enablement.              |
| Change Readiness & Change Enablement                              | Viết theo readiness/adoption, không thành change methodology quá rộng.    |
| Stakeholder Engagement Logic                                      | Viết để hỗ trợ KB03/KB04: sponsor, owner, affected group, decision maker. |
| HR Policy / HR Analytics / Legal / DEI / Communication interfaces | Viết như boundary/interface, không thành KB chuyên ngành.                 |

---

### P3: Coverage nhẹ hoặc phase sau

| P3 Node                               | Cách xử lý                                                              |
| ------------------------------------- | ----------------------------------------------------------------------- |
| Project Management / Rollout Planning | Chỉ dùng phase, owner, milestone, dependency, checkpoint.               |
| Business Strategy Alignment           | Chỉ dùng strategy như context; không tư vấn strategy.                   |
| Talent Management Interface           | Chỉ nối capability với role readiness/career/succession ở mức boundary. |
| Employee Experience Touchpoints       | Chỉ dùng như signal cho engagement/culture/change.                      |
| Organizational Psychology Reference   | Chỉ dùng như lens cấp nhóm/hệ thống.                                    |
| Group Dynamics / Team Effectiveness   | Chỉ dùng nếu cần giải thích team climate/collaboration.                 |
| HRIS / Data Source Literacy           | Chỉ dùng để hiểu data source trong measurement.                         |
| Conflict Handling Reference           | Chỉ dùng trong manager guide ở mức neutral conversation/escalation cue. |

---

## 4. Dependency Notes

### 4.1. Node nào phải hiểu trước node nào?

| Phải hiểu trước                             | Sau đó mới viết tốt                                                       | Lý do                                                                                 |
| ------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **OD Advisory Logic**                       | Diagnostic Logic, Artifact Schema                                         | Nếu không có framing logic, diagnostic report và memo sẽ thiếu assumption/confidence. |
| **Problem Type Map + Symptom Library**      | Diagnostic Question Bank                                                  | Phải biết symptom thuộc nhóm nào trước khi thiết kế câu hỏi.                          |
| **Diagnostic Layers & Root-cause Patterns** | Intervention Fit Matrix                                                   | Phải biết root cause nằm ở layer nào mới chọn intervention đúng.                      |
| **Intervention Fit Matrix**                 | Intervention Playbook, Roadmap, Artifact Schema                           | Nếu chưa biết intervention fit, roadmap/proposal sẽ chỉ là template rỗng.             |
| **Measurement Logic**                       | Dashboard Outline, PIR Template, Improvement Plan                         | Metric phải gắn với problem/intervention, không thể viết dashboard trước.             |
| **Boundary Pattern**                        | Manager Guide, Employee FAQ, Performance Artifact, Legal/Compliance notes | Artifact càng gần manager/employee càng cần boundary.                                 |
| **Stakeholder Engagement Logic**            | Executive Memo, Manager Guide, Employee FAQ, Rollout Plan                 | Audience quyết định depth, wording, risk và required sections.                        |

IA Pack cũng đã tách KB theo vai trò runtime: KB02 dùng cho symptom/root cause/hypothesis, KB03 dùng cho intervention fit, KB04 dùng cho artifact, KB05 dùng cho validation/safety; vì vậy không nên viết artifact hoặc intervention trước khi xong diagnostic core.

---

### 4.2. Node nào dễ gây nhầm lẫn nếu viết riêng lẻ?

| Node                          | Dễ nhầm thành                              | Cách tránh                                                                  |
| ----------------------------- | ------------------------------------------ | --------------------------------------------------------------------------- |
| **Engagement Drivers**        | Employee happiness / wellbeing chung chung | Luôn nối với driver, root-cause layer, data, action owner.                  |
| **Culture System**            | Slogan / values campaign                   | Luôn nối values → behavior → reinforcement → measurement.                   |
| **Capability Architecture**   | L&D course design                          | Luôn kiểm tra role requirement, work application, learning transfer.        |
| **Performance Management**    | Individual performance scoring / PIP       | Chỉ xử lý system, process, fairness, criteria, cadence.                     |
| **Change Enablement**         | Full change management consulting          | Giới hạn ở readiness, adoption, cascade, feedback loop cho OD intervention. |
| **HR Analytics**              | Data science / BI / predictive model       | Chỉ đọc tín hiệu, baseline, trend, caveat, data source.                     |
| **Legal / Compliance**        | Legal advice                               | Chỉ boundary, checklist, escalation, HR/Legal review.                       |
| **Organizational Psychology** | Psychological diagnosis cá nhân            | Chỉ dùng ở cấp nhóm/hệ thống; không suy diễn cá nhân.                       |

---

### 4.3. Node nào cần boundary rule đi kèm?

| Node                                        | Boundary rule bắt buộc                                                                                                                                                                                                |
| ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Performance Management & Goal Alignment** | Không rating/xếp loại/kỷ luật/PIP cá nhân.                                                                                                                                                                            |
| **Manager Capability**                      | Không gắn nhãn “manager yếu”; kiểm tra workload, quyền hạn, accountability, process.                                                                                                                                  |
| **Culture System & Trust**                  | Không kết luận “toxic culture” từ vài comment; cần evidence và dữ liệu ẩn danh.                                                                                                                                       |
| **Engagement & Employee Voice**             | Không xử lý grievance/investigation như OD listening; nếu có cáo buộc cụ thể thì escalation.                                                                                                                          |
| **Capability Architecture**                 | Không chấm điểm năng lực cá nhân; chỉ dùng role/group/system level.                                                                                                                                                   |
| **HR Analytics**                            | Không dùng dữ liệu cá nhân chưa ẩn danh; không overclaim causality.                                                                                                                                                   |
| **Legal / Compliance Boundary**             | Không diễn giải luật, không viết termination/discipline memo.                                                                                                                                                         |
| **Artifact Schema**                         | Manager/employee artifacts luôn có fairness/privacy/boundary note. Measurement + Artifact Library cũng yêu cầu artifact hướng tới manager/employee phải có boundary note và không xử lý dữ liệu cá nhân chưa ẩn danh. |

---

## Recommended Research Path v1

Dựa trên bảng ưu tiên, thứ tự viết/research nên là:

### Phase 1 — Build diagnostic core

1. OD Advisory Logic & Problem Framing
2. Problem Type Map + Symptom Library
3. Diagnostic Layers & Root-cause Patterns
4. Organization Diagnosis & Evidence Logic

### Phase 2 — Build intervention core

5. Intervention Fit Matrix + Intervention Groups
6. Intervention Anti-patterns
7. Stakeholder Engagement Logic

### Phase 3 — Build measurement and artifact core

8. Measurement & Improvement Logic
9. Artifact Schema & Output Families
10. Boundary / Safety / No Individual Judgment Pattern

### Phase 4 — Fill domain-specific core modules

11. Organization Design
12. Culture & Engagement
13. Performance & Capability
14. Leadership / Manager Effectiveness
15. Change Readiness & Enablement

### Phase 5 — Add guarded adjacent interfaces

16. HR Policy Interface
17. HR Analytics Interface
18. Legal / Compliance Boundary
19. DEI / Fairness Interface
20. Internal Communication / Rollout Interface

**Kết luận:**
Không nên bắt đầu KB01 bằng cách viết sâu toàn bộ OD domain. Nên bắt đầu từ **KB02 diagnostic core**, sau đó viết **KB03 intervention fit**, rồi mới chuẩn hóa **KB04 artifact/measurement/boundary**. KB01 nên viết song song ở mức nền vừa đủ, tránh biến thành tài liệu lý thuyết dài.
