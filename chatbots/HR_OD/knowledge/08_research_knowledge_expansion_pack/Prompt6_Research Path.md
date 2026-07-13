# HR/OD Advisor — Research Path v1

## Research Path v1

## Phase 1 — Breadth Confirmation

### Mục tiêu

Xác nhận rằng phạm vi research hiện tại đã **đủ rộng nhưng chưa bị lan scope** trước khi đào sâu P1 nodes.

Phase này không nhằm viết nội dung KB chi tiết. Mục tiêu là kiểm tra:

* Core domain đã bao phủ đúng nhiệm vụ HR/OD Advisor chưa?
* Near domain chỉ đóng vai trò interface/boundary chưa?
* Extended và Out-of-scope đã được chặn đúng chưa?
* Có node nào bị thiếu nhưng ảnh hưởng trực tiếp đến KB01–KB04 không?

Exploration Map đã phân loại rõ Core, Near, Extended và Out-of-scope; đồng thời cảnh báo các rủi ro như biến chatbot thành HR tổng quát, legal advisor, L&D designer, BI/data engineering hoặc change consultant quá rộng.

### Input

Sử dụng các artifact đã có:

1. Synthesis
2. Exploration Map
3. Keyword Expansion Matrix: Deep Core / Core / Near
4. Facet Matrix
5. Adjacent Domain Boundary Map
6. Symptom × Problem Type Matrix
7. Diagnostic Question Bank
8. Intervention Fit Matrix
9. Measurement + Artifact Starter Library

### Việc cần làm

| Việc cần làm                                    | Mục đích                                                                         |
| ----------------------------------------------- | -------------------------------------------------------------------------------- |
| 1. Rà lại Core / Near / Extended / Out-of-scope | Đảm bảo không đưa node ngoài scope vào KB01–KB04                                 |
| 2. Kiểm tra 8 P1 nodes                          | Đảm bảo P1 nodes đủ đại diện cho core runtime của chatbot                        |
| 3. Đối chiếu P1 nodes với KB01–KB04             | Biết node nào sẽ đi vào KB nào                                                   |
| 4. Kiểm tra gap còn lại                         | Xác định node nào cần research thêm trước khi viết                               |
| 5. Kiểm tra boundary                            | Đảm bảo legal/compliance, psychology, analytics, change không bị mở rộng quá mức |

### Output cần tạo

Tạo một file/bảng tên:

**Research Scope Confirmation Sheet**

Gồm các cột:

| Node / Domain | Current classification | Keep / Move / Remove | Related KB | Gap status | Decision note |
| ------------- | ---------------------- | -------------------- | ---------- | ---------- | ------------- |

### Checkpoint

Dừng Phase 1 để kiểm tra 5 câu:

1. Có node nào đang nằm trong Core nhưng thực ra chỉ nên là Near không?
2. Có node nào đang nằm trong Near nhưng cần đưa vào Core để viết KB không?
3. Có node nào Extended cần nâng lên Near không?
4. Có node nào Out-of-scope đang bị kéo vào KB không?
5. 8 P1 nodes có đủ để viết KB01–KB04 chưa?

### Stop rule

Chỉ chuyển sang Phase 2 khi:

* Không có node ngoài scope nằm trong P1.
* Không có P1 node nào bị mô tả quá rộng.
* Near domain đã được xác định là interface/boundary, không phải KB độc lập.
* Các gap quan trọng đã được gom vào P1/P2 rõ ràng.

Nếu chưa đạt, quay lại chỉnh **Node Prioritization Table** trước, không đào sâu tiếp.

---

## Phase 2 — Priority Node Deepening

### Mục tiêu

Đào sâu 8 P1 nodes để tạo nguyên liệu viết KB01–KB04.

Phase này là phần quan trọng nhất. Kết quả của phase này phải đủ để viết:

* KB01 — OD Domain Map
* KB02 — Diagnostic Frameworks
* KB03 — Intervention Playbook
* KB04 — Artifacts & Templates

### P1 nodes cần đào sâu

| P1 node                                               | Vai trò trong chatbot                                                                          | KB chính            |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------- |
| 1. OD Advisory Logic & Problem Framing                | Giúp chatbot frame đúng trước khi advise                                                       | KB01 / KB02 / KB04  |
| 2. Organization Diagnosis & Evidence Logic            | Xương sống của Diagnose                                                                        | KB02                |
| 3. Diagnostic Layers & Root-cause Patterns            | Tránh quy kết cá nhân, chọn đúng tầng nguyên nhân                                              | KB02 / KB03         |
| 4. Problem Type Map + Symptom Library                 | Route vấn đề theo Culture, Performance, Capability, Org Design, Change, Engagement, Leadership | KB01 / KB02         |
| 5. Intervention Fit Matrix + Intervention Groups      | Nối root cause với intervention phù hợp                                                        | KB03                |
| 6. Measurement & Improvement Logic                    | Đo hiệu quả, đọc tín hiệu, điều chỉnh intervention                                             | KB01 / KB03 / KB04  |
| 7. Artifact Schema & Output Families                  | Tạo proposal, memo, roadmap, checklist, dashboard, FAQ                                         | KB04                |
| 8. Boundary / Safety / No Individual Judgment Pattern | Giữ chatbot an toàn và đúng scope                                                              | KB04 / KB05 sau này |

---

### Node 1 — OD Advisory Logic & Problem Framing

#### Câu hỏi research chính

1. Khi user hỏi mơ hồ, chatbot cần frame lại như thế nào?
2. Cần phân biệt những lớp nào: symptom, interpretation, assumption, hypothesis, recommendation?
3. Khi nào chatbot được đưa recommendation tạm thời?
4. Khi nào phải ghi Missing evidence?
5. Khi nào chuyển từ Standard Task Flow sang Deep OD Advisory Flow?
6. Output framing tối thiểu cần gồm những section nào?

#### Keyword nên dùng

* problem framing
* OD advisory logic
* symptom vs cause
* assumption note
* confidence label
* missing evidence
* advisory recommendation
* diagnostic hypothesis

#### Output cần tạo

**OD Advisory Logic Sheet**

| Input pattern | Framing action | Assumption note needed? | Confidence label? | Next step | Related output |
| ------------- | -------------- | ----------------------- | ----------------- | --------- | -------------- |

#### Checkpoint

Node này đủ sâu khi chatbot có thể xử lý input mơ hồ mà không nhảy thẳng sang giải pháp.

#### Stop rule

Không đào sâu thành consulting methodology tổng quát. Chỉ giữ logic đủ dùng cho HR/OD Advisor.

---

### Node 2 — Organization Diagnosis & Evidence Logic

#### Câu hỏi research chính

1. Chatbot cần phân loại input evidence như thế nào?
2. Survey, interview, focus group, HR metrics, business signal dùng khác nhau ra sao?
3. Khi nào dữ liệu đủ để tạo hypothesis?
4. Khi nào chỉ được đưa “possible causes”?
5. Cách ghi supporting evidence / contradicting evidence như thế nào?
6. Khi nào cần confidence label?

Diagnostic Question Bank hiện đã thiết kế câu hỏi để kiểm chứng giả thuyết, không dẫn dắt kết luận, không quy kết cá nhân và giữ boundary với legal, individual judgment, sensitive data.

#### Keyword nên dùng

* OD diagnosis
* evidence-based diagnosis
* data triangulation
* supporting evidence
* contradicting evidence
* evidence gap
* diagnostic hypothesis
* confidence level
* missing evidence

#### Output cần tạo

**Evidence Logic Map**

| Evidence type | What it can support | What it cannot prove | Caveat | Related diagnostic use |
| ------------- | ------------------- | -------------------- | ------ | ---------------------- |

#### Checkpoint

Node này đủ sâu khi chatbot biết dùng dữ liệu để tạo hypothesis nhưng không overclaim.

#### Stop rule

Không chuyển thành HR analytics/data science. Chỉ dùng evidence để hỗ trợ OD diagnosis.

---

### Node 3 — Diagnostic Layers & Root-cause Patterns

#### Câu hỏi research chính

1. Mỗi symptom có thể nằm ở những diagnostic layer nào?
2. Dấu hiệu nào cho thấy root cause nằm ở manager layer?
3. Dấu hiệu nào cho thấy root cause nằm ở process/structure/system layer?
4. Làm sao tránh gán vấn đề cho cá nhân?
5. Root-cause pattern phổ biến theo từng problem type là gì?
6. Khi nào phải giữ nhiều competing hypotheses?

#### Keyword nên dùng

* diagnostic layers
* root-cause layer
* system-level cause
* manager layer
* process layer
* structure layer
* culture layer
* leadership layer
* no individual judgment

#### Output cần tạo

**Root-cause Pattern Map**

| Symptom | Possible root-cause layer | Pattern | Evidence needed | Risk if misread | Boundary note |
| ------- | ------------------------- | ------- | --------------- | --------------- | ------------- |

Symptom × Problem Type Matrix đã nhấn mạnh symptom chỉ là tín hiệu ban đầu, không phải kết luận nguyên nhân; mỗi symptom cần evidence needed và risk if misread.

#### Checkpoint

Node này đủ sâu khi mỗi symptom quan trọng có ít nhất 2–3 root-cause hypotheses.

#### Stop rule

Nếu output bắt đầu kết luận “manager yếu”, “nhân viên chống đối”, “team toxic”, phải dừng và viết lại theo layer/system logic.

---

### Node 4 — Problem Type Map + Symptom Library

#### Câu hỏi research chính

1. 7 problem type có đủ chưa?
2. Mỗi problem type có symptom đặc trưng nào?
3. Symptom nào dễ bị nhầm sang problem type khác?
4. Với mỗi problem type, data needed tối thiểu là gì?
5. Risk if misread là gì?
6. Output nào phù hợp với từng problem type?

#### Keyword nên dùng

* problem type map
* symptom library
* culture symptom
* performance system issue
* capability gap
* organization design issue
* change readiness
* engagement driver
* manager effectiveness

#### Output cần tạo

**Problem Type Research Sheet**

| Problem type | Common symptoms | Confusion pairs | Data needed | Boundary trigger | Best next output |
| ------------ | --------------- | --------------- | ----------- | ---------------- | ---------------- |

#### Checkpoint

Node này đủ sâu khi 7 problem type có symptom, confusion pair, data needed và boundary trigger.

#### Stop rule

Không mở rộng thành toàn bộ HR problem taxonomy. Chỉ giữ 7 problem type phục vụ OD Advisor.

---

### Node 5 — Intervention Fit Matrix + Intervention Groups

#### Câu hỏi research chính

1. Với mỗi root-cause layer, intervention nào phù hợp?
2. Khi nào cần diagnostic intervention trước?
3. Khi nào không nên dùng training?
4. Khi nào không nên dùng communication plan?
5. Khi nào không nên dùng culture workshop?
6. Mỗi intervention cần success condition và risk gì?

Intervention Fit Matrix hiện đã định nghĩa “best-fit intervention” là can thiệp phù hợp với root-cause layer đã được kiểm chứng, không phải “best practice”; matrix này dùng để nối KB02 sang KB04 và tránh training hóa mọi vấn đề.

#### Keyword nên dùng

* intervention fit
* intervention selection
* root cause to intervention
* intervention group
* success condition
* intervention anti-pattern
* diagnostic intervention
* organization design intervention
* manager capability intervention
* change enablement

#### Output cần tạo

**Intervention Design Sheet**

| Problem type | Root-cause layer | Best-fit intervention | Do not use when | Success condition | Related artifact | Suggested metric |
| ------------ | ---------------- | --------------------- | --------------- | ----------------- | ---------------- | ---------------- |

#### Checkpoint

Node này đủ sâu khi mỗi intervention có:

* điều kiện dùng,
* điều kiện không dùng,
* success condition,
* artifact,
* metric.

#### Stop rule

Không dùng ngôn ngữ “best practice” nếu chưa có nguồn. Không tạo intervention framework quá rộng.

---

### Node 6 — Measurement & Improvement Logic

#### Câu hỏi research chính

1. Mỗi intervention nên đo outcome gì?
2. Leading indicator nào giúp biết intervention đang đi đúng hướng?
3. Adoption metric nào phù hợp?
4. Experience metric nào cần theo dõi?
5. Data source là gì?
6. Khi nào cần caveat về attribution hoặc Missing evidence?
7. Review cadence nên là gì?

Measurement + Artifact Library quy định rõ: không dùng một metric duy nhất để kết luận thành công, không đo activity thay outcome, không dùng dữ liệu cá nhân chưa ẩn danh, không overclaim causality, và nếu thiếu baseline phải ghi Missing evidence.

#### Keyword nên dùng

* measurement architecture
* outcome metric
* leading indicator
* lagging indicator
* adoption metric
* experience metric
* baseline
* review cadence
* post-implementation review
* stop continue redesign

#### Output cần tạo

**Measurement Logic Sheet**

| Problem type / Intervention | Outcome metric | Leading indicator | Adoption metric | Experience metric | Data source | Cadence | Caveat |
| --------------------------- | -------------- | ----------------- | --------------- | ----------------- | ----------- | ------- | ------ |

#### Checkpoint

Node này đủ sâu khi mỗi intervention chính có measurement starter set.

#### Stop rule

Không đi vào BI/dashboard kỹ thuật, statistical modeling hoặc data engineering.

---

### Node 7 — Artifact Schema & Output Families

#### Câu hỏi research chính

1. Chatbot cần tạo những artifact nào?
2. Artifact nào phục vụ leadership?
3. Artifact nào phục vụ HR/OD?
4. Artifact nào phục vụ manager?
5. Artifact nào phục vụ employee?
6. Required sections của từng artifact là gì?
7. Artifact nào cần boundary note bắt buộc?

#### Keyword nên dùng

* artifact schema
* executive memo
* diagnostic report
* intervention roadmap
* rollout checklist
* manager guide
* employee FAQ
* dashboard outline
* safe alternative artifact

#### Output cần tạo

**Artifact Schema Sheet**

| Artifact | Audience | Use case | Required sections | Optional sections | Boundary note | Related KB |
| -------- | -------- | -------- | ----------------- | ----------------- | ------------- | ---------- |

#### Checkpoint

Node này đủ sâu khi mỗi artifact có audience, use case, required sections và boundary note.

#### Stop rule

Không biến KB04 thành kho template quá dài. Mỗi artifact chỉ cần schema đủ tạo output nhất quán.

---

### Node 8 — Boundary / Safety / No Individual Judgment Pattern

#### Câu hỏi research chính

1. Khi nào cần boundary note?
2. Khi nào cần HR/Legal review?
3. Khi nào cần anonymization note?
4. Khi nào không được tạo artifact?
5. Khi nào được tạo safe alternative?
6. Khi nào phải Refer to human expert?
7. Boundary pattern cần gắn vào artifact nào?

Adjacent Domain Boundary Map đã xác định legal/compliance chỉ là boundary awareness; chatbot không được tư vấn luật, diễn giải luật, viết quyết định xử lý cá nhân, chẩn đoán tâm lý cá nhân, làm data science chuyên sâu hoặc change consulting tổng quát.

#### Keyword nên dùng

* no individual judgment
* legal escalation trigger
* HR/Legal review
* sensitive data
* anonymized data
* safe alternative
* neutral checklist
* boundary note
* refer to human expert

#### Output cần tạo

**Boundary Pattern Library**

| Trigger | What chatbot must not do | Safe alternative | Boundary note | Refer to human expert? |
| ------- | ------------------------ | ---------------- | ------------- | ---------------------- |

#### Checkpoint

Node này đủ sâu khi mọi high-risk case đều có safe alternative.

#### Stop rule

Không viết legal policy, disciplinary script, termination letter, individual scoring, psychological diagnosis.

---

## Phase 3 — KB Translation Readiness

### Mục tiêu

Chuyển toàn bộ research từ Phase 2 thành cấu trúc sẵn sàng viết **KB01–KB04**.

Phase này không thêm research lan man. Chỉ làm 3 việc:

1. Chọn nội dung nào đưa vào KB nào.
2. Xác định độ sâu từng section.
3. Chuẩn hóa format viết KB.

---

### Cách chuyển research thành KB01–KB04

| KB                               | Vai trò                                               | Research input chính                                                                              | Cách viết                                                                          |
| -------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **KB01 — OD Domain Map**         | Giải thích domain, taxonomy, concept, boundary nền    | OD Advisory Logic, Problem Type Map, OD Foundations, Measurement concept, Boundary overview       | Viết vừa đủ để chatbot hiểu “đây là gì” và “nằm trong/ngoài scope nào”.            |
| **KB02 — Diagnostic Frameworks** | Chẩn đoán symptom, problem type, evidence, root cause | Symptom Library, Diagnostic Question Bank, Diagnostic Layers, Evidence Logic                      | Viết sâu nhất. Đây là lõi Diagnose.                                                |
| **KB03 — Intervention Playbook** | Chọn và thiết kế intervention                         | Intervention Fit Matrix, Intervention Groups, Anti-patterns, Stakeholder Logic, Measurement Logic | Viết theo logic “khi nào dùng / không dùng / success condition / risk / artifact”. |
| **KB04 — Artifacts & Templates** | Tạo output dùng được                                  | Artifact Schema, Measurement Starter Library, Boundary Pattern, Audience Logic                    | Viết thành template schema ngắn, dùng được cho Produce/Plan/Measure/Validate.      |

---

### Boundary rules cần áp dụng

Áp dụng các rule này trong mọi KB:

1. Không biến chatbot thành HR tổng quát.
2. Không đưa legal advice cụ thể.
3. Legal/compliance chỉ là boundary awareness.
4. Không chẩn đoán tâm lý cá nhân.
5. Không đánh giá năng lực, đạo đức, tính cách cá nhân cụ thể.
6. Không dùng dữ liệu nhân sự nhạy cảm nếu chưa ẩn danh.
7. Không overclaim khi thiếu evidence.
8. Không gọi intervention nào là best practice nếu chưa có nguồn.
9. Không mặc định training là giải pháp cho mọi vấn đề.
10. Không dùng communication plan để thay thế structure/process intervention.
11. Manager/employee-facing artifact phải có fairness và boundary note.
12. Khi cần chuyên gia thật, ghi rõ: **Refer to human expert**.

---

### Format đề xuất cho KB

## KB01 — OD Domain Map

Đề xuất format:

```markdown
# KB01 — OD Domain Map

## 1. Purpose
## 2. In-scope OD Domains
## 3. Core Concepts
## 4. Problem Type Overview
## 5. Diagnostic Layer Overview
## 6. Intervention Group Overview
## 7. Measurement Concept Overview
## 8. Boundary Overview
## 9. Common Misuse / Scope Drift
```

Độ sâu: **medium**.
Không viết quá dài, tránh thành textbook OD.

---

## KB02 — Diagnostic Frameworks

Đề xuất format:

```markdown
# KB02 — Diagnostic Frameworks

## 1. Purpose
## 2. Diagnostic Principles
## 3. Symptom × Problem Type Matrix
## 4. Diagnostic Layers
## 5. Root-cause Pattern Map
## 6. Diagnostic Question Bank
## 7. Evidence Logic
## 8. Confidence / Missing Evidence Rules
## 9. Boundary Triggers
## 10. Diagnostic Output Templates
```

Độ sâu: **high**.
Đây là KB cần viết sâu nhất.

---

## KB03 — Intervention Playbook

Đề xuất format:

```markdown
# KB03 — Intervention Playbook

## 1. Purpose
## 2. Intervention Selection Principles
## 3. Intervention Groups
## 4. Intervention Fit Matrix
## 5. When to Use / Not Use
## 6. Success Conditions
## 7. Intervention Anti-patterns
## 8. Stakeholder Engagement Logic
## 9. Measurement Link
## 10. Implementation Notes
```

Độ sâu: **high**.
Phải nối chặt với KB02 và KB04.

---

## KB04 — Artifacts & Templates

Đề xuất format:

```markdown
# KB04 — Artifacts & Templates

## 1. Purpose
## 2. Artifact Selection Logic
## 3. Advisory Artifacts
## 4. Diagnostic Artifacts
## 5. Intervention / Roadmap Artifacts
## 6. Leadership-facing Artifacts
## 7. Manager-facing Artifacts
## 8. Employee-facing Artifacts
## 9. Measurement Artifacts
## 10. Safe Alternative Artifacts
## 11. Boundary Note Patterns
```

Độ sâu: **high**, nhưng mỗi template phải ngắn và có required fields rõ.

---

### Checkpoint trước khi viết KB

Trước khi viết KB01–KB04, kiểm tra:

| Checkpoint             | Pass condition                                                                |
| ---------------------- | ----------------------------------------------------------------------------- |
| Scope clarity          | Core / Near / Extended / Out-of-scope không bị lẫn                            |
| P1 completeness        | 8 P1 nodes đều có sheet hoặc matrix đủ dùng                                   |
| Diagnostic readiness   | Symptom, problem type, layer, question, evidence logic đã nối được            |
| Intervention readiness | Root cause đã nối được intervention, success condition, metric, artifact      |
| Measurement readiness  | Có outcome, leading, adoption, experience metric cho intervention chính       |
| Artifact readiness     | Mỗi artifact có audience, use case, required sections, boundary note          |
| Safety readiness       | Có trigger và safe alternative cho legal, individual judgment, sensitive data |
| KB mapping             | Mỗi node biết nằm ở KB01, KB02, KB03 hoặc KB04                                |
| No scope drift         | Không có legal advice, psychology diagnosis, BI/data science, PMO, HR ops     |

### Stop rule

Chỉ bắt đầu viết KB khi:

* KB02 có đủ diagnostic core.
* KB03 có đủ intervention fit.
* KB04 có đủ artifact schema.
* Boundary pattern đã được nhúng vào KB02–KB04.
* Các nội dung còn thiếu được đánh dấu **Missing evidence** hoặc **Need external validation**.

Nếu chưa đạt, không viết KB hoàn chỉnh; quay lại Phase 2 để đào sâu node bị thiếu.

---

# Research Questions by KB

| KB section                                   | Main research questions                                                                       | Related P1 nodes                        | Required depth | Risk if missing                                               | Validation needed                  |
| -------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------- | -------------- | ------------------------------------------------------------- | ---------------------------------- |
| **KB01 — Purpose & Scope**                   | Chatbot này giải quyết vấn đề gì? Không giải quyết vấn đề gì? Người dùng chính là ai?         | OD Advisory Logic; Boundary Pattern     | Medium         | Chatbot bị hiểu thành HR generalist hoặc consultant tổng quát | Internal scope review              |
| **KB01 — OD Core Concepts**                  | OD, organization effectiveness, system thinking, enterprise context cần giải thích ở mức nào? | OD Advisory Logic; Problem Type Map     | Medium         | KB01 thành lý thuyết quá dài hoặc quá nông                    | Domain expert review optional      |
| **KB01 — Problem Type Overview**             | 7 problem type có đủ và đúng scope không?                                                     | Problem Type Map + Symptom Library      | Medium         | Chatbot không route đúng Diagnose/Design                      | Internal consistency check         |
| **KB01 — Diagnostic Layer Overview**         | Cần giới thiệu diagnostic layer ra sao để tránh quy kết cá nhân?                              | Diagnostic Layers                       | Medium         | User hiểu sai rằng chatbot đánh giá cá nhân                   | Safety review                      |
| **KB01 — Measurement Concept Overview**      | Outcome, leading, lagging, adoption, experience, business linkage cần định nghĩa thế nào?     | Measurement & Improvement Logic         | Medium         | Measure output nông, chỉ có KPI chung chung                   | OD/HR practitioner review optional |
| **KB02 — Diagnostic Principles**             | Chatbot cần chẩn đoán theo logic nào? Khi nào chỉ đưa hypothesis?                             | Diagnosis & Evidence; OD Advisory Logic | High           | Chatbot overclaim hoặc nhảy thẳng sang solution               | High-priority review               |
| **KB02 — Symptom × Problem Type**            | Mỗi symptom có thể thuộc problem type nào? Có confusion pairs nào?                            | Problem Type + Symptom Library          | High           | Chatbot hiểu sai input người dùng                             | Test scenario validation           |
| **KB02 — Root-cause Patterns**               | Root cause có thể nằm ở layer nào? Evidence nào cần kiểm chứng?                               | Diagnostic Layers; Evidence Logic       | High           | Quy kết cá nhân hoặc chọn sai intervention                    | Safety + domain review             |
| **KB02 — Diagnostic Question Bank**          | Câu hỏi tối thiểu và câu hỏi đầy đủ cho từng problem type là gì?                              | Diagnosis & Evidence; Problem Type Map  | High           | Chatbot hỏi lan man hoặc thiếu câu hỏi quan trọng             | Test with scenarios                |
| **KB02 — Evidence / Confidence Rules**       | Khi nào ghi Missing evidence, Assumption, Confidence label?                                   | Diagnosis & Evidence; Boundary Pattern  | High           | Kết luận chắc khi thiếu dữ liệu                               | Safety review                      |
| **KB03 — Intervention Selection Principles** | Chọn intervention dựa trên gì? Khi nào diagnostic first?                                      | Intervention Fit; Diagnostic Layers     | High           | Chọn solution sai tầng                                        | Domain review                      |
| **KB03 — Intervention Groups**               | Mỗi intervention group dùng khi nào? Không dùng khi nào?                                      | Intervention Fit Matrix                 | High           | Training hóa mọi vấn đề hoặc slogan hóa culture               | Test scenario validation           |
| **KB03 — Anti-patterns**                     | Lỗi can thiệp nào cần cảnh báo?                                                               | Intervention Fit; Boundary Pattern      | High           | Đề xuất nghe hay nhưng triển khai thất bại                    | Practitioner review optional       |
| **KB03 — Success Conditions**                | Với mỗi intervention, điều kiện thành công là gì?                                             | Intervention Fit; Measurement Logic     | High           | Intervention không có outcome rõ                              | Internal consistency check         |
| **KB03 — Stakeholder Logic**                 | Sponsor, owner, affected group, manager, employee tham gia thế nào?                           | Intervention Fit; Artifact Schema       | Medium–High    | Roadmap thiếu owner và adoption mechanism                     | Practitioner review optional       |
| **KB04 — Artifact Selection Logic**          | Khi nào dùng memo, roadmap, diagnostic report, manager guide, employee FAQ?                   | Artifact Schema; OD Advisory Logic      | High           | Produce output sai format hoặc sai audience                   | Output test                        |
| **KB04 — Advisory Artifacts**                | Diagnostic report, hypothesis table, recommendation note cần section nào?                     | Artifact Schema; Diagnosis & Evidence   | High           | Output tư vấn dài nhưng không dùng được                       | Output test                        |
| **KB04 — Implementation Artifacts**          | Roadmap, rollout checklist, stakeholder map cần field nào?                                    | Artifact Schema; Intervention Fit       | High           | Plan thiếu owner, checkpoint, risk                            | Output test                        |
| **KB04 — Measurement Artifacts**             | Dashboard outline, KPI table, PIR template cần metric/data/cadence nào?                       | Measurement & Improvement Logic         | High           | Dashboard chung chung, không ra quyết định được               | Measurement review                 |
| **KB04 — Manager-facing Artifacts**          | Manager guide/talking points cần boundary nào?                                                | Artifact Schema; Boundary Pattern       | High           | Biến thành script kỷ luật hoặc quy kết cá nhân                | Safety review                      |
| **KB04 — Employee-facing Artifacts**         | Employee FAQ/change communication cần clarity, fairness, voice thế nào?                       | Artifact Schema; Boundary Pattern       | High           | Truyền thông một chiều hoặc thiếu fairness                    | Safety + communication review      |
| **KB04 — Safe Alternative Artifacts**        | Khi nào tạo checklist trung lập, HR/Legal questions, anonymization note?                      | Boundary Pattern                        | High           | Chatbot vượt legal/safety boundary                            | Mandatory safety review            |

---

# Definition of Done

Research Expansion Pack được xem là đủ tốt để chuyển sang viết KB01–KB04 khi đạt các tiêu chí sau:

## 1. Scope readiness

* Core / Near / Extended / Out-of-scope đã rõ.
* Không có node ngoài scope trong P1.
* Near domains chỉ đóng vai trò interface hoặc boundary.
* Legal/compliance không có nội dung advice pháp lý cụ thể.
* Organizational Psychology không có chẩn đoán tâm lý cá nhân.
* HR Analytics không có data science/BI chuyên sâu.
* Change Management không biến thành consulting framework quá rộng.

## 2. Diagnostic readiness

* 7 problem type đã có symptom library.
* Mỗi symptom quan trọng có possible problem type, root-cause layers, evidence needed, risk if misread.
* Diagnostic Question Bank có minimum questions và full questions.
* Có rule cho Missing evidence, Assumption note, Confidence label.
* Có safety trigger cho individual judgment, legal, sensitive data.

## 3. Intervention readiness

* Có intervention groups rõ.
* Có Intervention Fit Matrix nối problem type + root-cause layer + intervention.
* Mỗi intervention chính có “use when / do not use when”.
* Có success condition.
* Có anti-pattern.
* Có related artifact và suggested metric.

## 4. Measurement readiness

* Mỗi intervention chính có outcome metric, leading indicator, adoption metric, experience metric.
* Có data source và review cadence.
* Có caveat cho missing baseline, attribution risk, weak data.
* Không dùng activity metric thay outcome.
* Không dùng dữ liệu cá nhân chưa ẩn danh.

## 5. Artifact readiness

* Có artifact families cho advisory, diagnostic, implementation, leadership-facing, manager-facing, employee-facing, measurement và safe alternative.
* Mỗi artifact có audience, use case, required sections, optional sections và boundary note.
* Manager/employee-facing artifact có fairness và no-individual-judgment boundary.
* Safe alternative artifact có HR/Legal escalation question, neutral checklist hoặc anonymization note.

## 6. KB mapping readiness

* Mỗi P1 node đã biết nằm ở KB nào.
* Không có nội dung quan trọng bị bỏ trống giữa KB02 → KB03 → KB04.
* KB01 chỉ giữ vai trò domain map và concept overview, không thành tài liệu OD học thuật dài.
* KB02 là KB sâu nhất về diagnosis.
* KB03 nối diagnosis với intervention.
* KB04 biến tư vấn thành output dùng được.

## 7. Validation readiness

* Có ít nhất 1 test scenario cho mỗi problem type.
* Có ít nhất 1 test scenario high-risk cho legal/individual/sensitive data boundary.
* Có ít nhất 1 test scenario cho manager-facing artifact.
* Có ít nhất 1 test scenario cho employee-facing artifact.
* Có ít nhất 1 test scenario cho measurement/dashboard output.
* Các phần **Needs verification** hoặc **Missing evidence** đã được đánh dấu, không giả vờ chắc chắn.

## 8. External / expert review needed

Cần ghi **Need external validation** hoặc **Refer to human expert** cho các phần sau:

| Area                      | Khi nào cần review                                                                        |
| ------------------------- | ----------------------------------------------------------------------------------------- |
| Legal / compliance        | Khi có sa thải, kỷ luật, điều chuyển, grievance, harassment, discrimination, labor impact |
| HR analytics              | Khi cần thống kê nghiêm ngặt, dữ liệu cá nhân, dữ liệu nhóm nhỏ, data governance          |
| Organizational psychology | Khi có sức khỏe tâm thần, wellbeing cá nhân, clinical concern                             |
| Change / restructuring    | Khi change có tác động lao động lớn hoặc tái cấu trúc nhạy cảm                            |
| Performance / calibration | Khi output có thể ảnh hưởng rating, promotion, discipline hoặc compensation               |
| DEI / fairness            | Khi có cáo buộc hoặc rủi ro discrimination/adverse impact                                 |

---

## Kết luận triển khai

Thứ tự thực tế nên làm là:

1. **Hoàn thiện Phase 1 trong 1 bảng Scope Confirmation Sheet.**
2. **Đào sâu 8 P1 nodes trong Phase 2.**
3. **Chuyển từng research sheet sang KB01–KB04 trong Phase 3.**
4. **Chỉ sau đó mới viết KB hoàn chỉnh.**

Điểm quan trọng nhất:
**Đừng bắt đầu bằng cách viết KB01 thật dài.**
Hãy bắt đầu từ **KB02 diagnostic core**, vì nếu chẩn đoán yếu thì KB03 intervention và KB04 artifact đều sẽ yếu theo.
