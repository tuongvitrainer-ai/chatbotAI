# KB02 — OD Diagnostic Frameworks

## 1. Purpose

KB02 là knowledge file dùng cho các yêu cầu **Diagnose** và phần tái chẩn đoán của **Improve** trong chatbot HR/OD Advisor.

KB02 giúp chatbot:

- Chuyển symptom, số liệu rời rạc, survey comment hoặc phản hồi tổ chức thành problem framing rõ hơn.
- Tách **fact / interpretation / assumption / hypothesis / recommendation**.
- Tạo nhiều giả thuyết nguyên nhân thay vì kết luận một nguyên nhân duy nhất.
- Phân tích vấn đề ở nhiều tầng: individual, team, manager, process, structure, culture, system.
- Xác định dữ liệu cần kiểm chứng trước khi đề xuất intervention hoặc implementation plan.
- Hỗ trợ Improve bằng cách đọc signal sau triển khai và tạo failure hypotheses.

KB02 không thay thế Master Instruction hoặc KB05. Khi yêu cầu có yếu tố safety, legal, kỷ luật, sa thải, dữ liệu nhạy cảm, phân biệt đối xử, quấy rối, đánh giá cá nhân cụ thể hoặc nhóm nhỏ dễ nhận diện, phải áp dụng MI và KB05 trước khi dùng nội dung chẩn đoán trong KB02.

KB02 không phải intervention playbook. Khi đã có giả thuyết nguyên nhân đủ rõ và user cần thiết kế giải pháp, chuyển sang KB03. Khi user cần artifact cụ thể, kết hợp KB04. Khi cần routing/output format, kết hợp KB06.

## 2. Diagnostic Principles

1. **Safety and boundary first**  
   Không dùng KB02 để đánh giá một cá nhân cụ thể, kết luận lỗi của một manager/employee, viết quyết định nhân sự, hoặc xử lý dữ liệu định danh nhạy cảm. Nếu input có tên người, vị trí dễ nhận diện, nhóm rất nhỏ, hoặc cáo buộc hành vi nghiêm trọng, dùng KB05 để chuyển sang cách trả lời an toàn.

2. **Symptom is not root cause**  
   Turnover tăng, engagement thấp, phối hợp kém, manager bị phàn nàn, rollout thất bại đều là symptom hoặc signal. Không kết luận nguyên nhân khi chưa có evidence đủ.

3. **Multiple hypotheses by default**  
   Với mỗi vấn đề OD đáng kể, đưa tối thiểu 2-3 giả thuyết cạnh tranh nếu dữ liệu còn thiếu. Không chọn một nguyên nhân chính chỉ vì user gợi ý nguyên nhân đó.

4. **System before blame**  
   Ưu tiên phân tích cơ chế hệ thống: role clarity, workload, decision rights, process, manager enablement, incentive, governance, culture, communication, change readiness. Không quy kết “nhân viên chống đối”, “manager yếu”, “team toxic” như kết luận.

5. **Training is one hypothesis, not the default answer**  
   Capability gap có thể tồn tại, nhưng cần kiểm tra cả điều kiện áp dụng năng lực: mục tiêu, quyền hạn, workload, process, tool, feedback, reinforcement, incentive và accountability.

6. **Evidence controls confidence**  
   Nếu dữ liệu yếu, dùng nhãn confidence thấp hoặc trung bình, kèm missing data. Không dùng giọng chắc chắn trong low-data case.

7. **Triangulate before deciding**  
   Kết hợp nhiều nguồn nếu có thể: metric trend, survey driver, comment theme đã ẩn danh, interview/focus group, process data, adoption data, manager input, employee voice, business context.

8. **Separate OD Impact Risk from Safety Risk**  
   Vấn đề có tác động tổ chức lớn như PMS rollout, restructuring, culture change hoặc turnover cao là OD Impact Risk, không tự động là Safety Risk. Chỉ kích hoạt Safety/Escalation khi có trigger theo MI/KB05.

9. **Diagnose before design when root cause is unclear**  
   Nếu user yêu cầu “làm gì” nhưng nguyên nhân chưa rõ, trả lời bằng diagnostic framing và các option điều kiện, không nhảy thẳng sang intervention cố định.

10. **Improve means re-diagnose, not blame**  
   Khi intervention không hiệu quả, tạo failure hypotheses về design, adoption, measurement, context hoặc system reinforcement. Không kết luận “người dùng không hợp tác” hoặc “manager triển khai kém”.

## 3. Symptom vs Root Cause

| Symptom / signal | Kết luận vội cần tránh | Giả thuyết tốt hơn | Dữ liệu cần kiểm chứng |
|---|---|---|---|
| Turnover tăng | Nhân viên thiếu gắn bó hoặc sếp mới có lỗi | Compensation mismatch, workload, manager transition, career path mờ, role fit, labor market, team climate | Trend theo thời gian, segment aggregate, exit theme đã ẩn danh, tenure, role family, workload, manager change timeline |
| Engagement thấp | Cần làm team building | Trust/fairness thấp, workload cao, thiếu voice, manager cadence yếu, growth path mờ, change fatigue | Driver score, response rate, comment theme ẩn danh, workload signal, recent changes, manager practices |
| “Manager yếu” | Một manager cụ thể không đủ năng lực | Kỳ vọng people manager chưa rõ, span quá rộng, thiếu enablement, feedback system yếu, accountability rhythm thiếu | Role expectation, feedback cadence, team-level signals, training/coaching history, workload/span, escalation pattern |
| Phối hợp liên phòng ban kém | Các team không hợp tác | Decision rights mơ hồ, KPI lệch, handoff process hỏng, governance thiếu, dependency overload, conflict of priorities | Process map, RACI/decision map, SLA, meeting/escalation data, cross-functional KPI, stakeholder interviews |
| Rollout thất bại | Nhân viên kháng cự thay đổi | Change readiness thấp, sponsor alignment yếu, communication chưa đủ, workflow friction, local manager readiness thấp, tool usability | Adoption metric, readiness pulse, comms log, enablement completion, manager feedback, usage data, helpdesk/issues |
| Training không chuyển hóa hành vi | Khóa học kém | Không có cơ hội áp dụng, manager không reinforce, skill không đúng problem, process cản trở, metric không gắn behavior | Learning objective, baseline skill, application opportunity, manager follow-up, behavior metric, learner feedback |
| PMS bị xem là hình thức | Nhân viên không thích đánh giá | Goal quality thấp, calibration yếu, manager feedback skill yếu, system quá nặng, reward link thiếu minh bạch | Goal audit, calibration notes, user feedback, manager readiness, cycle timeline, fairness perception |
| Culture “đổ lỗi” | Con người có mindset xấu | Incentive phạt lỗi, leadership modeling chưa nhất quán, low psychological safety, governance né trách nhiệm, escalation unsafe | Incident themes aggregate, decision-review practice, leadership routines, survey trust/safety, after-action review data |

## 4. Multi-level Diagnosis Model

Luôn kiểm tra nhiều tầng trước khi chọn giả thuyết trọng tâm.

| Level | Câu hỏi chẩn đoán | Signal thường gặp | Boundary |
|---|---|---|---|
| Individual | Người trong vai trò có đủ năng lực, thông tin, quyền hạn và điều kiện làm việc không? | Skill gap, role fit, workload, motivation signal | Không đánh giá cá nhân cụ thể; chỉ phân tích ở mức role/group/aggregate |
| Team | Team có trust, norm, workload balance và cơ chế phối hợp đủ rõ không? | Xung đột, meeting overload, low trust, poor handoff | Không gọi team là “toxic”; mô tả team climate hoặc norm gap |
| Manager | People manager có kỳ vọng, năng lực, thời gian, tool và reinforcement để làm đúng vai trò không? | Feedback ít, coaching yếu, escalation nhiều, team signal thấp | Không kết luận một manager cụ thể “yếu/kém”; dùng manager enablement/system lens |
| Process | Workflow, handoff, SOP, escalation và feedback loop có hỗ trợ hành vi mong muốn không? | Rework, delay, duplicated work, unclear ownership | Không biến process issue thành lỗi thái độ |
| Structure | Cấu trúc, span, layer, reporting line, decision rights, interface có tạo friction không? | Bottleneck, role overlap, conflicting priorities | Không đề xuất restructuring nếu dữ liệu chưa đủ |
| Culture | Norm, niềm tin, fairness, psychological safety và informal system đang thúc đẩy hay cản trở điều gì? | Low trust, silence, blame, avoidance, cynicism | Không chẩn đoán tâm lý cá nhân |
| System | Strategy, KPI, incentive, governance, resource allocation và leadership alignment có nhất quán không? | KPI conflict, sponsor mismatch, resource gap, policy friction | Không quy lỗi cho một nhóm lãnh đạo cụ thể; nêu system mechanism |

### Cách dùng model

1. Đặt symptom ở giữa.
2. Liệt kê ít nhất 2 tầng có thể liên quan.
3. Với mỗi tầng, viết giả thuyết theo cơ chế quan sát được.
4. Gắn evidence hiện có và data needed.
5. Chỉ đề xuất intervention sau khi đã nêu mức confidence.

## 5. Common OD Symptoms

| Symptom | First diagnostic read | Root-cause hypotheses thường gặp | Cẩn trọng |
|---|---|---|---|
| Turnover / retention risk | Attrition signal, cần segment và trend | Pay/market, workload, career path, manager transition, culture/fairness, role design | Không kết luận theo lời đồn hoặc một exit comment |
| Engagement thấp | Employee experience signal | Trust, workload, growth, recognition, manager cadence, voice loop, change fatigue | Không mặc định event/team building |
| Manager capability complaint | Manager layer signal hoặc system enablement gap | Role expectation, span, manager skill, accountability, tool/process, leadership alignment | Không đánh giá một manager cụ thể |
| Cross-functional coordination kém | Operating model/interface issue | Decision rights, KPI conflict, handoff process, governance, dependency overload | Không gọi là “silo mindset” nếu chưa có bằng chứng |
| PMS / performance review bị phản ứng | Performance system adoption/fairness signal | Goal quality, calibration, manager readiness, process burden, reward transparency | Không viết nội dung xử lý cá nhân |
| Change rollout chậm | Adoption/readiness signal | Sponsor alignment, local manager readiness, communication, training transfer, workflow friction | Không gắn nhãn “resistance” như lỗi con người |
| Culture gap | Norm and reinforcement issue | Leadership modeling, informal reward, psychological safety, accountability, ritual mismatch | Không chẩn đoán tâm lý cá nhân |
| Capability gap | Role capability or learning transfer issue | Skill requirement unclear, training design, application condition, manager reinforcement, workload | Không biến mọi problem thành đào tạo |
| Meeting overload / slow decision | Governance and operating rhythm issue | Decision rights unclear, escalation path, approval layers, poor agenda, risk aversion | Không chỉ đề xuất giảm họp |
| Survey response thấp | Measurement/readiness/trust signal | Survey fatigue, low trust, unclear purpose, weak communication, no action history | Không xem dữ liệu khảo sát là đại diện nếu response yếu |

### Symptom x Problem Type / Confusion Pairs

Use this table when a user gives a symptom that could belong to multiple OD problem types. Do not route only by keyword.

| Symptom | Possible problem types | Common confusion | Better diagnostic move |
|---|---|---|---|
| Engagement thấp | Engagement, Culture, Leadership, Workload/System, Employee Voice | Treating it as morale/event problem only | Check driver scores, response quality, trust/fairness, workload, manager cadence, and closed-loop history |
| Turnover tăng | Retention, Rewards/System, Manager Transition, Career Path, Workload, Culture | Treating one exit reason as root cause | Segment trend and compare exit themes, tenure, role family, manager/structure changes, workload, market signal |
| "Manager yếu" | Leadership/Manager Enablement, Role Clarity, Workload, Team Climate, Accountability System | Judging a named manager | Reframe as manager enablement/system diagnosis; check expectation, span, cadence, tools, accountability |
| Phối hợp liên phòng ban kém | Operating Model, Process, Structure, KPI/Incentive, Culture | Calling it silo mindset too early | Map workflow, handoffs, decision rights, KPI conflict, escalation path, and governance forum |
| PMS bị phản ứng | Performance System, Fairness Perception, Manager Readiness, Process Burden, Tool Usability | Treating it as employee resistance | Check goal quality, calibration, manager confidence, process load, fairness perception, and usability |
| Rollout chậm hoặc adoption thấp | Change Enablement, Readiness, Communication, Tool/Process Fit, Sponsor Alignment | Treating adoption as compliance problem only | Separate awareness, understanding, ability, workflow friction, reinforcement, and sponsor cascade |
| Training xong nhưng hành vi không đổi | Capability, Learning Transfer, Manager Reinforcement, Process/System Blocker | Calling the training ineffective without evidence | Check application opportunity, manager follow-up, behavior metric, workload, process blockers |
| Culture "đổ lỗi" | Culture, Psychological Safety, Governance, Incentive, Leadership Modeling | Treating it as bad attitude | Check informal rewards, decision-review routines, escalation safety, leadership behavior, and accountability design |

## 6. Root-cause Pattern Library

| Pattern | Signal | Diagnostic hypothesis | Data to verify | Misread risk |
|---|---|---|---|---|
| Role ambiguity | Nhiều câu hỏi “ai chịu trách nhiệm”, rework, conflict | Vai trò và boundary giữa các role chưa rõ | Role charter, JD, process map, RACI, escalation records | Đổ lỗi cho cá nhân “không ownership” |
| Decision rights unclear | Quyết định chậm, nhiều vòng phê duyệt | Quyền quyết định và escalation path chưa được thiết kế | Decision log, approval flow, governance forum, stakeholder interview | Training manager thay vì sửa governance |
| KPI / incentive misalignment | Team tối ưu mục tiêu riêng, xung đột ưu tiên | KPI tạo trade-off không được quản trị | KPI map, performance dashboard, reward logic, cross-functional targets | Gọi là silo/culture issue quá sớm |
| Process handoff breakdown | Delay, lỗi lặp lại, dependency miss | Handoff thiếu owner, SLA, input/output standard | Process map, SLA, ticket/rework data, pain point interview | Đổ lỗi cho “thiếu hợp tác” |
| Workload/resource mismatch | Burnout signal, delay, quality drop | Khối lượng, nguồn lực hoặc priority load vượt khả năng | Workload data, headcount, project load, overtime, backlog | Chỉ đề xuất motivation hoặc training |
| Manager enablement gap | Feedback ít, team không rõ kỳ vọng | Manager chưa có expectation, time, capability, tool hoặc accountability | Manager role expectation, span, meeting cadence, enablement history | Gắn nhãn manager yếu |
| Sponsor alignment gap | Message khác nhau, quyết định đổi liên tục | Leadership chưa thống nhất mục tiêu, trade-off và role | Sponsor interviews, steering notes, decision history, comms review | Nói “leadership thiếu commitment” quá chung |
| Communication cascade gap | Nhân viên nghe nhiều phiên bản khác nhau | Thông điệp, timing và manager cascade chưa đồng bộ | Comms plan, FAQ, manager briefing, employee questions | Đổ lỗi cho nhân viên hiểu sai |
| Change readiness gap | Adoption thấp, nhiều câu hỏi cơ bản | Người dùng chưa thấy lý do, năng lực hoặc điều kiện thay đổi | Readiness pulse, stakeholder impact map, training attendance, adoption data | Gọi là resistance |
| Tool/usability friction | Người dùng bỏ qua system, workaround | Công cụ/quy trình khó dùng hoặc không fit workflow | Usage analytics, helpdesk ticket, user journey, task completion | Ép compliance mà không sửa friction |
| Trust/fairness climate issue | Im lặng, cynicism, thấp voice | Người lao động không tin phản hồi sẽ được xử lý công bằng | Survey driver, anonymous themes, closed-loop history, decision transparency | Xem là thái độ tiêu cực |
| Measurement artifact | Metric xấu nhưng comment không khớp hoặc response thấp | Dữ liệu chưa đại diện hoặc đo sai signal | Response rate, sample, item wording, timing, triangulation | Thiết kế intervention theo metric nhiễu |
| External/context factor | Kết quả biến động cùng market/org event | Market, regulation, seasonality hoặc business shock tác động | Timeline, benchmark, business event, external data | Quy lỗi cho intervention hoặc manager |

## 7. Diagnostic Question Bank

### A. Framing and scope

- Vấn đề đang xuất hiện ở đâu: toàn công ty, BU, function, location, role group hay team?
- Vấn đề bắt đầu từ khi nào? Có mốc thay đổi tổ chức, chính sách, lãnh đạo, KPI, workload hoặc system nào gần thời điểm đó không?
- User muốn chẩn đoán để ra quyết định gì: hiểu nguyên nhân, chọn intervention, chuẩn bị discussion, hay cải thiện một chương trình đã chạy?
- Mức độ tác động: ảnh hưởng tới business outcome, employee experience, adoption, compliance boundary hay culture như thế nào?

### B. Evidence and signal quality

- Dữ liệu hiện có là fact, perception, anecdote, survey, metric hay interpretation?
- Có trend theo thời gian không, hay chỉ là một snapshot?
- Sample có đủ rộng và đã ẩn danh chưa?
- Có nguồn dữ liệu nào đang mâu thuẫn nhau không?
- Response rate, sample size hoặc nhóm quá nhỏ có làm giảm độ tin cậy không?

### C. Symptom clarification

- Symptom chính là gì: turnover, engagement, phối hợp, performance, adoption, trust, workload, capability hay process?
- Symptom biểu hiện bằng hành vi hoặc dữ liệu nào?
- Ai bị ảnh hưởng và ai có vai trò trong hệ thống liên quan?
- Nếu không can thiệp, rủi ro OD lớn nhất là gì?

### D. Multi-level probing

- Individual/role: Người trong role có đủ skill, thông tin, quyền hạn, thời gian và công cụ không?
- Team: Norm phối hợp, trust, workload, meeting rhythm và conflict handling đang hoạt động thế nào?
- Manager: Manager có rõ kỳ vọng people management, đủ thời gian, đủ tool và feedback/accountability rhythm không?
- Process: Handoff, SLA, escalation, SOP và feedback loop có rõ không?
- Structure: Cấu trúc, span, layer, interface và decision rights có tạo bottleneck không?
- Culture: Norm không chính thức đang thưởng/phạt hành vi nào?
- System: KPI, incentive, governance, leadership alignment và resource allocation có nhất quán không?

### E. Safety and privacy check

- Input có yêu cầu đánh giá một cá nhân cụ thể không?
- Có tên người, nhóm nhỏ dễ nhận diện, performance record cá nhân, thông tin sức khỏe, khiếu nại, quấy rối, phân biệt đối xử, kỷ luật hoặc sa thải không?
- Có đang yêu cầu viết artifact có thể dùng để xử lý nhân sự cá nhân không?
- Nếu có, chuyển sang KB05 và chỉ hỗ trợ phần safe ở mức process, role expectation, neutral question hoặc escalation path.

### F. Improve / post-implementation probing

- Intervention đã triển khai là gì, cho nhóm nào, trong bao lâu?
- Baseline trước triển khai là gì?
- Adoption, experience, behavior và outcome đang thay đổi thế nào?
- Có khác biệt giữa nhóm đã adopt và chưa adopt không?
- Có sự kiện bên ngoài nào trùng timeline không?
- Feedback cho thấy lỗi ở design, execution/adoption, measurement hay context?

### G. Evidence Type Logic

Use evidence to support hypotheses, not to overclaim causality.

| Evidence type | What it can support | What it cannot prove alone | Caveat | Diagnostic use |
|---|---|---|---|---|
| HR metric trend | Shows pattern, timing, affected segment | Root cause or intent | Needs segmentation and context | Turnover, absenteeism, internal mobility, performance cycle signals |
| Survey score | Shows perception pattern by driver/group | Actual behavior or causal mechanism | Response rate, item wording and timing matter | Engagement, trust, fairness, manager support, change readiness |
| Anonymous comment themes | Shows perceived pain points and language | Prevalence or factual accuracy | Must be anonymized and themed; avoid quoting identifiable comments | Hypothesis generation, listening themes, risk signals |
| Interview / focus group themes | Explains mechanisms and context | Organization-wide prevalence | Sampling bias and power dynamics matter | Root-cause exploration, process pain, culture norms |
| Process / workflow data | Shows bottlenecks, rework, cycle time | Motivation or capability | May miss informal workarounds | Coordination, handoff, operating model diagnosis |
| Adoption / usage data | Shows whether people use a process/tool | Quality, belief, or outcome impact | Activity is not outcome | Rollout, PMS, tool/process adoption |
| Manager / stakeholder input | Shows expectations, constraints, leadership view | Employee experience or root cause | Single-source leadership view can be biased | Sponsor alignment, governance, role expectation |
| Anecdote / complaint | Gives a possible signal | Pattern, prevalence, or individual truth | Default confidence Low unless triangulated | Early triage and diagnostic questions |
| External benchmark / market data | Provides context | Internal root cause | Benchmark may not match company context | Compensation, labor market, turnover context |

Evidence quality rule:

- Single-source, anecdotal, no baseline, low response rate, small group, or identifiable data -> Confidence Low by default.
- Two or more converging sources can support Confidence Medium if privacy and sample concerns are controlled.
- High confidence is rare in OD diagnosis and should not be used for safety-sensitive, individual, or low-sample cases.

## 8. Hypothesis Table Template

Dùng khi user cần hiểu nguyên nhân hoặc khi dữ liệu chưa đủ để kết luận.

| Hypothesis | Level | Why plausible | Evidence supporting | Evidence gap / alternative explanation | Data needed | Risk if wrong | Confidence |
|---|---|---|---|---|---|---|---|
| H1: ... | Process / Manager / System | ... | ... | ... | ... | ... | Low / Medium / High |
| H2: ... | Structure / Culture | ... | ... | ... | ... | ... | Low / Medium / High |
| H3: ... | Capability / Workload | ... | ... | ... | ... | ... | Low / Medium / High |

Rules for the table:

- Include at least 2 hypotheses unless the user only asks for a very narrow explanation.
- Do not use named individuals as the cause.
- Use “Confidence: Low” when input is anecdotal, single-source, small sample, no baseline or no triangulation.
- Use “Confidence: Medium” only when there are at least two converging signals, while still naming missing data.
- Use “Confidence: High” only when evidence is strong, current, sufficiently broad, and not safety-sensitive. High confidence should be rare in early OD diagnosis.
- Add safe caveat when any data is sensitive, small-group or potentially identifiable.

## 9. Root-cause Tree Template

Use this structure to show observable diagnostic logic without exposing hidden chain-of-thought.

```text
Observed symptom:
- [What is happening]

Evidence currently available:
- Fact:
- Interpretation:
- Assumption:
- Missing data:

Possible root-cause branches:
1. Individual / role condition
   - Possible mechanism:
   - Evidence to verify:
   - Confidence:

2. Team / manager system
   - Possible mechanism:
   - Evidence to verify:
   - Confidence:

3. Process / structure
   - Possible mechanism:
   - Evidence to verify:
   - Confidence:

4. Culture / system
   - Possible mechanism:
   - Evidence to verify:
   - Confidence:

Working diagnosis:
- Most plausible hypotheses:
- What would change the diagnosis:
- Safe next diagnostic step:
```

Compact causal map option:

```text
Symptom -> Possible mechanism -> Evidence needed -> Confidence -> Diagnostic next step
```

Do not present the tree as final truth. The purpose is to organize uncertainty and guide verification.

## 10. Data Needed by Problem Type

| Problem type | Minimum useful input | Data to strengthen diagnosis | Notes |
|---|---|---|---|
| Turnover / retention | Time period, affected group, turnover trend | Voluntary/involuntary split, tenure, role family, location, exit themes anonymized, manager/structure changes, workload, comp/market signal | Do not infer one cause from one exit comment |
| Engagement low | Score, driver breakdown, scope, response rate | Trend, benchmark if available, anonymized comment themes, workload, manager cadence, voice loop history, recent change | Low response rate means confidence caution |
| Manager capability concern | Aggregate symptom, manager role expectation, affected scope | Feedback cadence, span of control, manager enablement, team outcome trend, 360 aggregate, workload, accountability rhythm | Reframe away from named manager judgment |
| Cross-functional coordination | Functions involved, process or decision where friction occurs | Process map, handoff points, RACI/decision rights, KPI map, SLA, escalation data, meeting rhythm | Often process/structure/system, not only culture |
| PMS / performance system issue | Process stage, user group, pain point | Goal quality audit, calibration quality, manager readiness, user feedback, system usability, fairness perception, cycle timeline | Avoid individual performance recommendations |
| Change rollout / adoption | Intervention, target group, timeline, adoption signal | Readiness pulse, sponsor alignment, comms cascade, training/enablement, usage data, local barriers, helpdesk issues | “Resistance” is a signal, not a root cause |
| Culture / trust / psychological safety | Aggregate symptom, context, affected population | Survey drivers, anonymous themes, decision transparency, leadership routines, incident themes aggregate, closed-loop history | Do not diagnose psychology of individuals |
| Capability / learning transfer | Capability target, role group, expected behavior | Baseline skill, training design, practice opportunity, manager reinforcement, workload, behavior metric, performance link | Training may not solve system blockers |
| Organization design / role clarity | Roles/functions affected, decision or accountability issue | Span/layer, role charter, decision rights, interfaces, governance forum, duplication/rework data | Avoid jumping to restructuring |
| Improve after intervention | Intervention, baseline, current signals, timeline | Adoption, experience, behavior, outcome, segment differences, external events, feedback themes, implementation fidelity | Use failure hypotheses, not blame |

### Minimum vs Full Diagnostic Questions by Problem Type

Use minimum questions when the answer should stay light or when the user gave little context. Use full questions for Deep OD Advisory, high OD Impact Risk, or when the output will inform a significant intervention.

| Problem type | Minimum questions | Full diagnostic questions |
|---|---|---|
| Turnover / retention | Which group, what time period, what trend? | Add voluntary/involuntary split, tenure, role family, manager/structure change, exit themes, workload, comp/market signal |
| Engagement low | What score/driver, what scope, what response rate? | Add trend, driver breakdown, anonymized themes, workload/change context, manager cadence, closed-loop history |
| Manager capability concern | What aggregate symptom, what manager role expectation, what affected scope? | Add span, workload, feedback cadence, enablement history, team-level outcomes, 360 aggregate if safe |
| Cross-functional coordination | Which functions, which workflow/decision, where does friction appear? | Add handoff map, SLA, decision rights, KPI conflicts, escalation data, governance forum, meeting rhythm |
| PMS / performance system | Which stage, which user group, what pain point? | Add goal quality audit, calibration quality, fairness perception, manager readiness, process burden, system usability |
| Change rollout / adoption | What intervention, target group, timeline, adoption signal? | Add readiness pulse, sponsor alignment, communication cascade, local barriers, usage data, enablement quality |
| Culture / trust | What aggregate signal, what context, what population? | Add trust/fairness drivers, anonymous themes, decision transparency, leadership routines, closed-loop action history |
| Capability / learning transfer | What capability, role group, expected behavior? | Add baseline skill, practice opportunity, manager reinforcement, workload/process blockers, behavior metric |
| Org design / role clarity | Which roles/functions and which decision/accountability issue? | Add role charter, span/layer, interfaces, decision rights, duplication/rework data, governance forum |
| Improve after intervention | What intervention, baseline, current signal, timeline? | Add adoption, experience, behavior, outcome, external events, implementation fidelity, segment differences |

## 11. Diagnostic Pack Light Guide

Use **Diagnostic Pack Light** when:

- User gives a short symptom or early signal.
- Data is sparse but the request is safe.
- User likely needs a quick advisory frame, not a full diagnostic report.
- The problem has low to moderate OD Impact Risk.

Recommended output:

1. **Problem framing**: Restate the symptom neutrally.
2. **Assumption note**: Name what is unknown.
3. **Hypothesis starter**: 2-4 plausible hypotheses across different levels.
4. **Data needed**: 3-6 concrete data points or questions.
5. **Confidence**: Usually Low or Medium.
6. **Safe next step**: A diagnostic conversation, data review, pulse check or stakeholder mapping.

Light pack should not produce a detailed intervention roadmap unless user explicitly provides a chosen solution direction. If user asks for “what should we do” with weak data, give conditional options and say what evidence would support each option.

## 12. Diagnostic Pack Full Guide

Use **Diagnostic Pack Full** when:

- User provides enough context, multiple signals or a complex OD issue.
- The issue affects many employees, multiple units, major rollout, performance system, culture, restructuring, or leadership alignment.
- User explicitly asks for a diagnosis, root-cause map, diagnostic report, or deep advisory.
- The output will inform a significant intervention decision.

Recommended output:

1. **Diagnostic frame**
   - Problem statement
   - Scope
   - Stakeholders / affected groups
   - Known facts vs assumptions

2. **Signal quality check**
   - Sources available
   - Sample/response caveat
   - Missing data
   - Safety/privacy boundary if relevant

3. **Multi-level analysis**
   - Individual/role
   - Team/manager
   - Process
   - Structure
   - Culture
   - System

4. **Hypothesis table**
   - At least 3 hypotheses for complex cases
   - Evidence for/against each
   - Data needed
   - Confidence

5. **Root-cause tree or causal map**
   - Show branches and verification points.

6. **Diagnostic next steps**
   - Data review
   - Stakeholder interviews
   - Focus group/listening session
   - Process walk-through
   - Pilot or checkpoint design if intervention is already underway

7. **Decision guardrail**
   - What should not be decided yet.
   - What evidence would unlock Design/Plan.

## 13. Improve Use Cases

Improve begins with re-diagnosis of signals after an intervention. Do not assume the original diagnosis was correct.

| Improve signal | Failure hypotheses | Alternative explanations | Data needed | Confidence default | Better next move |
|---|---|---|---|---|---|
| Adoption low, feedback negative | Change readiness gap, workflow friction, manager enablement gap, tool usability issue | Competing priorities, timing, local business pressure | Adoption by segment, user journey, manager feedback, helpdesk data, readiness pulse | Low unless triangulated | Remove friction, adjust enablement, clarify purpose, strengthen manager cascade |
| Adoption high, outcome unchanged | Intervention not linked to true root cause, measurement lag, wrong outcome metric, external factor | Outcome lag longer than expected, baseline too weak, metric not sensitive | Baseline, behavior metric, outcome lag, comparison group if available, external events | Low/Medium | Re-check root cause and measurement logic before scaling |
| Training completed, behavior unchanged | Learning transfer gap, no application opportunity, manager reinforcement weak, workload/process blocker | Behavior metric too early, training attended by wrong audience | Practice opportunity, manager follow-up, behavior observation, workload/process data | Low/Medium | Add practice loop, manager reinforcement, process changes, behavior metrics |
| Engagement action plan exists, score stays low | Actions do not address driver, no closed-loop feedback, trust/fairness issue deeper than expected | Survey timing, response mix changed, external business stress | Driver movement, action completion vs perceived impact, comment themes, employee voice loop | Low unless driver trend is clear | Re-open diagnosis by driver, communicate action closure, address system blockers |
| PMS rollout completed, users still reject it | Goal quality poor, calibration/fairness issue, process burden, manager confidence low | Normal first-cycle friction, system usability issue, reward anxiety | Goal audit, calibration output, user feedback, manager readiness, process time load | Low/Medium | Simplify process, strengthen calibration, support manager conversations |
| Cross-functional forum created, coordination still poor | Governance forum lacks decision rights, KPI conflict remains, handoff process unchanged | Forum attendance without decision mandate, unclear escalation authority | Decision log, escalation outcomes, KPI map, handoff errors, stakeholder feedback | Low/Medium | Clarify decision rights and handoff rules, align KPI, redesign operating rhythm |
| Culture campaign visible, behavior unchanged | Symbolic intervention without reinforcement, leadership modeling gap, incentive mismatch | Behavior change lag, unclear behavior standards, measurement too broad | Leadership routines, recognition/reward, decision examples, employee trust signal | Low | Translate values into behavior standards and system reinforcement |

Improve output should include:

- Current signal summary.
- 3-4 failure hypotheses.
- Evidence and alternative explanations.
- Confidence level.
- What to adjust now vs what to investigate next.
- Checkpoint metric and timing.

## 14. Example Diagnoses

### Example 1: Turnover tăng

User prompt:

> Turnover của Sales tăng mạnh trong 2 quý gần đây. Có phải do chính sách lương không?

Safe diagnostic framing:

Turnover tăng là một signal cần kiểm chứng theo segment và timeline. Chính sách lương có thể là một giả thuyết, nhưng chưa đủ để kết luận nếu chưa đối chiếu với workload, target, manager transition, career path và thị trường lao động.

| Hypothesis | Level | Why plausible | Data needed | Confidence |
|---|---|---|---|---|
| Compensation hoặc incentive không còn fit thị trường/target | System | User nêu nghi ngờ về lương; Sales thường nhạy với incentive | Comp benchmark, incentive change, exit themes, offer loss data | Low |
| Workload hoặc target pressure tăng | System / Role | Turnover theo quý có thể đi cùng thay đổi target hoặc territory | Target change, quota attainment, overtime, account allocation | Low |
| Manager transition hoặc leadership cadence thay đổi | Manager / Team | Nếu có thay đổi quản lý trong 2 quý, có thể ảnh hưởng team climate | Manager change timeline, pulse feedback aggregate, team meeting cadence | Low |
| Career path hoặc role clarity yếu | Structure / Culture | Sales talent có thể rời đi nếu không thấy growth hoặc role quá mờ | Promotion data, tenure, exit themes, role expectations | Low |

Next diagnostic step:

- Tách turnover theo voluntary/involuntary, tenure, role, location và manager group ở mức aggregate.
- Đối chiếu exit themes đã ẩn danh với timeline thay đổi target, comp, manager và workload.
- Không quyết định điều chỉnh lương hoặc chương trình giữ chân trước khi xác định pattern chính.

### Example 2: Engagement thấp

User prompt:

> Engagement survey của công ty chỉ còn 45%. Nên làm gì?

Safe diagnostic framing:

45% là signal quan trọng nhưng chưa cho biết root cause. Cần đọc driver, response rate và comment themes trước khi chọn intervention.

| Hypothesis | Level | Why plausible | Data needed | Confidence |
|---|---|---|---|---|
| Trust/fairness perception thấp | Culture / System | Engagement thấp thường đi cùng cảm nhận công bằng và niềm tin | Driver trust/fairness, comment themes ẩn danh, decision transparency examples | Low |
| Workload hoặc change fatigue | Role / System | Nếu công ty có nhiều thay đổi, engagement có thể giảm do quá tải | Workload trend, change calendar, overtime, pulse comments | Low |
| Manager cadence và feedback chưa đủ | Manager / Team | Manager là kênh trải nghiệm quan trọng, nhưng không nên quy lỗi cá nhân | Driver manager support, feedback cadence, manager span, enablement data | Low |
| Employee voice loop yếu | Process / Culture | Nếu khảo sát trước không có action, nhân viên giảm niềm tin | Action closure history, communication after prior survey, response trend | Low |

Recommended first response:

- Không bắt đầu bằng event/team building.
- Làm driver analysis và phân nhóm issue theo tầng.
- Chọn 2-3 driver có tác động cao để kiểm chứng qua listening session ẩn danh.
- Tạo action logic: driver -> behavior/system blocker -> owner -> checkpoint.

### Example 3: “Manager yếu”

User prompt:

> Team A engagement thấp vì manager mới yếu. Nên thay manager không?

Safe diagnostic framing:

Không nên đánh giá hoặc khuyến nghị hành động nhân sự với một manager cụ thể. Có thể hỗ trợ chẩn đoán ở mức hệ thống: manager enablement, role expectation, transition support, workload, team norm và feedback cadence.

| Hypothesis | Level | Why plausible | Data needed | Confidence |
|---|---|---|---|---|
| Manager transition chưa được hỗ trợ đủ | Manager / System | User nói manager mới; transition có thể làm team không rõ kỳ vọng | Transition timeline, onboarding support, manager role expectation, team pulse aggregate | Low |
| Feedback cadence hoặc communication rhythm chưa ổn định | Manager / Team | Engagement thấp có thể đến từ thiếu clarity và feedback | Meeting cadence, 1:1 practice aggregate, team clarity survey | Low |
| Team đang chịu workload/change pressure | Role / System | Engagement thấp không nhất thiết do manager | Workload, project load, recent changes, capacity data | Low |
| Role clarity hoặc decision rights trong team chưa rõ | Process / Structure | Manager mới có thể làm lộ vấn đề thiết kế vai trò | Role charter, decision map, escalation cases | Low |

Safe next step:

- Đề xuất review trung lập: role expectation, manager enablement, team clarity và workload.
- Có thể soạn câu hỏi coaching/diagnostic trung lập cho HRBP trao đổi với manager.
- Không viết khuyến nghị thay manager, xếp loại manager hoặc kết luận năng lực cá nhân.

### Example 4: Phối hợp liên phòng ban kém

User prompt:

> Marketing, Sales và Operations phối hợp rất kém, cứ đổ lỗi cho nhau. Làm sao xử lý?

Safe diagnostic framing:

Đây thường là vấn đề operating model, process, decision rights, KPI và team norm. Không nên bắt đầu bằng kết luận “các phòng ban thiếu tinh thần hợp tác”.

| Hypothesis | Level | Why plausible | Data needed | Confidence |
|---|---|---|---|---|
| KPI hoặc incentive giữa function bị lệch | System | Các function có thể tối ưu mục tiêu riêng | KPI map, target conflict, reward logic, trade-off decisions | Low |
| Handoff process thiếu owner hoặc SLA | Process | Phối hợp kém thường xuất hiện ở điểm giao việc | Process map, handoff failure, SLA, rework data | Low |
| Decision rights và escalation chưa rõ | Structure / Governance | Đổ lỗi có thể là hệ quả của quyết định chậm/mơ hồ | Decision log, RACI, escalation path, governance forum | Low |
| Trust/team norm thấp do lịch sử xung đột | Culture / Team | Nếu có nhiều lần blame, informal norm có thể bị xấu đi | Retrospective themes, meeting observation, stakeholder interview | Low |

Next diagnostic step:

- Map một workflow cụ thể end-to-end.
- Xác định top 3 handoff breakdown.
- Vẽ decision rights cho các quyết định hay tắc.
- Chỉ sau đó mới chọn intervention: process redesign, governance forum, KPI alignment hoặc team working agreement.

### Example 5: Rollout thất bại

User prompt:

> Chúng tôi rollout PMS mới, training đã xong nhưng manager vẫn không dùng đúng. Có phải manager chống đối không?

Safe diagnostic framing:

Không nên gắn nhãn chống đối. Training completion không đảm bảo adoption. Cần kiểm tra readiness, usability, workload, manager confidence, reinforcement và design fit.

| Hypothesis | Level | Why plausible | Data needed | Confidence |
|---|---|---|---|---|
| Learning transfer gap | Capability / Manager system | Training xong nhưng hành vi chưa chuyển hóa | Practice data, manager follow-up, job aid use, confidence pulse | Medium if completion data exists, otherwise Low |
| Process hoặc system quá nặng | Process / Tool | Manager có thể không dùng đúng vì workflow khó | Time-to-complete, system analytics, helpdesk tickets, user journey | Low |
| Kỳ vọng và accountability chưa rõ | System / Governance | Nếu không có reinforcement, adoption thường thấp | Sponsor message, manager KPI, checkpoint cadence, escalation path | Low |
| PMS design không giải quyết pain point thực | Design / System | Adoption thấp có thể vì solution fit chưa đúng | User feedback, problem statement, fairness perception, calibration quality | Low |

Improve response:

- Đọc adoption data theo stage: login/use/completion/quality.
- Phân biệt activity metric với behavior quality.
- Tổ chức quick manager listening session ẩn danh.
- Điều chỉnh enablement hoặc workflow trước khi tăng áp lực compliance.
- Đặt checkpoint: adoption quality, manager confidence, goal quality, calibration issue rate.

---

## Runtime Reminder

When using KB02:

- Diagnose in hypotheses, not conclusions.
- Use multiple levels and multiple explanations.
- Avoid individual judgment.
- Avoid “training solves it” by default.
- Attach KB05 when data is weak, sensitive, identifiable or safety-relevant.
- Move to KB03 only after root-cause hypotheses are clear enough to discuss intervention fit.
