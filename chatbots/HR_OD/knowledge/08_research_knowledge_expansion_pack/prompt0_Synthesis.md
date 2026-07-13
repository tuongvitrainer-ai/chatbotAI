# SYNTHESIS:  Research Expansion Scope Summary — HR/OD Advisor

## 1. Input Summary

### 1.1. Chatbot này phục vụ ai?

**Fact từ input:**
HR/OD Advisor phục vụ nhóm người dùng chính gồm **HR Manager, OD Manager, HRBP cấp quản lý và người phụ trách dự án OD trong tập đoàn**. Các nhóm này cần xử lý vấn đề tổ chức, thiết kế chương trình năng lực/văn hóa/hiệu suất/thay đổi, tư vấn cho business unit, và chuẩn bị proposal, workshop, rollout plan, KPI, feedback loop.

**Interpretation:**
Người dùng không phải nhóm HR vận hành phổ thông, mà là nhóm cần năng lực tư vấn, chẩn đoán, thiết kế và triển khai OD trong bối cảnh tổ chức nhiều tầng, nhiều stakeholder.

**Assumption:**
Người dùng có nền tảng HR/OD nhất định, cần chatbot như một “thinking partner” có cấu trúc, không cần chatbot giải thích HR cơ bản từ đầu trong mọi tình huống.

---

### 1.2. Bài toán chính là gì?

**Fact từ input:**
Bài toán chính là giúp người dùng chuyển từ **câu hỏi mơ hồ** sang **vấn đề được định khung**, **giả thuyết chẩn đoán**, **giải pháp OD**, **kế hoạch triển khai**, **artifact ứng dụng**, **kiểm định rủi ro**, **đo lường** và **cải tiến**.

**Interpretation:**
Research expansion không nên chỉ mở rộng “kiến thức HR/OD”, mà cần mở rộng theo logic tư vấn OD: hiểu vấn đề → chẩn đoán → chọn can thiệp → triển khai → đo lường → cải tiến.

**Assumption:**
Mục tiêu của research không phải tạo encyclopedia HR/OD, mà tạo nền tri thức đủ dùng để chatbot trả lời đúng scope, đúng độ sâu và đúng output.

---

### 1.3. Domain chính là gì?

**Fact từ input:**
Domain tổng là **HR/OD Advisor Domain**, tập trung vào Phát triển tổ chức trong bối cảnh tập đoàn, bao gồm OD foundations, enterprise context, organization system & design, culture/engagement/employee experience, performance & capability systems, leadership/manager effectiveness, change & transformation, OD diagnosis/evidence logic, intervention design, measurement/learning/improvement.

**Interpretation:**
Domain chính không phải “HR tổng quát”, mà là **OD advisory trong enterprise context**. Các mảng HR khác chỉ được kéo vào khi chúng phục vụ chẩn đoán hoặc can thiệp OD.

---

### 1.4. Output cuối cần hỗ trợ là gì?

**Fact từ input:**
Chatbot cần hỗ trợ 9 task runtime: **Explain, Compare, Diagnose, Design, Plan, Produce, Validate, Measure, Improve**. Output cần bao gồm concept note, comparison table, hypothesis table, root-cause map, roadmap, proposal, memo, workshop agenda, checklist, dashboard outline, risk matrix, improvement plan.
**Interpretation:**
Research expansion cần phục vụ cả 3 lớp output:

1. **Advisory output:** framing, diagnosis, recommendation, risk.
2. **Implementation output:** roadmap, stakeholder plan, rollout checklist.
3. **Artifact output:** proposal, memo, agenda, guide, dashboard, KPI/OKR draft.

---

## 2. Scope Boundary

### 2.1. In-scope

**Fact từ input:**
Các vùng core gồm: OD fundamentals, organization diagnosis, organization design, culture & engagement, leadership & manager capability, performance & capability systems, change management/enablement, intervention design, measurement & improvement, validation & epistemic control.

**Research expansion nên bao gồm:**

| In-scope area                       | Mục đích research                                                           |
| ----------------------------------- | --------------------------------------------------------------------------- |
| OD foundations & enterprise context | Làm rõ khái niệm OD, system thinking, enterprise complexity                 |
| Organization design                 | Structure, role clarity, decision rights, operating model, governance       |
| Culture & engagement                | Culture system, behavior norms, trust, employee voice, engagement drivers   |
| Performance & capability            | KPI/OKR, PMS ở cấp hệ thống, competency/capability architecture             |
| Leadership & manager effectiveness  | Leadership alignment, manager capability, middle management layer           |
| Change & transformation             | Readiness, resistance, sponsor alignment, adoption, change enablement       |
| Diagnosis & evidence logic          | Symptom, root cause, diagnostic layers, hypothesis, confidence              |
| Intervention design                 | Intervention fit, intervention components, success conditions, risks        |
| Measurement & improvement           | Leading/lagging indicators, adoption metrics, feedback loop, learning cycle |
| Validation & safety                 | Assumption, confidence, risk, no individual judgment, escalation            |

---

### 2.2. Near-scope

**Fact từ input:**
Adjacent domains gồm HR policy, talent management, L&D, workforce analytics, labor law/compliance, DEI/fairness, internal communication, project management, business strategy — nhưng chỉ được kéo vào khi có liên quan đến OD và phải có giới hạn rõ.

**Interpretation:**
Near-scope là vùng hỗ trợ, không phải vùng mở rộng chính. Chỉ research ở mức **boundary + interface logic**, không viết thành KB chuyên sâu độc lập.

| Near-scope area        | Khi nào dùng                                            | Giới hạn research                               |
| ---------------------- | ------------------------------------------------------- | ----------------------------------------------- |
| HR policy              | Khi intervention chạm chính sách tổ chức                | Không viết policy thay HR owner                 |
| Talent management      | Khi competency, succession, career liên quan capability | Không mở rộng toàn bộ talent suite              |
| L&D                    | Khi intervention cần capability building                | Không thiết kế khóa học chi tiết ngoài OD       |
| Workforce analytics    | Khi cần đọc dữ liệu HR/OD                               | Không làm BI/data engineering                   |
| Legal/compliance       | Khi có rủi ro pháp lý                                   | Chỉ tạo checklist/escalation, không tư vấn luật |
| DEI/fairness           | Khi liên quan công bằng, bias, employee voice           | Không kết luận cáo buộc cá nhân                 |
| Internal communication | Khi cần change communication                            | Không biến thành PR/content bot                 |
| Project management     | Khi cần rollout plan                                    | Không biến thành PMO bot                        |
| Business strategy      | Khi cần align OD với strategy                           | Không tư vấn chiến lược kinh doanh tổng thể     |

---

### 2.3. Out-of-scope

**Fact từ input:**
Các vùng ngoài scope gồm tư vấn pháp lý lao động chuyên sâu, quyết định sa thải/kỷ luật/cá nhân, đánh giá năng lực/đạo đức/tính cách cá nhân cụ thể, xử lý dữ liệu nhạy cảm chưa ẩn danh, coaching/chẩn đoán tâm lý cá nhân, C&B chi tiết, payroll/HR admin/hợp đồng, recruitment sourcing/interview scoring cá nhân, employee relations investigation, business strategy consulting tổng thể.

**Research expansion không nên bao gồm:**

* Luật lao động chuyên sâu.
* Mẫu email sa thải/kỷ luật/quyết định cá nhân.
* Scoring cá nhân cho tuyển dụng, thăng chức, điều chuyển, kỷ luật.
* Payroll, hợp đồng, HR admin.
* Compensation & benefits design chi tiết.
* Điều tra employee relations.
* Coaching tâm lý hoặc chẩn đoán tâm lý cá nhân.
* Business strategy consulting ngoài phần OD implication.

---

## 3. Existing Knowledge Map

### 3.1. Các node đã có trong Decomposition Pack

**Fact từ input:**
Domain Decomposition Pack đã tách rõ domain tree, functional map, stakeholder map, problem type map, intervention map và boundary map. Pack cũng nhấn mạnh mỗi node mới là khung phân rã, chưa phải nội dung KB chi tiết.

#### A. Domain nodes đã có

| Node chính                          | Tình trạng hiện tại                                   | Research expansion cần thêm                                              |
| ----------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------ |
| OD Foundations & Enterprise Context | Đã có node và sub-node                                | Cần định nghĩa, ví dụ enterprise, misconception, boundary                |
| Organization System & Design        | Đã có structure/role/operating model                  | Cần symptom pattern, diagnostic cues, intervention options               |
| Culture, Engagement & EX            | Đã có culture system, drivers, touchpoints            | Cần phân biệt culture vs engagement vs EX, trigger và output implication |
| Performance & Capability Systems    | Đã có PMS, capability, talent linkage                 | Cần boundary giữa OD và HR performance/talent specialty                  |
| Leadership & Manager Effectiveness  | Đã có leadership system, manager capability           | Cần pattern chẩn đoán manager issue không quy kết cá nhân                |
| Change & Transformation             | Đã có readiness, enablement, problems                 | Cần adoption logic, stakeholder readiness, communication boundary        |
| OD Diagnosis & Evidence Logic       | Đã có input types, layers, hypothesis, evidence risks | Cần question bank, confidence rules, evidence interpretation             |
| OD Intervention Design              | Đã có strategy, components, logic, risks              | Cần fit matrix, anti-patterns, success conditions                        |
| Measurement & Improvement           | Đã có measurement architecture, data source, cadence  | Cần metric library theo intervention type                                |

#### B. Functional map đã có

**Fact từ input:**
Functional Map gồm Learn → Diagnose → Design → Plan → Produce → Validate → Measure → Improve; mỗi function đã có user intent, input pattern, chatbot action, output candidate và KB implication.

**Interpretation:**
Functional map đủ làm nền cho Prompt Exploration Map, nhưng cần research thêm “input pattern” và “output pattern” cụ thể theo từng task type.

#### C. Problem type map đã có

**Fact từ input:**
Problem type map đã bao gồm Culture, Performance, Competency, Organization Design, Change, Engagement, Leadership; mỗi problem type có symptom, diagnostic focus, output phù hợp và intervention liên quan.

**Missing input:**
Chưa có đủ:

* Symptom library chi tiết theo từng problem type.
* Confusion pairs, ví dụ: engagement thấp nhưng root cause là manager capability hoặc workload.
* Diagnostic question bank theo từng problem type.
* Red flag / safety trigger theo từng problem type.
* Output mẫu theo từng problem type.

#### D. Intervention map đã có

**Fact từ input:**
Intervention Map đã có Diagnostic, Organization Design, Culture & Behavior, Leadership Alignment, Manager Capability, Performance System, Competency & Capability, Change Enablement, Engagement & Employee Voice, Measurement & Learning. Logic chọn intervention cũng đã nêu: problem chưa rõ thì diagnosis trước; role/decision/process thì org design; norms/trust thì culture; manager behavior thì manager capability + leadership alignment; adoption/resistance thì change enablement; mọi intervention nên có measurement layer.

**Missing input:**
Chưa có đủ:

* Intervention profile chi tiết.
* Điều kiện dùng / không dùng từng intervention.
* Minimum viable intervention vs full intervention.
* Risk/anti-pattern cụ thể.
* Output artifact tương ứng với từng intervention.
* Metric tương ứng với từng intervention.

---

### 3.2. Các cấu trúc đã có trong IA Pack

**Fact từ input:**
IA Pack đã thiết kế taxonomy theo vai trò runtime của tri thức, chia thành 6 nhóm KB: Domain Knowledge, Diagnostic Knowledge, Intervention Knowledge, Artifact Knowledge, Validation & Safety Knowledge, Routing & Output Knowledge.

#### A. KB architecture đã có

| KB                                    | Vai trò hiện tại                                 | Research expansion implication                                 |
| ------------------------------------- | ------------------------------------------------ | -------------------------------------------------------------- |
| KB01 — OD Domain Map                  | Nền khái niệm/domain                             | Cần glossary, domain boundaries, core concepts, misconceptions |
| KB02 — Diagnostic Frameworks          | Đọc triệu chứng, dữ liệu, root cause, hypothesis | Cần symptom taxonomy, root-cause patterns, question bank       |
| KB03 — Intervention Playbook          | Chọn và thiết kế intervention                    | Cần intervention profiles, fit logic, risk, success conditions |
| KB04 — Artifacts & Templates          | Tạo proposal, memo, roadmap, agenda, dashboard   | Cần template schema và examples                                |
| KB05 — Validation & Safety            | Safety, risk, assumption, confidence             | Cần trigger library, safe alternatives, confidence labels      |
| KB06 — Output Standards & Task Router | Route task, chọn KB, chọn output, depth          | Cần intent pattern, output contracts, good/bad examples        |

#### B. Entity Relationship Map đã có

**Fact từ input:**
IA Pack đã xác định các entity lõi: Problem, Symptom, Root cause, Stakeholder, Intervention, Artifact, Metric, Risk. Relationship graph đi theo logic: problem được chỉ báo bởi symptom, có thể do root cause, được xử lý bằng intervention, truyền đạt qua artifact, đo bằng metric, và có thể kích hoạt validation/safety.

**Interpretation:**
Đây là xương sống rất tốt cho research expansion. Các nội dung research nên được map vào entity, tránh gom kiến thức lan man theo “chủ đề HR”.

#### C. Task × Knowledge Matrix đã có

**Fact từ input:**
IA Pack đã xác định task nào dùng KB nào: Explain ưu tiên KB01; Diagnose ưu tiên KB02; Design ưu tiên KB03; Plan dùng KB03 + KB04; Produce dùng KB04 + KB06; Validate dùng KB05; Measure dùng KB01 + KB04; Improve quay lại KB02 + KB03 + KB04.

**Interpretation:**
Research expansion nên bám matrix này. Không nên research mọi domain ở cùng độ sâu; nên ưu tiên những phần tạo khác biệt tư vấn: Diagnose, Intervention, Safety, Output.

---

### 3.3. Những phần có vẻ còn thiếu

**Missing input — ở mức domain/content:**

1. Chưa có **Prompt Exploration Map** để chỉ rõ câu hỏi research nào cần hỏi cho từng node.
2. Chưa có **keyword matrix** cho các chủ đề OD chính.
3. Chưa có **source strategy**: loại nguồn nào được phép dùng, nguồn nào không dùng, cách ghi nhận nguồn.
4. Chưa có **benchmark/source inventory**; input cũng yêu cầu không tự bịa benchmark hoặc best practice.
5. Chưa có **depth rule cho research**: node nào chỉ cần overview, node nào cần viết sâu.
6. Chưa có **node prioritization** đầy đủ theo business value / runtime frequency / risk / KB dependency.
7. Chưa có **external framework boundary**: framework nào được phép đưa vào, framework nào cần tránh nếu không có nguồn.
8. Chưa có **example library** theo bối cảnh tập đoàn.
9. Chưa có **diagnostic question bank** theo problem type.
10. Chưa có **intervention fit matrix** chi tiết.
11. Chưa có **artifact schema chi tiết** cho KB04.
12. Chưa có **safety scenario library** cho KB05.
13. Chưa có **good/bad output examples** cho KB06.

---

## 4. Research Expansion Risk

### 4.1. Rủi ro nếu mở rộng quá hẹp

| Rủi ro                        | Hệ quả                                                                       |
| ----------------------------- | ---------------------------------------------------------------------------- |
| Chỉ research OD concepts      | Chatbot trả lời như tài liệu lý thuyết, yếu ở Diagnose/Design/Plan           |
| Bỏ qua diagnostic logic       | Chatbot nhảy thẳng sang giải pháp, vi phạm nguyên tắc Diagnose before Design |
| Bỏ qua intervention risk      | Chatbot đề xuất chương trình nghe hay nhưng không triển khai được            |
| Bỏ qua measurement            | Chatbot thiếu learning loop, không hỗ trợ Measure/Improve                    |
| Bỏ qua stakeholder/adaptation | Output không phù hợp HR Manager, OD Manager, HRBP, Leadership, Line Manager  |
| Bỏ qua safety/validation      | Chatbot overclaim, có thể quy kết cá nhân hoặc tạo artifact rủi ro           |

**Interpretation:**
Mở rộng quá hẹp sẽ làm chatbot trở thành “OD explainer”, không đạt positioning là “OD advisor có cấu trúc”.

---

### 4.2. Rủi ro nếu mở rộng quá rộng

| Rủi ro                             | Hệ quả                                                                |
| ---------------------------------- | --------------------------------------------------------------------- |
| Mở rộng sang HR tổng quát          | Chatbot trôi sang payroll, recruitment, C&B, HR admin                 |
| Mở rộng sang legal/compliance sâu  | Tạo rủi ro tư vấn pháp lý thay Legal                                  |
| Mở rộng sang đánh giá cá nhân      | Vi phạm No Individual Judgment                                        |
| Mở rộng sang PMO/business strategy | Làm loãng OD scope                                                    |
| Nhồi quá nhiều framework           | Chatbot thiếu ổn định, dễ chọn framework sai bối cảnh                 |
| Dùng best practice không nguồn     | Vi phạm constraint không bịa nguồn/benchmark/framework                |
| Research quá nhiều chi tiết        | KB khó dùng trong Custom GPT, retrieval nhiễu, MI phải gánh quá nhiều |

**Interpretation:**
Mở rộng quá rộng sẽ phá positioning: chatbot không còn là HR/OD Advisor mà thành HR consultant tổng quát, legal-lite, PMO-lite hoặc business strategy bot.

---

## 5. Recommendation for Next Step

### 5.1. Miền nên bắt đầu mở rộng trước

**Recommendation:**
Nên bắt đầu research expansion theo thứ tự sau:

| Priority | Miền research                           | Lý do ưu tiên                                                                                            |
| -------: | --------------------------------------- | -------------------------------------------------------------------------------------------------------- |
|        1 | **OD Diagnosis & Evidence Logic**       | Đây là năng lực lõi để tránh nhảy thẳng sang giải pháp; cũng là điểm khác biệt so với chatbot HR hỏi đáp |
|        2 | **Problem Type Map + Symptom Library**  | Giúp chatbot nhận diện Culture, Performance, Competency, Org Design, Change, Engagement, Leadership      |
|        3 | **Intervention Selection Logic**        | Giúp chuyển từ diagnosis sang solution đúng tầng vấn đề                                                  |
|        4 | **Boundary & Safety Expansion**         | Cần khóa scope sớm để không trôi sang legal, ER, individual judgment                                     |
|        5 | **Measurement & Learning Logic**        | Cần cho Measure/Improve và giúp mọi intervention có feedback loop                                        |
|        6 | **Artifact & Output Schema**            | Cần để chatbot tạo proposal, roadmap, memo, agenda, dashboard dùng được                                  |
|        7 | **OD Foundations & Enterprise Context** | Cần nhưng không nên research quá sâu trước; dùng làm nền cho Explain/Compare                             |
|        8 | **Adjacent-domain Boundary Map**        | Chỉ mở rộng ở mức interface: HR policy, L&D, analytics, legal/compliance, DEI, communication, PM         |

---

### 5.2. Research Expansion Pack nên tạo tiếp

**Recommendation:**
Bước tiếp theo nên tạo **Prompt Exploration Map** với các nhóm prompt sau:

1. **Core OD Domain Exploration**

   * OD foundations
   * Enterprise context
   * Organization design
   * Culture/engagement/EX
   * Performance/capability
   * Leadership/manager effectiveness
   * Change/transformation

2. **Diagnostic Exploration**

   * Symptom taxonomy
   * Diagnostic layers
   * Root-cause patterns
   * Evidence quality
   * Hypothesis table
   * Diagnostic question bank

3. **Intervention Exploration**

   * Intervention groups
   * Fit by problem type
   * Success conditions
   * Anti-patterns
   * Implementation risks
   * Measurement layer

4. **Adjacent-domain Boundary Exploration**

   * Org psychology
   * Change management
   * HR analytics
   * Legal/compliance boundary
   * DEI/fairness
   * Internal communication
   * L&D / talent boundary

5. **Output & Artifact Exploration**

   * Advisory artifacts
   * Implementation artifacts
   * Leadership-facing artifacts
   * Manager-facing artifacts
   * Employee-facing artifacts
   * Safe alternative artifacts

6. **Safety & Validation Exploration**

   * Safety triggers
   * No individual judgment
   * Sensitive data handling
   * Escalation patterns
   * Assumption note
   * Confidence label
   * Risk matrix

---

### 5.3. Node prioritization rule đề xuất

**Recommendation:**
Khi vào Prompt Exploration Map, nên ưu tiên node theo 5 tiêu chí:

| Tiêu chí          | Câu hỏi đánh giá                                                         |
| ----------------- | ------------------------------------------------------------------------ |
| Runtime frequency | Node này có thường xuyên xuất hiện trong câu hỏi người dùng không?       |
| Advisory value    | Node này có giúp chatbot tư vấn sâu hơn không?                           |
| Safety risk       | Node này có dễ dẫn đến legal/individual judgment/privacy risk không?     |
| Output dependency | Node này có ảnh hưởng đến proposal, roadmap, KPI, memo, dashboard không? |
| Scope control     | Node này có giúp chatbot không trôi sang HR tổng quát không?             |

**Priority recommendation:**
Node nên viết sâu trước: **Diagnosis, Problem Type, Intervention Selection, Safety/Validation, Measurement, Artifact Schema**.
Node chỉ cần overview trước: **OD Foundations, Enterprise Context, Adjacent Domains**.
Node cần boundary mạnh: **Legal/compliance, HR policy, ER investigation, individual decision, sensitive data, recruitment scoring, C&B, payroll**.

---

## Kết luận chuẩn hóa

**Fact từ input:** HR/OD Advisor đã có framing rõ, domain decomposition khá đầy đủ và IA đủ để thiết kế KB01–KB06.

**Interpretation:** Bộ artifact hiện tại đã đủ để bước sang research expansion, nhưng chưa đủ để viết KB chi tiết.

**Assumption:** Bước tiếp theo không nên viết Master Instruction ngay; nên tạo Prompt Exploration Map để mở rộng có kiểm soát, sau đó mới viết KB outline và KB chi tiết.

**Recommendation:** Research expansion nên tập trung vào **OD diagnosis → problem type → intervention fit → safety/validation → measurement → artifact schema**, đồng thời chỉ xử lý adjacent domains ở mức boundary để giữ chatbot đúng vai trò **HR/OD Advisor**, không biến thành chatbot HR tổng quát.
