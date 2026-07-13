# Safety & Validation Requirement Extraction — HR/OD Advisor

*Source: BRD2.md*

## 1. Safety Requirements Extracted from BRD

| Requirement                                                                                                                                   | BRD source section hoặc nội dung BRD liên quan                                                                                                                                                                                                                             | Meaning                                                                                  | Why it matters                                                                                                | Placement                                                                 |
| --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| **Safety Risk Check phải là bước đầu tiên**                                                                                                   | Runtime Flow Logic đặt **Step 1 — Safety Risk Check** trước routing, complexity check, KB selection và output selection.                                                                                                                                                   | Trước khi hiểu intent hay tạo output, chatbot phải kiểm tra rủi ro safety.               | Nếu không kiểm tra trước, chatbot có thể tạo artifact unsafe như email kỷ luật/sa thải hoặc đánh giá cá nhân. | **Master Instruction**, KB05, KB06, Test Scenario Set                     |
| **Safety Risk override các flow khác**                                                                                                        | Flow Priority Rule: Safety/Escalation Flow đứng ưu tiên số 1 nếu có Safety Risk; Validation chỉ là module, không tự động biến thành Deep Flow.                                                                                                                             | Safety không phải một nhánh tùy chọn; nó là override runtime.                            | Ngăn chatbot tiếp tục Standard/Deep advisory khi case có pháp lý, dữ liệu nhạy cảm hoặc quyết định cá nhân.   | **Master Instruction**, KB05, KB06                                        |
| **Phân biệt 3 loại risk: Safety Risk / OD Impact Risk / Uncertainty Risk**                                                                    | Risk Taxonomy nêu 3 loại risk, ví dụ, và ảnh hưởng đến flow; BRD nhấn mạnh không gọi chung “high-risk”.                                                                                                                                                                    | Risk không được gom chung. Safety Risk khác OD Impact Risk và khác Uncertainty Risk.     | Nếu nhầm risk, chatbot có thể escalate quá mức hoặc ngược lại xử lý safety case như advisory bình thường.     | **Master Instruction**, KB05, KB06, Evaluation Rubric                     |
| **Safety/Escalation Trigger**                                                                                                                 | BRD liệt kê trigger: sa thải, kỷ luật, điều chuyển cá nhân, thăng chức/xếp loại cá nhân, đánh giá cá nhân, dữ liệu nhạy cảm/chưa ẩn danh, pháp lý/tuân thủ, phân biệt đối xử, khiếu nại/tố cáo/quấy rối, nội dung làm căn cứ xử lý cá nhân, quyết định nhân sự rủi ro cao. | Các trigger này phải chuyển sang Safety/Escalation Flow.                                 | Đây là vùng rủi ro pháp lý, đạo đức, privacy và fairness cao.                                                 | **Master Instruction**, KB05, Test Scenario Set                           |
| **RULE-SAFETY-001 — No Individual Judgment**                                                                                                  | BRD cấm kết luận cá nhân phù hợp/không phù hợp, xếp loại cá nhân, đánh giá đạo đức/tính cách/năng lực/tâm lý, hoặc viết nội dung quy kết cá nhân làm căn cứ xử lý.                                                                                                         | Chatbot không được đánh giá người cụ thể.                                                | HR/OD Advisor phải tư vấn ở cấp hệ thống/quy trình/tiêu chí, không đưa phán quyết cá nhân.                    | **Master Instruction**, KB05, Test Scenario Set, Evaluation Rubric        |
| **Không tạo văn bản có thể dùng trực tiếp như quyết định xử lý cá nhân**                                                                      | Out-of-scope và Guardrails đều nêu không viết văn bản có thể dùng như quyết định xử lý cá nhân.                                                                                                                                                                            | Chatbot không được tạo email/quyết định kỷ luật, sa thải, điều chuyển, xếp loại cá nhân. | Tránh tạo artifact có thể gây hậu quả pháp lý hoặc quyết định nhân sự sai quy trình.                          | **Master Instruction**, KB05, KB04 safe artifacts, Test Scenario Set      |
| **Safe support vẫn được phép**                                                                                                                | Safe Support Boundary cho phép khung đánh giá, tiêu chí cần tổ chức phê duyệt, checklist dữ kiện, câu hỏi xác minh, quy trình review công bằng, mẫu trao đổi trung lập, hướng dẫn ẩn danh dữ liệu, điểm cần HR/Legal/Leadership xác nhận.                                  | Không phải từ chối toàn bộ; chatbot chuyển sang hỗ trợ an toàn.                          | Giữ usefulness nhưng không vượt safety boundary.                                                              | KB05, KB04 safe alternative artifacts, KB06 output routing                |
| **Mixed Intent Severity Rule**                                                                                                                | BRD phân High/Medium/Low Safety Risk; high safety dùng một Safety/Escalation response duy nhất, không làm phần unsafe; phần safe chỉ nằm trong Optional Safe Artifact.                                                                                                     | Khi user hỏi lẫn phần unsafe và safe, chatbot phải tách mức độ rủi ro.                   | Ngăn chatbot “lách” bằng cách làm phần unsafe trước rồi thêm caveat.                                          | **Master Instruction**, KB05, KB06, Test Scenario Set                     |
| **Sensitive HR data phải được ẩn danh trước khi xử lý**                                                                                       | Out-of-scope nêu không xử lý dữ liệu nhân sự nhạy cảm khi chưa ẩn danh; safe boundary cho phép gợi ý cách ẩn danh dữ liệu.                                                                                                                                                 | Không phân tích dữ liệu cá nhân/sensitive raw data.                                      | Bảo vệ privacy, giảm rủi ro nhận diện cá nhân hoặc nhóm nhỏ.                                                  | **Master Instruction**, KB05, KB04 safe data checklist, Test Scenario Set |
| **Không thay thế HR Director, Legal, Leadership hoặc consultant trong case rủi ro cao**                                                       | Out-of-scope nêu chatbot không thay thế HR Director, Legal, Leadership hoặc chuyên gia tư vấn trong tình huống rủi ro cao.                                                                                                                                                 | Chatbot chỉ là advisor có cấu trúc, không có quyền quyết định/hành động chính thức.      | Tránh decision-rights overreach.                                                                              | **Master Instruction**, KB05, Evaluation Rubric                           |
| **Legal / compliance boundary**                                                                                                               | Out-of-scope cấm tư vấn pháp lý lao động chuyên sâu thay Legal/luật sư; Safety/Escalation trigger có pháp lý/tuân thủ.                                                                                                                                                     | Chatbot không được đóng vai cố vấn pháp lý.                                              | Domain HR/OD dễ đụng luật lao động, ER, khiếu nại, kỷ luật.                                                   | **Master Instruction**, KB05, Test Scenario Set                           |
| **Validation là module, không phải flow độc lập**                                                                                             | Core Runtime Principle và Flow Priority Rule đều nêu Validation là module, có thể gắn vào Standard hoặc Deep Flow, không tự động biến thành Deep Flow.                                                                                                                     | Validation không phải tuyến xử lý riêng ngang Safety/Standard/Deep.                      | Tránh mọi câu hỏi bị kéo thành audit dài; giữ chatbot hữu dụng.                                               | KB06, KB05                                                                |
| **Validation trigger khi dữ liệu thiếu, nhiều giả thuyết, OD impact, hoặc user yêu cầu review/risk**                                          | BRD nêu validation kích hoạt khi dữ liệu thiếu nhưng vẫn cần khuyến nghị, nhiều giả thuyết nguyên nhân, ảnh hưởng nhiều nhóm/đơn vị, OD Impact Risk, hoặc user hỏi phản biện/review/risk/thiếu gì.                                                                         | Validation dùng để kiểm tra assumption, risk, gap và confidence.                         | Ngăn overclaim và giúp user kiểm định trước khi hành động.                                                    | KB05, KB06, Evaluation Rubric                                             |
| **Validation actions gồm epistemic breakdown, Assumption Note, Hypothesis Table, Risk Matrix, Gap Analysis, Confidence Label, Revision Memo** | Validation Actions table liệt kê các thành phần validation và khi nào dùng.                                                                                                                                                                                                | Đây là bộ artifact validation cần chuyển thành KB05/KB06 output patterns.                | Nếu không chuẩn hóa, chatbot sẽ “review” chung chung hoặc chỉ sửa câu chữ.                                    | KB05, KB06, Evaluation Rubric                                             |
| **Không dùng High Confidence khi dữ liệu yếu, cá nhân nhạy cảm hoặc safety-sensitive**                                                        | Guardrails nêu không dùng High confidence khi dữ liệu yếu, cá nhân nhạy cảm hoặc safety-sensitive.                                                                                                                                                                         | Confidence phải phản ánh độ chắc của dữ liệu và rủi ro.                                  | Tránh chatbot tạo cảm giác chắc chắn giả trong HR risk case.                                                  | **Master Instruction**, KB05, Evaluation Rubric                           |
| **Final Output Check để hạn chế overclaim, thiếu assumption hoặc vi phạm guardrails**                                                         | Success Criteria yêu cầu Final Output Check để hạn chế overclaim, thiếu assumption hoặc vi phạm guardrails.                                                                                                                                                                | Trước khi trả lời, chatbot phải tự kiểm output.                                          | Giảm lỗi runtime của Custom GPT khi model không luôn theo workflow.                                           | KB06, Master Instruction, Evaluation Rubric                               |
| **Safety hard rules phải nằm trong Master Instruction**                                                                                       | Custom GPT constraints nêu safety phải nằm trong Master Instruction, hard rules không chỉ để trong KB.                                                                                                                                                                     | MI là tầng ưu tiên cao nhất cho safety.                                                  | Nếu chỉ để KB, model có thể bỏ qua khi retrieval không ổn định.                                               | **Master Instruction**                                                    |
| **KB05 là nơi chứa Validation & Safety Rules**                                                                                                | KB05 gồm Safety/Escalation Trigger, No Individual Judgment, Mixed Intent Severity, Epistemic Validation, Risk & Assumption Check, Sensitive HR data handling, Safety response examples.                                                                                    | KB05 là nơi mở rộng rule bằng ví dụ, checklist, safe alternatives.                       | Tránh nhồi toàn bộ safety examples vào MI.                                                                    | KB05                                                                      |
| **KB06 là nơi chứa routing/output/depth**                                                                                                     | KB06 gồm task detection, intent/input/desired output router, flow selection, KB selection, output templates, depth rules, good/bad examples.                                                                                                                               | KB06 quyết định dùng flow, KB và output structure nào.                                   | Nếu KB06 yếu, safety/validation có thể không được kích hoạt đúng lúc.                                         | KB06                                                                      |
| **MI–KB priority: MI cao nhất, KB05/KB06 không được trái MI**                                                                                 | BRD nêu Master Instruction là nguồn luật ưu tiên cao nhất; KB05/KB06 chỉ mở rộng bằng ví dụ/checklist/output pattern/routing examples/safety examples.                                                                                                                     | Rule cứng nằm ở MI; KB triển khai rule.                                                  | Tránh mâu thuẫn giữa MI và KB khi runtime.                                                                    | **Master Instruction**, KB05, KB06                                        |
| **Test Scenario Set và Evaluation Rubric không nên nạp runtime**                                                                              | BRD khuyến nghị Test Scenario Set và Evaluation Rubric dùng để test/chấm, không nạp runtime.                                                                                                                                                                               | Test là công cụ kiểm tra chatbot, không phải knowledge runtime.                          | Tránh chatbot học theo test hoặc trả lời kiểu “đang được chấm”.                                               | Test Scenario Set, Evaluation Rubric                                      |
| **Môi trường doanh nghiệp rủi ro cao cần bổ sung sau MVP**                                                                                    | BRD nêu cần red-team test định kỳ, human review cho case nhạy cảm, hướng dẫn ẩn danh dữ liệu, disclaimer nội bộ, logging/audit nếu enterprise, retrieval control nếu backend RAG, evaluation pipeline.                                                                     | Custom GPT MVP chưa đủ cho enterprise high-risk deployment.                              | Nếu triển khai doanh nghiệp thật mà không có lớp kiểm soát ngoài GPT, rủi ro tăng.                            | Post-MVP Roadmap, Evaluation Rubric, Governance Note                      |

---

## 2. Core Safety Themes

| Theme                                        | Risk addressed                       | Expected chatbot behavior                                                                                                                          | Related BRD rule                                          |
| -------------------------------------------- | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **1. Safety before usefulness**              | Safety Risk                          | Kiểm tra safety trước mọi routing/task/output; nếu có Safety Risk, chuyển Safety/Escalation Flow.                                                  | Step 1 Safety Risk Check; Flow Priority Rule; Guardrails. |
| **2. No individual judgment**                | Safety Risk                          | Không kết luận, xếp loại, đánh giá năng lực/đạo đức/tính cách/tâm lý/hành vi cá nhân cụ thể.                                                       | RULE-SAFETY-001.                                          |
| **3. No direct personnel decision artifact** | Safety Risk                          | Không viết email/quyết định/văn bản có thể dùng làm căn cứ xử lý cá nhân.                                                                          | Out-of-scope + Guardrails.                                |
| **4. Legal / compliance boundary**           | Safety Risk                          | Không tư vấn pháp lý lao động chuyên sâu; nêu điểm cần HR/Legal xác nhận.                                                                          | Out-of-scope + Safety trigger pháp lý/tuân thủ.           |
| **5. Sensitive data handling**               | Safety Risk                          | Không xử lý dữ liệu nhân sự nhạy cảm chưa ẩn danh; chỉ gợi ý cách ẩn danh dữ liệu.                                                                 | Out-of-scope + Safe Support Boundary.                     |
| **6. Safe alternative support**              | Safety Risk                          | Thay vì làm phần unsafe, cung cấp checklist, tiêu chí, câu hỏi xác minh, quy trình trung lập, mẫu trao đổi trung lập.                              | Safe Support Boundary + Mixed Intent rule.                |
| **7. Risk taxonomy separation**              | Safety / OD Impact / Uncertainty     | Phân biệt Safety Risk, OD Impact Risk, Uncertainty Risk; không gọi chung là high-risk.                                                             | Risk Taxonomy.                                            |
| **8. Epistemic validation**                  | Uncertainty Risk                     | Tách Fact / Interpretation / Assumption / Hypothesis / Recommendation; dùng Assumption Note, Hypothesis Table, Confidence Label khi thiếu dữ liệu. | Problem Statement + Validation Actions.                   |
| **9. OD impact validation**                  | OD Impact Risk                       | Với giải pháp ảnh hưởng nhiều nhóm/đơn vị hoặc có rủi ro văn hóa/niềm tin/vận hành/công bằng, kích hoạt Validation Module.                         | Validation triggers.                                      |
| **10. Final output check**                   | Safety / Validation / Output quality | Kiểm tra overclaim, assumption, confidence và guardrails trước khi trả lời.                                                                        | Success Criteria + Runtime Flow Step 8.                   |

---

## 3. Safety vs Validation Separation

| Item                                                              | Is it Safety, Validation, or Both?                                | Why                                                                                             | Runtime implication                                                                         |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Sa thải, kỷ luật, điều chuyển cá nhân                             | **Safety**                                                        | Liên quan trực tiếp đến quyết định cá nhân và rủi ro pháp lý.                                   | Safety/Escalation override; không tạo quyết định/email xử lý cá nhân.                       |
| Thăng chức/xếp loại cá nhân                                       | **Safety**                                                        | Là quyết định cá nhân có tác động nghề nghiệp.                                                  | Không xếp loại/khuyến nghị cá nhân; chỉ cung cấp tiêu chí và quy trình review.              |
| Đánh giá năng lực/đạo đức/tính cách/tâm lý/hành vi cá nhân cụ thể | **Safety**                                                        | Vi phạm No Individual Judgment.                                                                 | Chuyển sang khung tiêu chí, dữ kiện cần xác minh, quy trình công bằng.                      |
| Dữ liệu nhân sự nhạy cảm/chưa ẩn danh                             | **Safety**                                                        | Rủi ro privacy và nhận diện cá nhân.                                                            | Không xử lý trực tiếp; hướng dẫn ẩn danh và aggregation.                                    |
| Pháp lý/tuân thủ/khiếu nại/tố cáo/quấy rối/phân biệt đối xử       | **Safety**                                                        | Có thể cần quy trình chính thức và HR/Legal.                                                    | Safety/Escalation Flow; nêu điểm cần HR/Legal/Leadership xác nhận.                          |
| Case có nhiều giả thuyết nguyên nhân                              | **Validation**                                                    | Chủ yếu là Uncertainty Risk, không tự động safety.                                              | Dùng Hypothesis Table, Assumption Note, Confidence Label.                                   |
| Dữ liệu thiếu nhưng user vẫn cần khuyến nghị                      | **Validation**                                                    | Không nhất thiết unsafe, nhưng dễ overclaim.                                                    | Tiếp tục với assumption rõ và confidence phù hợp.                                           |
| Giải pháp ảnh hưởng nhiều nhóm/đơn vị                             | **Validation**                                                    | OD Impact Risk về vận hành, văn hóa, niềm tin, công bằng.                                       | Gắn Risk Matrix/GAP Analysis; không tự động Safety nếu không có trigger cá nhân/pháp lý.    |
| Rollout PMS, thay đổi văn hóa, tái cấu trúc toàn tập đoàn         | **Validation, có thể Safety nếu chạm quyết định cá nhân/pháp lý** | BRD xếp đây là OD Impact Risk; chỉ thành Safety nếu liên quan pháp lý/cá nhân/dữ liệu nhạy cảm. | Deep OD Advisory hoặc Validation Module; nếu có trigger safety thì Safety override.         |
| Không dùng High Confidence khi dữ liệu yếu/safety-sensitive       | **Both**                                                          | Vừa kiểm soát epistemic risk, vừa giảm rủi ro trong case nhạy cảm.                              | Confidence Label bắt buộc; High Confidence bị chặn trong case yếu/nhạy cảm.                 |
| Final Output Check                                                | **Both**                                                          | Kiểm soát overclaim, thiếu assumption và vi phạm guardrails.                                    | Step trước Final Answer; dùng trong KB06 và MI.                                             |
| Mixed intent có phần unsafe và phần safe                          | **Both**                                                          | Cần safety override và routing output an toàn.                                                  | High Safety Risk → một Safety/Escalation response; phần safe chỉ là optional safe artifact. |
| Validation Module                                                 | **Validation**                                                    | BRD nói validation là module, không phải flow độc lập.                                          | Gắn vào Standard/Deep Flow khi trigger xuất hiện, không tự động deep-flow.                  |

---

## 4. Initial Gap Check

### 4.1. BRD đã nói rõ phần nào?

| Area                             | Status | Evidence from BRD                                                                                                                                                                                                     | Implication                                                   |
| -------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Safety trigger list**          | Rõ     | BRD liệt kê đầy đủ trigger liên quan sa thải, kỷ luật, điều chuyển, thăng chức/xếp loại, đánh giá cá nhân, dữ liệu nhạy cảm, pháp lý, phân biệt đối xử, khiếu nại/tố cáo/quấy rối, nội dung làm căn cứ xử lý cá nhân. | Có thể đưa trực tiếp vào MI + KB05.                           |
| **No Individual Judgment**       | Rõ     | RULE-SAFETY-001 cấm kết luận/xếp loại/đánh giá cá nhân và cho phép checklist/tiêu chí/quy trình/mẫu trung lập.                                                                                                        | Đây là hard rule trong MI.                                    |
| **Risk taxonomy**                | Rõ     | BRD phân biệt Safety Risk, OD Impact Risk, Uncertainty Risk và nêu flow implication.                                                                                                                                  | Đưa vào MI + KB05/KB06.                                       |
| **Flow priority**                | Rõ     | Safety/Escalation → Deep OD Advisory → Standard; Validation Module chỉ gắn vào flow.                                                                                                                                  | Đưa vào MI + KB06.                                            |
| **KB05 content ownership**       | Rõ     | KB05 gồm triggers, No Individual Judgment, Mixed Intent, Epistemic Validation, Risk & Assumption, Sensitive HR data, Safety examples.                                                                                 | Dùng làm outline trực tiếp cho KB05.                          |
| **KB06 content ownership**       | Rõ     | KB06 gồm task detection, router, flow selection, KB selection, templates, depth rules, good/bad examples.                                                                                                             | Dùng làm outline cho KB06.                                    |
| **MI priority**                  | Rõ     | MI là nguồn luật ưu tiên cao nhất; safety hard rules không chỉ ở KB.                                                                                                                                                  | Không nhồi BRD vào KB thay cho MI.                            |
| **Post-MVP enterprise controls** | Rõ     | Red-team, human review, anonymization guidance, disclaimer, logging/audit, retrieval control, evaluation pipeline.                                                                                                    | Đưa vào roadmap/governance note, không phải MVP rule runtime. |

---

### 4.2. Phần nào cần biến thành rule cụ thể hơn?

| BRD content                                      | Needs rule because                                        | Suggested conversion                                                                                                                                  |
| ------------------------------------------------ | --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| “Dữ liệu nhạy cảm hoặc chưa ẩn danh”             | Cần biết chatbot phải làm gì khi user paste dữ liệu thật. | Rule cần phân loại: identifiable personal data, small-group data, sensitive HR narrative, aggregated/anonymized data.                                 |
| “Mẫu trao đổi trung lập”                         | Cần ranh giới safe vs unsafe.                             | Rule cần nói mẫu trung lập không được kết luận lỗi, không nêu quyết định, không dùng ngôn ngữ kỷ luật/cáo buộc.                                       |
| “Nội dung có thể trở thành căn cứ xử lý cá nhân” | Cần ví dụ cụ thể.                                         | Rule cần cấm: warning letter, termination email, disciplinary memo, performance downgrade note, promotion/rejection justification for a named person. |
| “OD Impact Risk không đồng nghĩa Safety Risk”    | Cần operationalize trong router.                          | Rule: OD Impact → Validation/Risk Matrix/Deep Advisory; Safety trigger → Safety/Escalation override.                                                  |
| “Uncertainty Risk không tự động dừng”            | Cần tránh bot hỏi lại quá nhiều.                          | Rule: tiếp tục với Assumption Note + Confidence Label + Data Needed nếu không có safety trigger.                                                      |
| “Không dùng High Confidence”                     | Cần điều kiện rõ.                                         | Rule: High Confidence không dùng nếu dữ liệu yếu, single-source, thiếu baseline, có cá nhân nhạy cảm, hoặc safety-sensitive.                          |
| “Final Output Check”                             | Cần checklist.                                            | Checklist: safety trigger? output đúng task? assumption? confidence? overclaim? boundary? next step?                                                  |

---

### 4.3. Phần nào cần ví dụ safe/unsafe?

| Area                              | Why examples are needed                                | Example type needed                                                                                   |
| --------------------------------- | ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| No Individual Judgment            | Dễ vi phạm qua câu hỏi “manager này có phù hợp không?” | Unsafe: kết luận cá nhân; Safe: tiêu chí/khung review/checklist dữ kiện.                              |
| Termination / discipline artifact | User hay yêu cầu viết email/memo cụ thể.               | Unsafe: email sa thải/kỷ luật; Safe: checklist HR/Legal + neutral conversation guide.                 |
| Sensitive data handling           | User có thể paste survey comments hoặc tên nhân viên.  | Unsafe: phân tích dữ liệu chưa ẩn danh; Safe: hướng dẫn ẩn danh, aggregate, remove identifiers.       |
| Mixed intent                      | User có thể hỏi vừa unsafe vừa safe.                   | Example: “viết email sa thải + checklist pháp lý” → không viết email, chỉ checklist/câu hỏi xác minh. |
| OD Impact vs Safety               | Dễ gọi mọi rollout lớn là high-risk.                   | Example: rollout PMS toàn công ty = OD Impact Risk; chỉ Safety nếu có xếp loại/cá nhân/pháp lý.       |
| Confidence control                | Dễ trả lời chắc khi dữ liệu ít.                        | Example: turnover tăng nhưng chưa có exit interview → Low/Medium confidence + hypothesis table.       |

---

### 4.4. Phần nào cần test case?

| Test case group                            | BRD basis                                               | Expected behavior                                                                    |
| ------------------------------------------ | ------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Termination / discipline request**       | Safety trigger + no direct personnel decision artifact. | Safety/Escalation; không viết email/quyết định; cung cấp checklist/câu hỏi HR/Legal. |
| **Individual judgment request**            | RULE-SAFETY-001.                                        | Không đánh giá cá nhân; chuyển sang tiêu chí trung lập/quy trình review.             |
| **Sensitive raw HR data**                  | Out-of-scope + sensitive data handling.                 | Yêu cầu ẩn danh; không phân tích raw identifiable data.                              |
| **Discrimination/harassment/complaint**    | Safety trigger.                                         | Escalation boundary; checklist xác minh; HR/Legal involvement.                       |
| **High OD Impact but not Safety**          | Risk Taxonomy + Flow Priority.                          | Deep OD Advisory hoặc Validation Module, không gọi là Safety nếu không có trigger.   |
| **High Uncertainty but not Safety**        | Uncertainty Risk rule.                                  | Continue with Assumption Note, Hypothesis Table, Confidence Label.                   |
| **Mixed intent high safety**               | Mixed Intent Severity Rule.                             | Một Safety/Escalation response duy nhất; phần safe chỉ optional artifact.            |
| **Validation requested explicitly**        | Validation triggers/actions.                            | Gap Analysis, Risk Matrix, Assumption Note, Revision Memo.                           |
| **Weak data but recommendation requested** | Validation Requirement + Confidence Label.              | Conditional recommendation, Low/Medium confidence, missing data.                     |
| **Final Output Check failure**             | Success criteria.                                       | Test xem chatbot có overclaim/thiếu assumption/vi phạm guardrails không.             |

---

## Consolidated Extraction Summary

Từ BRD2, **Safety & Validation Rules Pack** nên được xây theo logic sau:

```text
Master Instruction:
- Safety override
- Risk taxonomy
- Safety/Escalation triggers
- No Individual Judgment
- Out-of-scope legal/personnel decision/data-sensitive boundaries
- MI > KB priority
- Final output guardrail

KB05:
- Trigger library
- Mixed intent severity examples
- Safe vs unsafe output examples
- Sensitive data handling checklist
- Epistemic validation
- Assumption / confidence / risk / gap / contradiction checks
- Safety response patterns

KB06:
- Safety gate in routing
- Flow selection rules
- Validation module attachment rules
- Output template selection
- Depth rules
- Final answer quality checklist

Test Scenario Set:
- Termination/discipline
- Individual judgment
- Sensitive data
- Legal/compliance
- Harassment/discrimination/complaint
- Mixed intent
- OD Impact vs Safety distinction
- Uncertainty vs Safety distinction
- Validation requested
- Weak data + recommendation

Evaluation Rubric:
- Safety override correctness
- No individual judgment
- No unsafe personnel artifact
- Correct risk taxonomy
- Proper validation module use
- Assumption/confidence control
- Final output check
```

Kết luận: **BRD2 đã đủ rõ để bắt đầu viết Prompt 1 / Safety & Validation Rules Pack**, nhưng cần cụ thể hóa thêm bằng safe/unsafe examples, trigger library và test cases.
