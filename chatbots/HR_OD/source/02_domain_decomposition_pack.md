# HR/OD Advisor — Domain Decomposition Pack v1.0

> Mục đích: bóc domain HR/OD Advisor thành các bản đồ kiến thức và vận hành để chuẩn bị thiết kế KB01–KB03, IA, output schema, reasoning rules và safety rules.  
> Phạm vi: OD trong bối cảnh tập đoàn. Không mở rộng thành chatbot HR tổng quát. Không viết Master Instruction. Không viết KB chi tiết.

---

## 0. Design Principles

1. **Cấp 1 của Domain Decomposition Tree là miền tri thức OD**, không phải workflow, stakeholder hay output.
2. **Functional Map tách riêng workflow vận hành**: Learn → Diagnose → Design → Plan → Produce → Validate → Measure → Improve.
3. **Stakeholder Map tách riêng vai trò sử dụng / bị ảnh hưởng**.
4. **Problem Type Map tách riêng loại vấn đề OD** mà chatbot cần nhận diện.
5. **Intervention Map tách riêng nhóm can thiệp OD** để chuẩn bị cho KB03.
6. **Boundary Map phân biệt core / adjacent / out-of-scope** để tránh trôi sang chatbot HR tổng quát.
7. **Mỗi node chỉ là khung phân rã**, chưa phải nội dung KB chi tiết.

---

# 1. Domain Decomposition Tree 3–4 tầng

## Cấp 0 — Domain tổng

```text
HR/OD Advisor Domain
```

Chatbot cần hiểu và xử lý các vấn đề Phát triển tổ chức trong tập đoàn, từ kiến thức OD nền tảng đến chẩn đoán, thiết kế can thiệp, triển khai, đo lường và cải tiến.

---

## 1.1. OD Foundations & Enterprise Context

### 1.1.1. OD Core Concepts

- Organizational Development / Phát triển tổ chức
- Organization effectiveness / Hiệu quả tổ chức
- Organization health / Sức khỏe tổ chức
- System thinking trong OD
- Mối quan hệ giữa strategy, structure, people, process, culture

### 1.1.2. Enterprise Context

- Tập đoàn đa đơn vị / đa phòng ban
- Business unit / function / corporate center
- Matrix organization
- Shared services / center of excellence
- Governance layer trong tập đoàn

### 1.1.3. OD Advisory Logic

- Tư vấn theo vấn đề tổ chức, không chỉ theo yêu cầu bề mặt
- Phân biệt symptom, cause, root cause, systemic pattern
- Phân biệt issue cấp cá nhân, team, process, structure, culture, system
- Phân biệt OD solution, HR policy, legal decision, leadership decision

### 1.1.4. OD Value Logic

- Alignment với chiến lược
- Execution effectiveness
- Capability building
- Culture and behavior shift
- Employee experience
- Sustainable performance

---

## 1.2. Organization System & Design

### 1.2.1. Organization Structure

- Functional structure
- Divisional / BU structure
- Matrix structure
- Network / project-based structure
- Corporate center vs business unit accountability

### 1.2.2. Role & Accountability Design

- Role clarity
- Decision rights
- RACI / RAPID logic
- Accountability boundary
- Role conflict and overlap

### 1.2.3. Operating Model

- Governance model
- Core process flow
- Cross-functional collaboration
- Management rhythm
- Escalation and decision cadence

### 1.2.4. Organization Design Problems

- Silo giữa phòng ban
- Chồng chéo trách nhiệm
- Thiếu ownership
- Quy trình ra quyết định chậm
- Structure không còn phù hợp với strategy

---

## 1.3. Culture, Engagement & Employee Experience

### 1.3.1. Culture System

- Giá trị cốt lõi
- Norms / chuẩn hành vi
- Leadership behavior
- Symbols, rituals, stories
- Informal power and shadow culture

### 1.3.2. Engagement Drivers

- Trust
- Meaning and purpose
- Recognition
- Growth opportunity
- Manager relationship
- Workload and wellbeing
- Fairness and voice

### 1.3.3. Employee Experience Touchpoints

- Onboarding
- Performance review
- Career development
- Manager conversation
- Internal communication
- Change experience
- Exit / retention signals

### 1.3.4. Culture & Engagement Problems

- Engagement thấp
- Niềm tin giảm
- Văn hóa đổ lỗi
- Thiếu psychological safety
- Collaboration thấp
- Resistance ngầm
- Khoảng cách giữa giá trị tuyên bố và hành vi thực tế

---

## 1.4. Performance & Capability Systems

### 1.4.1. Performance Management

- Goal setting
- KPI / OKR
- Performance review
- Feedback conversation
- Calibration
- Performance improvement logic ở cấp hệ thống

### 1.4.2. Capability Architecture

- Competency framework
- Capability model
- Skill taxonomy
- Role-based capability requirement
- Capability gap analysis

### 1.4.3. Talent & Development Linkage

- Learning need analysis
- Development pathway
- Succession readiness
- Career path
- Manager capability building

### 1.4.4. Performance & Capability Problems

- KPI không liên kết chiến lược
- Đánh giá thiếu công bằng
- Manager yếu feedback
- Competency framework quá hình thức
- Khoảng cách năng lực ảnh hưởng execution
- Learning không gắn với business outcome

---

## 1.5. Leadership & Manager Effectiveness

### 1.5.1. Leadership System

- Leadership expectations
- Leadership behavior standards
- Leadership alignment
- Leadership communication
- Leadership role trong change

### 1.5.2. Manager Capability

- Coaching and feedback
- Performance conversation
- Team alignment
- Conflict handling
- Change communication
- Employee engagement ownership

### 1.5.3. Middle Management Layer

- Vai trò cầu nối strategy → execution
- Áp lực từ trên xuống và từ team lên
- Manager overload
- Inconsistent people management practice
- Manager buy-in với OD initiative

### 1.5.4. Leadership Problems

- Lãnh đạo không thống nhất thông điệp
- Manager không làm đúng vai trò people manager
- Thiếu năng lực dẫn dắt thay đổi
- Thiếu accountability ở cấp quản lý
- Khoảng cách giữa leadership intent và employee experience

---

## 1.6. Change & Transformation

### 1.6.1. Change Context

- Transformation program
- System rollout
- Restructuring at organization level
- Culture change
- Performance system change
- New operating model

### 1.6.2. Change Readiness

- Change impact assessment
- Stakeholder readiness
- Manager readiness
- Communication readiness
- Capability readiness
- Resistance pattern

### 1.6.3. Change Enablement

- Sponsorship
- Change narrative
- Stakeholder engagement
- Communication plan
- Training / enablement
- Feedback and adoption loop

### 1.6.4. Change Problems

- Resistance
- Change fatigue
- Low adoption
- Communication breakdown
- Lack of sponsor alignment
- Rollout không nhất quán
- Initiative không chuyển thành hành vi mới

---

## 1.7. OD Diagnosis & Evidence Logic

### 1.7.1. Diagnostic Input Types

- Triệu chứng định tính
- Survey data
- Interview / focus group insight
- HR metrics
- Business performance signal
- Process observation
- Stakeholder complaint / feedback

### 1.7.2. Diagnostic Layers

- Individual layer
- Team layer
- Manager layer
- Process layer
- Structure layer
- Culture layer
- Leadership layer
- System layer

### 1.7.3. Hypothesis Logic

- Multiple hypotheses
- Evidence supporting / contradicting
- Data needed to verify
- Confidence level
- Competing explanations

### 1.7.4. Evidence Risks

- Thiếu dữ liệu
- Dữ liệu thiên lệch
- Lẫn symptom với cause
- Quy kết cá nhân quá sớm
- Dùng survey score như kết luận tuyệt đối
- Thiếu phân tách fact / interpretation / assumption

---

## 1.8. OD Intervention Design

### 1.8.1. Intervention Strategy

- Fit giữa problem type và intervention type
- Intervention level: team / function / BU / enterprise
- Direct intervention vs enabling intervention
- Short-term fix vs system redesign
- Pilot vs full rollout

### 1.8.2. Intervention Components

- Objective
- Target group
- Stakeholder
- Activities
- Owner
- Timeline
- Success condition
- Risk and mitigation

### 1.8.3. Intervention Design Logic

- Diagnose before design
- Design for implementation
- Align with business context
- Account for stakeholder readiness
- Measure and learn
- Avoid over-engineering

### 1.8.4. Intervention Risks

- Can thiệp sai tầng vấn đề
- Training hóa mọi vấn đề
- Thiếu sponsor
- Không có owner
- Không có adoption mechanism
- Không có measurement loop
- Không kiểm soát tác động phụ

---

## 1.9. OD Measurement, Learning & Improvement

### 1.9.1. Measurement Architecture

- Outcome indicators
- Leading indicators
- Lagging indicators
- Adoption metrics
- Experience metrics
- Business linkage metrics

### 1.9.2. Data Sources

- Survey
- Pulse check
- HRIS metrics
- Performance data
- Retention / turnover data
- Participation data
- Manager feedback
- Qualitative interviews

### 1.9.3. Review Cadence

- Baseline
- Pilot review
- Mid-point review
- Post-implementation review
- Quarterly learning loop
- Continuous improvement cycle

### 1.9.4. Improvement Logic

- Signal reading
- Root cause re-check
- Intervention adjustment
- Stakeholder feedback
- Scaling decision
- Stop / continue / redesign decision

---

# 2. Functional Map: Learn → Diagnose → Design → Plan → Produce → Validate → Measure → Improve

> Functional Map mô tả workflow tư vấn của chatbot, không phải cây tri thức. Mục tiêu là giúp thiết kế routing, processing packs và output templates sau này.

| Function | User intent | Input pattern | Chatbot action | Output candidate | KB implication |
|---|---|---|---|---|---|
| **Learn** | Muốn hiểu hoặc so sánh kiến thức OD | Thuật ngữ, mô hình, framework, câu hỏi "là gì/khác gì" | Giải thích, phân biệt, đưa ví dụ, so sánh trade-off | Concept note, comparison table, checklist áp dụng | KB01 |
| **Diagnose** | Muốn hiểu vấn đề tổ chức nằm ở đâu | Triệu chứng, số liệu rời rạc, survey, phản hồi, hiện tượng | Tách symptom/fact/assumption, tạo giả thuyết, đề xuất dữ liệu kiểm chứng | Problem framing, hypothesis table, diagnostic questions, root-cause map | KB02 |
| **Design** | Muốn tạo giải pháp OD | Mục tiêu, problem statement, nhóm ảnh hưởng, constraint | Context scan, chọn tầng can thiệp, thiết kế solution structure | Design principles, intervention options, program structure | KB03 |
| **Plan** | Muốn biến giải pháp thành triển khai | Giải pháp đã chọn, timeline, stakeholder, scope | Chia phase, owner, activity, checkpoint, risk | Roadmap, rollout plan, stakeholder plan | KB03 + KB04 |
| **Produce** | Muốn tạo artifact cụ thể | Tên tài liệu hoặc mục đích trình bày/triển khai | Tạo bản nháp theo artifact template | Proposal, memo, workshop agenda, checklist, dashboard outline | KB04 |
| **Validate** | Muốn review hoặc phản biện | Bản nháp, kế hoạch, framework, proposal | Gap analysis, assumption check, risk matrix, revision memo | Validation report, gap table, risk matrix, revision note | KB05 |
| **Measure** | Muốn đo hiệu quả OD | Chương trình/giải pháp/outcome cần đo | Xác định outcome, indicator, data source, cadence | KPI/OKR, dashboard outline, feedback loop | KB01 + KB04 |
| **Improve** | Muốn điều chỉnh sau triển khai | Kết quả, phản hồi, survey, adoption data | Signal reading, re-diagnosis, improvement hypotheses, next actions | Improvement plan, revised roadmap, learning memo | KB02 + KB03 + KB04 |

## 2.1. Functional Dependency Rule

```text
Learn có thể đứng độc lập.
Diagnose nên đứng trước Design nếu nguyên nhân chưa rõ.
Design nên đứng trước Plan nếu chưa có solution structure.
Plan nên đứng trước Produce nếu artifact phụ thuộc roadmap.
Validate có thể gắn vào Diagnose / Design / Plan / Produce / Measure.
Measure nên được thiết kế trước hoặc trong quá trình triển khai, không chỉ sau triển khai.
Improve phụ thuộc vào Measure hoặc ít nhất có feedback signal.
```

---

# 3. Stakeholder Map

> Stakeholder Map cho thấy chatbot cần hiểu vai trò nào, nhu cầu nào và rủi ro nào. Đây không phải danh sách người dùng chính duy nhất; có stakeholder là người dùng trực tiếp, có stakeholder là người bị ảnh hưởng.

| Stakeholder | Vai trò trong OD context | Nhu cầu / câu hỏi thường gặp | Output chatbot nên hỗ trợ | Rủi ro cần kiểm soát |
|---|---|---|---|---|
| **HR Manager** | Quản lý bài toán HR/OD cấp công ty hoặc phòng ban | Vấn đề này nên xử lý thế nào? Có rủi ro gì? Cần trình lãnh đạo ra sao? | Problem framing, action plan, memo, risk checklist, stakeholder note | Quá thiên về giải pháp nhanh; bỏ qua nguyên nhân hệ thống |
| **OD Manager** | Thiết kế chương trình OD, culture, capability, performance, change | Nên dùng framework nào? Can thiệp nào phù hợp? Roadmap thế nào? | OD framework, intervention design, roadmap, risk matrix, measurement plan | Thiết kế quá phức tạp hoặc xa khả năng triển khai |
| **HRBP** | Tư vấn cho BU, hỗ trợ line manager, nối business với HR/OD | Làm sao tư vấn cho BU? Nên hỏi manager gì? Nên xử lý tension thế nào? | Diagnostic questions, talking points, stakeholder map, quick action plan | Bị kéo vào quyết định cá nhân hoặc xử lý case nhạy cảm |
| **CEO / Leadership** | Sponsor, ra quyết định chiến lược, cấp nguồn lực, làm gương | Tại sao cần làm? Tác động business là gì? Rủi ro nếu không làm? | Executive memo, business case, decision brief, risk/impact summary | Chatbot không được thay leadership ra quyết định |
| **Line Manager** | Người triển khai trực tiếp trong team, ảnh hưởng trải nghiệm nhân viên | Tôi cần làm gì với team? Nói chuyện với nhân viên ra sao? Theo dõi thế nào? | Manager guide, conversation guide, checklist, team action plan | Không quy kết cá nhân; tránh biến OD thành xử lý cá nhân |
| **Employee** | Người chịu tác động bởi chính sách, thay đổi, chương trình OD | Tôi bị ảnh hưởng thế nào? Tổ chức có công bằng không? Có kênh phản hồi không? | Employee communication draft, FAQ, feedback mechanism | Không xử lý dữ liệu cá nhân nhạy cảm; bảo vệ công bằng và voice |

## 3.1. Stakeholder Tension Patterns

| Tension | Biểu hiện | Chatbot cần hỗ trợ |
|---|---|---|
| Leadership muốn nhanh, OD cần chẩn đoán | Yêu cầu action ngay khi chưa rõ nguyên nhân | Assumption note + staged recommendation |
| HR muốn chuẩn hóa, BU muốn linh hoạt | Framework chung bị phản đối khi triển khai | Core standard + local adaptation logic |
| Manager muốn xử lý cá nhân, OD cần xử lý hệ thống | Vấn đề performance bị quy về một người | Boundary + system diagnosis |
| Employee cần tiếng nói, leadership cần kiểm soát | Thay đổi bị nhìn là áp đặt | Feedback loop + communication plan |
| HRBP bị kẹt giữa business và HR policy | Business yêu cầu xử lý nhanh nhưng rủi ro cao | Safe escalation + neutral talking points |

---

# 4. Problem Type Map

> Problem Type Map là taxonomy loại vấn đề OD mà chatbot cần nhận diện. Mỗi problem type có symptom, diagnostic focus và output phù hợp.

| Problem type | Symptom phổ biến | Diagnostic focus | Output phù hợp | Can thiệp có thể liên quan |
|---|---|---|---|---|
| **Culture** | Văn hóa đổ lỗi, thiếu trust, phối hợp yếu, giá trị không đi vào hành vi | Norms, leadership behavior, informal system, psychological safety | Culture diagnosis, behavior gap map, culture intervention design | Leadership alignment, behavior standards, rituals, communication, recognition |
| **Performance** | KPI lệch, đánh giá thiếu công bằng, hiệu suất không ổn định, review hình thức | Goal alignment, performance process, manager feedback, calibration | PMS review, KPI/OKR map, performance process redesign | Goal-setting redesign, calibration, manager feedback training, review cadence |
| **Competency** | Năng lực không đáp ứng strategy, training không hiệu quả, career path mờ | Capability model, role requirements, skill gap, learning transfer | Competency framework, capability gap analysis, development pathway | Competency design, L&D pathway, coaching, role-based learning |
| **Organization Design** | Chồng chéo trách nhiệm, silo, quyết định chậm, ownership mờ | Structure, role clarity, decision rights, operating model | Org design diagnosis, role/accountability map, operating model options | Role redesign, governance redesign, RACI/RAPID, process clarification |
| **Change** | Resistance, low adoption, change fatigue, truyền thông kém | Readiness, stakeholder impact, sponsor alignment, manager readiness | Change impact analysis, stakeholder plan, change roadmap | Change communication, sponsor alignment, enablement, adoption loop |
| **Engagement** | Engagement survey giảm, nhân viên mất động lực, turnover risk | Engagement drivers, manager relationship, workload, growth, fairness | Engagement driver analysis, hypothesis table, action plan | Manager action plan, recognition, workload review, employee voice mechanism |
| **Leadership** | Manager yếu, leadership message không thống nhất, thiếu accountability | Leadership expectation, manager capability, behavior consistency | Leadership gap analysis, manager capability program, leadership alignment plan | Manager training, leadership workshop, coaching, accountability rhythm |

## 4.1. Problem Type Routing Hints

```text
Nếu input là "điểm survey thấp" → không tự động xem là Engagement; cần xem chỉ số nào thấp.
Nếu input là "nhân viên không đạt KPI" → không tự động xem là cá nhân yếu; cần kiểm tra goal, manager, process, capability, structure.
Nếu input là "phòng ban phối hợp kém" → thường liên quan org design + culture + operating model.
Nếu input là "manager không làm" → thường liên quan leadership expectation + manager capability + workload + accountability.
Nếu input là "chống đối thay đổi" → cần kiểm tra change readiness, stakeholder impact, trust và communication.
```

---

# 5. Intervention Map: các nhóm can thiệp OD

> Intervention Map chuẩn bị cho KB03 — OD Intervention Playbook. Đây là danh mục nhóm can thiệp, không phải hướng dẫn chi tiết.

| Intervention group | Mục tiêu | Phù hợp với problem type | Thành phần thường có | Rủi ro nếu dùng sai |
|---|---|---|---|---|
| **Diagnostic Intervention** | Làm rõ vấn đề trước khi hành động | Tất cả problem types khi dữ liệu yếu | Survey review, interview, focus group, hypothesis table, root-cause map | Kéo dài phân tích, không chuyển thành hành động |
| **Organization Design Intervention** | Làm rõ structure, role, decision, governance | Org design, performance, change | Role clarity, RACI/RAPID, operating model, governance rhythm | Tái cấu trúc hình thức, không đổi hành vi |
| **Culture & Behavior Intervention** | Dịch giá trị thành hành vi và chuẩn vận hành | Culture, engagement, leadership, change | Behavior standards, leadership role modeling, rituals, recognition | Slogan hóa văn hóa, thiếu system reinforcement |
| **Leadership Alignment Intervention** | Tạo thống nhất ở leadership team | Culture, leadership, change, org design | Alignment workshop, decision principles, sponsor agreement, communication narrative | Workshop xong không có commitment/action |
| **Manager Capability Intervention** | Nâng năng lực quản lý con người và triển khai thay đổi | Leadership, engagement, performance, change | Manager training, coaching, conversation guide, practice loop | Training hóa vấn đề hệ thống |
| **Performance System Intervention** | Cải thiện goal, KPI/OKR, review, feedback, calibration | Performance, competency, leadership | Goal-setting, review process, calibration, feedback cadence | Tăng kiểm soát nhưng giảm trust nếu thiếu fairness |
| **Competency & Capability Intervention** | Xây năng lực phục vụ strategy và role | Competency, performance, leadership | Competency framework, skill gap, learning pathway, development plan | Framework quá nặng, không gắn việc thật |
| **Change Enablement Intervention** | Tăng readiness, adoption và sustainment | Change, culture, performance, org design | Change impact, stakeholder plan, communication, enablement, adoption metrics | Truyền thông một chiều, thiếu feedback loop |
| **Engagement & Employee Voice Intervention** | Cải thiện trải nghiệm, trust, voice và động lực | Engagement, culture, leadership | Pulse survey, listening sessions, manager action, recognition, workload review | Hỏi ý kiến nhưng không hành động |
| **Measurement & Learning Intervention** | Đo hiệu quả và điều chỉnh sau triển khai | Tất cả interventions | KPI/OKR, dashboard, review cadence, post-implementation review | Đo quá nhiều, không ra quyết định cải tiến |

## 5.1. Intervention Selection Logic

```text
1. Nếu problem chưa rõ → Diagnostic Intervention trước.
2. Nếu issue nằm ở role/decision/process → Organization Design Intervention.
3. Nếu issue nằm ở norms/behavior/trust → Culture & Behavior Intervention.
4. Nếu issue nằm ở manager behavior → Manager Capability + Leadership Alignment.
5. Nếu issue nằm ở goal/review/fairness → Performance System Intervention.
6. Nếu issue nằm ở năng lực → Competency & Capability Intervention.
7. Nếu issue nằm ở adoption/resistance → Change Enablement Intervention.
8. Nếu issue nằm ở voice/motivation/experience → Engagement & Employee Voice Intervention.
9. Mọi intervention nên có Measurement & Learning layer.
```

---

# 6. Boundary Map: Core / Adjacent / Out-of-scope

> Boundary Map giúp chatbot giữ đúng vai trò OD Advisor, không trôi sang HR chatbot tổng quát hoặc legal/clinical/individual judgment bot.

## 6.1. Core Domain

| Core area | Vì sao thuộc core | Ví dụ chatbot cần xử lý |
|---|---|---|
| OD fundamentals | Nền để giải thích và so sánh | OD là gì, khi nào dùng OD intervention |
| Organization diagnosis | Trọng tâm của cố vấn OD | Turnover tăng, engagement giảm, silo, manager resistance |
| Organization design | Vấn đề hệ thống trong tập đoàn | Role clarity, decision rights, operating model |
| Culture & engagement | OD core trong tập đoàn | Trust thấp, culture gap, employee voice |
| Leadership & manager capability | Đòn bẩy chính của OD | Manager yếu feedback, leadership không thống nhất |
| Performance & capability systems | Giao điểm giữa HR system và OD | PMS, KPI/OKR, competency framework |
| Change management / enablement | Gắn với rollout OD | Adoption, readiness, resistance |
| Intervention design | Năng lực tư vấn chính | Program design, OD roadmap, stakeholder plan |
| Measurement & improvement | Đảm bảo OD có learning loop | KPI, dashboard, review cadence, improvement plan |
| Validation & epistemic control | Tránh overclaim và khuyến nghị sai | Assumption, hypothesis, risk, confidence |

## 6.2. Adjacent Domain

| Adjacent area | Khi nào kéo vào | Giới hạn |
|---|---|---|
| HR policy | Khi giải pháp OD chạm policy cấp tổ chức | Không thay HR policy owner |
| Talent management | Khi competency, succession, career liên quan OD | Không mở rộng thành toàn bộ talent suite |
| Learning & Development | Khi can thiệp cần training/capability building | Không thiết kế khóa học quá chi tiết nếu không phải OD intervention |
| Workforce analytics | Khi cần đo lường hoặc đọc dữ liệu HR | Không làm BI/data engineering |
| Labor law / compliance | Khi có rủi ro pháp lý hoặc xử lý cá nhân | Chỉ nêu điểm cần Legal xác nhận |
| DEI / fairness | Khi liên quan công bằng, bias, voice | Không kết luận cáo buộc cá nhân |
| Internal communication | Khi cần communication plan cho change | Không trở thành chatbot PR/content thuần |
| Project management | Khi cần rollout plan | Không biến thành PMO bot tổng quát |
| Business strategy | Khi OD phải align với strategy | Không tư vấn chiến lược kinh doanh tổng thể |

## 6.3. Out-of-scope

| Out-of-scope area | Lý do loại trừ | Safe alternative |
|---|---|---|
| Tư vấn pháp lý lao động chuyên sâu | Cần luật sư/Legal | Checklist câu hỏi cho Legal |
| Quyết định sa thải/kỷ luật/cá nhân | Rủi ro pháp lý và đạo đức | Quy trình review công bằng, dữ kiện cần xác minh |
| Đánh giá năng lực/đạo đức/tính cách cá nhân cụ thể | Vi phạm No Individual Judgment | Khung tiêu chí trung lập |
| Xử lý dữ liệu nhân sự nhạy cảm chưa ẩn danh | Rủi ro privacy | Hướng dẫn ẩn danh dữ liệu |
| Coaching tâm lý / chẩn đoán tâm lý cá nhân | Không phải clinical tool | Gợi ý nguồn hỗ trợ phù hợp |
| Compensation & benefits design chi tiết | HR specialty khác, nhiều ràng buộc chính sách | Nêu điểm liên quan OD ở mức nguyên tắc |
| Payroll / HR admin / hợp đồng lao động | HR operations, không phải OD | Chuyển sang HR operations/Legal |
| Recruitment sourcing / interview scoring cá nhân | Talent acquisition, rủi ro đánh giá cá nhân | Khung competency hoặc interview structure chung |
| Employee relations investigation | Rủi ro pháp lý, cần quy trình chính thức | Escalation + neutral checklist |
| Business strategy consulting tổng thể | Ngoài phạm vi HR/OD Advisor | Chỉ kết nối OD implication với strategy đã có |

---

# 7. Mapping sang KB01–KB03

## 7.1. KB01 — OD Domain Map

KB01 nên lấy các phần sau làm nền:

- 1.1. OD Foundations & Enterprise Context
- 1.2. Organization System & Design
- 1.3. Culture, Engagement & Employee Experience
- 1.4. Performance & Capability Systems
- 1.5. Leadership & Manager Effectiveness
- 1.6. Change & Transformation
- Phần Problem Type Map ở mức taxonomy khái quát

## 7.2. KB02 — OD Diagnostic Frameworks

KB02 nên lấy các phần sau làm nền:

- 1.7. OD Diagnosis & Evidence Logic
- Problem Type Map
- Stakeholder tension patterns
- Functional Map phần Diagnose
- Boundary liên quan safety/diagnostic risks

## 7.3. KB03 — OD Intervention Playbook

KB03 nên lấy các phần sau làm nền:

- 1.8. OD Intervention Design
- Intervention Map
- Functional Map phần Design / Plan / Improve
- Measurement & Learning layer ở mức liên kết
- Boundary Map phần adjacent/out-of-scope để tránh khuyến nghị vượt phạm vi

---

# 8. Quality Check

## 8.1. MECE-ish Check

| Kiểm tra | Đánh giá |
|---|---|
| Cấp 1 của tree có đồng nhất không? | Có. Cấp 1 là các miền tri thức OD, không phải workflow/stakeholder/output. |
| Workflow có bị trộn vào tree không? | Không. Workflow được tách sang Functional Map. |
| Stakeholder có bị trộn vào problem type không? | Không. Stakeholder Map tách riêng. |
| Problem type có bị trùng intervention không? | Không. Problem Type = loại vấn đề; Intervention Map = nhóm can thiệp. |
| Boundary có rõ core/adjacent/out-of-scope không? | Có. Dùng để kiểm soát scope chatbot. |

## 8.2. Readiness for Architect Step

Artifact này đã đủ dùng để tiếp tục:

```text
Domain Decomposition Pack
→ KB01 OD Domain Map outline
→ KB02 Diagnostic Frameworks outline
→ KB03 Intervention Playbook outline
→ Output Schema / IA
→ Reasoning Pack
→ Safety & Validation Rules
```

## 8.3. Cảnh báo khi dùng pack này

- Không nên nạp nguyên pack này như KB runtime nếu chưa tinh gọn.
- Không nên biến tất cả node thành nội dung chi tiết trong MI.
- Không nên mở rộng sang HR operations, legal, payroll, recruitment hoặc employee relations investigation.
- Khi viết KB, mỗi node cần có ví dụ, boundary và output implication riêng.
