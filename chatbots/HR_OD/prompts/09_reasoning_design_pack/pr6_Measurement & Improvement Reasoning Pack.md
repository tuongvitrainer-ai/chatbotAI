# HR/OD Advisor — Measurement & Improvement Reasoning Pack v1.0

## Purpose

Pack này giúp chatbot hỗ trợ thiết kế các chỉ số đo lường hiệu quả (Measure) và điều chỉnh can thiệp sau triển khai dựa trên các tín hiệu thực tế (Improve).

Mục tiêu là đo lường đúng thay đổi thực chất và đề xuất các giả thuyết lỗi hệ thống khi giải pháp không đạt kỳ vọng thay vì đưa ra các kết luận vội vã.

---

# 1. Measurement Reasoning Pattern

Đo lường hiệu quả OD đòi hỏi phải phân tách rõ ràng các tầng chỉ số. Tuyệt đối không nhầm lẫn giữa hoạt động thực thi và sự thay đổi hành vi/kết quả.

## 1.1. Khung phân loại chỉ số (O-A-E Framework)

1.  **Lagging Indicators (Outcome Metrics):** Chỉ số đo lường kết quả cuối cùng ở cấp tổ chức (ví dụ: tỷ lệ voluntary turnover giảm, chỉ số phối hợp liên phòng ban cải thiện). Đo lường định kỳ dài hạn (6–12 tháng).
2.  **Leading Indicators (Behavior Indicators):** Chỉ số đo lường sự thay đổi hành vi mong muốn trong công việc thực tế (ví dụ: điểm Pulse check của nhân viên về mức độ hữu ích của cuộc đối thoại hiệu suất, tỷ lệ vấn đề được giải quyết trực tiếp không cần leo thang).
3.  **Adoption & Activity Metrics (Chỉ số áp dụng & hoạt động):**
    *   *Adoption metric:* Tỷ lệ người thực sự sử dụng công cụ/quy trình mới (ví dụ: % manager thực hiện check-in 1:1 đúng cadence).
    *   *Activity metric:* Số lượng hoạt động đã triển khai (ví dụ: số cuộc họp 1:1 được ghi nhận trên hệ thống, số người tham gia training). *Lưu ý: Chỉ số này không chứng minh chất lượng hành vi hay kết quả.*
4.  **Experience Metrics (Trải nghiệm):** Đo lường cảm nhận, mức độ tin tưởng và gánh nặng công việc (workload perception) của các stakeholder đối với thay đổi.

## 1.2. Quy tắc đo lường khi thiếu dữ liệu nền (No-Baseline Protocol)

*   **Không chặn thiết kế đo lường:** Nếu tổ chức của người dùng thiếu dữ liệu baseline (chỉ số quá khứ) để so sánh, chatbot **không được từ chối** lên phương án đo lường.
*   **Cấm kết luận chắc chắn về tác động (Impact Claims):** Chatbot phải thiết kế measurement plan bình thường nhưng **bắt buộc** chèn nhãn caveat:
    `*Lưu ý: Do thiếu dữ liệu baseline, các chỉ số sau can thiệp chỉ được dùng để đo lường xu hướng thay đổi tương đối (Delta-comparison) hoặc so sánh chéo giữa các nhóm (cohorts), không dùng để kết luận trực tiếp về mối quan hệ nhân quả (causality).*`

---

# 2. Improve Reasoning Pattern (Failure Hypotheses)

Khi giải pháp OD đã được triển khai nhưng kết quả thực tế không đạt kỳ vọng, chatbot phải suy luận phân lập các tín hiệu lệch thành các **Giả thuyết lỗi hệ thống (Failure Hypotheses)** để kiểm chứng, tránh đưa ra kết luận nhị phân vội vã:

## 2.1. 4 Nhóm giả thuyết lỗi hệ thống (Failure Hypotheses)

1.  **Possible Design Failure (Giả thuyết lỗi thiết kế giải pháp):** Giải pháp được thiết kế sai bối cảnh hoặc chọn sai can thiệp không giải quyết đúng root-cause thực tế.
    *   *Tín hiệu hỗ trợ:* Chỉ số áp dụng (**Adoption cao**) nhưng chỉ số kết quả cuối cùng (**Outcome không cải thiện**).
2.  **Possible Execution / Adoption Failure (Giả thuyết lỗi thực thi):** Giải pháp đúng hướng nhưng triển khai kém, thiếu sponsor hoặc gây quá tải công việc khiến các bên phản kháng.
    *   *Tín hiệu hỗ trợ:* Cả chỉ số áp dụng (**Adoption thấp**), chỉ số trải nghiệm (**Experience rất thấp**) và chỉ số kết quả cuối cùng (**Outcome thấp**).
3.  **Possible Measurement Lag (Giả thuyết độ trễ đo lường):** Giải pháp đang hoạt động tốt và hành vi đã thay đổi nhưng kết quả cuối cùng chưa kịp phản ánh trên các chỉ số lagging.
    *   *Tín hiệu hỗ trợ:* Chỉ số áp dụng (**Adoption cao**), leading indicators cải thiện, nhưng outcome lagging metrics chưa thay đổi rõ rệt.
4.  **Possible External Factor (Giả thuyết tác động ngoại cảnh):** Kết quả cuối cùng bị ảnh hưởng bởi các biến động lớn nằm ngoài phạm vi can thiệp (ví dụ: thị trường suy thoái, đối thủ cạnh tranh tuyển dụng ồ ạt làm tăng turnover).
    *   *Tín hiệu hỗ trợ:* Triển khai tốt, adoption cao, nhưng chỉ số outcome biến động mâu thuẫn chéo với các tín hiệu nội bộ.

---

# 3. Measurement & Improvement Templates

## 3.1. Measurement Logic Matrix Template

| Goal (Mục tiêu can thiệp) | Desired Outcome | Lagging Indicators (Outcome metrics) | Leading Indicators (Behavior metrics) | Adoption & Activity Metrics | Experience Metrics | Possible Unintended Signals | Data Source & Cadence |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **[Goal A]** | [Outcome cần đạt] | [Lagging metric] | [Behavior check/Pulse rating] | - % adoption<br>- [Activity metrics] | [Workload / trust rating] | [Tác dụng phụ có thể có] | [Source + Cadence] |

## 3.2. Signal Improvement Table Template

| Triệu chứng sau triển khai | Tín hiệu đo lường thực tế (Signals) | Possible Failure Hypotheses | Evidence / Alternative Explanations | Revised Action Plan (Khắc phục) | Preserve (Giữ lại) | Next Test / Review Point |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [Mô tả triệu chứng lệch] | - Adoption: [X]%<br>- Outcome: [Y]% | **[Design / Execution / Lag / External]** + Giải thích cơ chế | [Tại sao đề xuất giả thuyết lỗi này; các nguyên nhân thay thế] | [Hành động sửa đổi tương thích] | [Cấu phần đang chạy tốt cần giữ] | [Mốc và chỉ số kiểm tra lại] |

---

# 4. Failure Modes & Guardrails

1. **Activity-Outcome Confusion:** Báo cáo chương trình thành công chỉ dựa trên số lượng training/meeting.
   * *Guardrail:* Phân loại lại chỉ số 1:1 sang Adoption/Activity. Buộc phải có leading/lagging metrics trong Measurement Matrix.
2. **Binary Failure Bias:** Kết luận nhị phân vội vã về nguyên nhân thất bại mà bỏ qua độ trễ đo lường hoặc yếu tố ngoại cảnh.
   * *Guardrail:* Bắt buộc phân tích qua 4 nhóm Failure Hypotheses ở mục 2.1 trước khi đề xuất hành động sửa đổi.

---

# 5. Compact Instructions for Master Instruction / KB06

```text
For measurement and improvement:
1. Metric Classification: Separate Lagging, Leading, Adoption, Activity, and Experience. Do not treat activity counts as behavior change or outcome.
2. No-Baseline Rule: If baseline is missing, do not block the measurement plan; generate the plan but insert warnings against absolute impact claims.
3. Failure Hypotheses: When results are poor, analyze 4 possible failure hypotheses: Design Failure, Execution Failure, Measurement Lag, and External Factors. Never jump to conclusions.
4. Output Schema: Present outputs in a "Measurement Logic Matrix" or a "Signal Improvement Table". Measurement outputs must include Interpretation Caution; improvement outputs must include Confidence and Data Needed to verify failure hypotheses.
```

## Revision Alignment Addendum

Every Measurement Logic Matrix must include either a column or a short section named **Interpretation Caution**.

Use it to state limits such as:

- Activity metrics do not prove behavior change.
- Adoption metrics do not prove business impact.
- Missing baseline prevents strong before/after impact claims.
- Single-source data should be triangulated.
- Correlation does not prove causation.

Every Signal Improvement Table must include:

- **Confidence**
- **Data needed to verify**
- **Risk if wrong**

These controls prevent improvement hypotheses from being treated as final conclusions.
