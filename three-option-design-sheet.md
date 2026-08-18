# AI Support Log (Khai báo sử dụng AI)

**Học viên:** Nguyễn Văn Tuấn Anh (MHV: 2A202601813)  
**Nhóm:** Chicken Plus  
**Bài lab:** Track 1 - Day 18 (Multiple Prototypes - Human–AI design)

## 1. Hypothesis Problem & Comparison Contract

### Hypothesis Problem
Học viên VLearn khi tự học lập trình trực tuyến một mình vào buổi tối, khi gặp phải bài tập React Hooks có bug (`useEffect` state không cập nhật) thường tốn 30–40 phút thử sai mà không nhận diện được lỗ hổng kiến thức cốt lõi. Học viên bị mắc kẹt giữa hai cực: hoặc mò mẫm mất thời gian, hoặc chép đáp án mẫu mà không hiểu bản chất.

### Comparison Contract (Yếu tố giữ nguyên cho A/B/C)
* **Target User:** Học viên tự học lập trình Web/React trên VLearn.
* **Situation:** Tự làm bài tập một mình vào ca đêm, bị test case báo lỗi và không có ai hỗ trợ trực tiếp.
* **Task:** Tìm ra nguyên nhân khiến state `user` không cập nhật khi đổi `userId` và sửa code để pass Test Case #2.
* **Desired Outcome:** Tự nhận diện được lỗi thiếu Dependency Array, sửa đúng code và hiểu bản chất mà không phụ thuộc vào đáp án có sẵn.
* **Content Fixture:** Bài tập React Hooks với đoạn code lỗi `useEffect(() => { fetchUserData(userId)... }, []);`.

---

## 2. Ma trận 3 Solution Options

| Yếu tố | Option A: Socratic Hints AI | Option B: Contextual Explainer | Option C: Fast SLA Q&A |
| :--- | :--- | :--- | :--- |
| **Cơ chế (Mechanism)** | AI chẩn đoán lỗi và đưa ra chuỗi câu hỏi gợi mở, không cho đáp án trực tiếp. | User bôi đen vị trí bị kẹt (code/video), AI giải thích cô đọng đúng phạm vi đó. | Chuyển giao câu hỏi cho Trợ giảng con người (TA) với cam kết SLA phản hồi ≤ 30 phút. |
| **User làm gì?** | Bấm *"Gợi ý tư duy"*, đọc câu hỏi của AI và gõ câu trả lời/sửa code. | Bôi đen dòng code hoặc mốc video khó hiểu và bấm *"Giải thích đoạn này"*. | Soạn mô tả bế tắc + đính kèm code lỗi, gửi ticket và chờ phản hồi. |
| **AI làm gì?** | Phân tích bug, đoán lỗ hổng kiến thức và điều hướng trình tự câu hỏi gợi mở. | Giải thích ngắn gọn phạm vi được chọn; không mở rộng khái niệm lạ ngoài bài học. | **0% AI**. Hệ thống đóng gói ticket và tự động định tuyến đến TA. |
| **Trigger** | Nút bấm *"💡 Cần gợi ý tư duy"*. | Thao tác bôi đen text + Pop-up *"🔍 Giải thích đoạn này"*. | Nút bấm *"🙋‍♂️ Gửi câu hỏi cho TA"*. |
| **Quyền quyết định** | AI dẫn dắt câu hỏi; User quyết định trả lời hay dừng lại. | User toàn quyền chọn phạm vi; AI thụ động phản hồi trong phạm vi đó. | Trợ giảng người thật (TA) toàn quyền chẩn đoán và đưa ra giải pháp. |
| **Trade-off chính** | Hiểu sâu bản chất nhưng tốn thời gian; rủi ro AI đoán sai gây ức chế. | Trả lời đúng chỗ ngứa, nhanh chóng; rủi ro user chọn sai vị trí bị kẹt. | Câu trả lời chuẩn xác 100%; nhưng phải chờ đợi lâu (SLA 30 phút) gây đứt đà học. |

---

## 3. Distance Check

* **A khác B vì:** Option A để AI chủ động chẩn đoán và đặt câu hỏi điều hướng tư duy người dùng; Option B phụ thuộc vào việc User chủ động khoanh vùng và AI chỉ thụ động giải thích trong phạm vi hẹp đó.
* **B khác C vì:** Option B sử dụng AI phản hồi ngay tức thì dựa trên đoạn chọn; Option C loại bỏ AI để chuyển sang con người (Trợ giảng) hỗ trợ có độ trễ.
* **A khác C vì:** Option A là tương tác tương tác thời gian thực giữa Người và AI; Option C là giao tiếp bất đồng bộ giữa Người và Người (Human baseline).

---

## 4. Human–AI Decision Table

| Decision | Option A (Socratic Hints) | Option B (Contextual Explainer) | Option C (Fast SLA Q&A) |
| :--- | :--- | :--- | :--- |
| **Expectation** | Micro-copy: *"AI sẽ đặt câu hỏi gợi mở giúp bạn tự suy nghĩ, không cho đáp án."* | Micro-copy: *"AI giải thích ngắn gọn đúng nội dung bạn khoanh vùng."* | Notification: *"Gửi tới Trợ giảng TA. Cam kết phản hồi trong ≤ 30 phút."* |
| **Role & Agency** | **Ask (Moderate)**: AI gợi mở khi user bấm nút, không tự chèn code sửa. | **Don't Act (Low)**: AI nằm ẩn hoàn toàn cho đến khi user bôi đen kích hoạt. | **Don't Act (No AI)**: 0% Generative AI, con người xử lý. |
| **Evidence & Uncertainty** | Chỉ ra dòng code fail test case; hiển thị câu hỏi xác nhận nếu chưa rõ lỗ hổng. | Highlight lại đúng đoạn code user chọn; cảnh báo nếu đoạn chọn quá ngắn. | Hiển thị đồng hồ đếm ngược SLA & trạng thái ticket; cảnh báo nếu đêm muộn ít TA. |
| **Control & Recovery** | **Control:** Nút *"Đổi hướng gợi ý"*. <br>**Recovery:** Nút khẩn cấp *"Xem đáp án mẫu"*. | **Control:** Nút *"Cho ví dụ"*. <br>**Recovery:** Nút *"✖ Đóng pop-up"* để quay lại bài học. | **Control:** Sửa ticket / *"Đã tự sửa được"*. <br>**Recovery:** Nút *"Học bài tiếp"* trong lúc chờ. |