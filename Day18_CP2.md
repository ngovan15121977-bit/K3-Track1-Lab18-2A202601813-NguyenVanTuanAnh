# Day 18 — Chặng 2: Chọn ba Solution Options

**Nhóm:** Chicken Plus  
**Thành viên:** 1. Phạm Bá Huy (MHV: 2A202601132)
2. Nguyễn Văn Tuấn Anh (MHV: 2A202601813)  
**Case study:** AI Support Radar trên nền tảng VLearn

---

## 1. Thành phần giữ nguyên (Constants Across A/B/C)

Để đảm bảo phép so sánh ở Chặng 6 có ý nghĩa, cả 3 Solution Options đều giữ nguyên các thành phần nền tảng từ Hypothesis Problem ở Chặng 1:

* **Target User:** Học viên tự học lập trình trực tuyến trên VLearn.
* **Situation:** Học viên đang tự học một mình vào ban đêm, gặp phải bài tập hoặc khái niệm không hiểu và không có ai bên cạnh để hỏi ngay.
* **Task:** Tự chẩn đoán đúng lỗ hổng kiến thức của mình và nhận giải thích đúng tầm hiểu biết để tiếp tục bài học.
* **Desired Outcome:** Nhận diện được điểm thiếu sót trong kiến thức, tự sửa được lỗi và tiếp tục bài học mà không bị nản lòng hay phụ thuộc vào đáp án làm sẵn.
* **Content / Data Fixture:** Đoạn bài giảng và bài tập React Hooks có bug `useEffect` (state không cập nhật khi chuyển component).

---

## 2. Ma trận 3 Solution Options (Differentiating Variables)

Nhóm chọn 3 cách giải đại diện cho 3 mức độ chia sẻ công việc và quyền quyết định khác nhau trên cùng một bài toán:

| Thành phần | Option A: Socratic Hints AI | Option B: In-video Contextual Explainer | Option C: Fast SLA Q&A |
| :--- | :--- | :--- | :--- |
| **Nguồn (Parking Lot #)** | #1 | #3 | #2 |
| **Cơ chế chính (Mechanism)** | AI chẩn đoán lỗi và đặt chuỗi câu hỏi gợi mở (Socratic) từng bước, không cho đáp án làm sẵn. | User chủ động bôi đen/chọn vị trí bị kẹt (code/slide/video), AI giải thích cô đọng đúng phạm vi đó. | Chuyển giao câu hỏi đến Trợ giảng người thật (TA) với cam kết thời gian phản hồi (SLA). |
| **User làm gì?** | Bấm xin gợi ý, đọc câu hỏi gợi mở của AI và nhập câu trả lời hoặc thử lại code. | Bôi đen/tap chọn đoạn code hoặc mốc video chưa hiểu và yêu cầu AI giải thích. | Nhập câu hỏi cụ thể kèm mã nguồn lỗi, gửi ticket hỗ trợ và chờ phản hồi. |
| **AI làm gì?** | Chủ động suy đoán lỗ hổng kiến thức từ code lỗi và điều hướng trình tự câu hỏi gợi mở. | Giải thích đúng phạm vi nội dung user đã chọn, không mở rộng sang khái niệm/thuật ngữ mới. | Không dùng AI (Baseline con người). Hệ thống chỉ tự động định tuyến ticket đến TA. |
| **Trigger** | Nút bấm *"Cần gợi ý tư duy"*. | Thao tác Highlight/Chọn văn bản + Nút *"Giải thích đoạn này"*. | Nút bấm *"Gửi câu hỏi cho TA"*. |
| **Ai giữ quyền quyết định?** | AI dẫn dắt trình tự câu hỏi; User quyết định trả lời hay bỏ qua. | User quyết định phạm vi nội dung; AI chỉ phản hồi giới hạn trong phạm vi đó. | Con người (Trợ giảng TA) toàn quyền chẩn đoán và đưa ra câu trả lời. |
| **Trade-off chính** | Buộc user phải tự tư duy nhưng tốn thời gian; rủi ro AI đoán sai lỗ hổng khiến hint bị lạc đề. | Phản hồi nhanh và sát ngữ cảnh; rủi ro user chọn sai vị trí do không biết mình bị kẹt ở đâu. | Câu trả lời chính xác từ con người; nhưng phải chờ đợi (SLA ≤ 30 phút) làm đứt đà tự học. |

---

## 3. Distance Check (Kiểm tra độ biệt lập giữa các Option)

* **A khác B vì:** Option A để AI chủ động đoán lỗ hổng và đặt câu hỏi điều hướng tư duy của user, trong khi Option B hoàn toàn do user chủ động khoanh vùng vị trí bị kẹt và AI chỉ phản hồi thụ động trong phạm vi hẹp đó.
* **B khác C vì:** Option B sử dụng AI giải thích tức thì theo ngữ cảnh khoanh vùng, trong khi Option C loại bỏ hoàn toàn AI để chuyển giao cho con người (Trợ giảng) phản hồi có độ trễ.
* **A khác C vì:** Option A là tương tác thời gian thực giữa User và AI qua luồng đối thoại gợi mở, trong khi Option C là luồng tương tác bất đồng bộ giữa User và con người làm mốc đối chứng (human baseline).

---

## 4. Tự kiểm — GATE 2 (Meaningful options)

| Tiêu chí | Đạt? | Minh chứng |
| :--- | :---: | :--- |
| **Giữ nguyên User, Situation, Task & Desired Outcome** | ✅ | Cả 3 options đều dùng chung ngữ cảnh học viên bị kẹt bài tập `useEffect`. |
| **Khác nhau có ý nghĩa ở cơ chế (Mechanism / Agency)** | ✅ | Chia rõ 3 mức độ: AI-Led (Option A), User-Led (Option B), và Human Escalation (Option C). |
| **Không phân biệt chỉ bằng UI / Wording** | ✅ | Sự khác biệt nằm ở vai trò, quyền quyết định và bản chất luồng xử lý bài toán. |

**→ Đã hoàn thành Chặng 2 và đạt Gate 2.** Sẵn sàng chuyển sang Chặng 3 (Human–AI Design Pass).