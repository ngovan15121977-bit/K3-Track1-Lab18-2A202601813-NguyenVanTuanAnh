# Day 18 — Chặng 3: Human–AI Design Pass

**Nhóm:** Chicken Plus  
**Thành viên:** 1. Phạm Bá Huy (MHV: 2A202601132)  
2. Nguyễn Văn Tuấn Anh (MHV: 2A202601813)  
**Case study:** AI Support Radar trên nền tảng VLearn

---

## 1. Human–AI Decision Table

Bảng dưới đây tổng hợp 4 quyết định thiết kế cho **Critical Interaction** (khoảnh khắc học viên bị kẹt code `useEffect` và kích hoạt trợ giúp) của cả 3 Solution Options:

| Human–AI Decision | Option A: Socratic Hints AI *(AI-Led / Guided)* | Option B: Contextual Explainer *(User-Led / Bounded)* | Option C: Fast SLA Q&A *(Human Baseline)* |
| :--- | :--- | :--- | :--- |
| **User làm gì?** | Nhấp *"Cần gợi ý tư duy"*, đọc câu hỏi gợi mở của AI và gõ câu trả lời/sửa code. | Bôi đen/khoanh vùng đoạn code hoặc mốc video bị kẹt và nhấp *"Giải thích đoạn này"*. | Nhập mô tả bế tắc + gắn code lỗi, gửi ticket hỗ trợ và chờ phản hồi. |
| **AI / Hệ thống làm gì?** | Phân tích bug, suy đoán lỗ hổng kiến thức, đặt câu hỏi gợi mở từng bước; không cho đáp án làm sẵn. | Giải thích cô đọng đúng vùng được chọn; tuyệt đối không mở rộng sang kiến thức ngoài bài học. | **0% Generative AI**. Hệ thống thu thập log/code, đóng gói ticket và định tuyến đến Trợ giảng (TA). |
| **Agency: Act / Ask / Don't Act?** | **Ask (Moderate Agency)**: AI chỉ đặt câu hỏi gợi ý khi user yêu cầu; không tự sửa code để tránh triệt tiêu tư duy. | **Don't Act (Low Agency)**: AI hoàn toàn yên lặng cho đến khi user bôi đen và bấm nút kích hoạt. | **Don't Act (No AI)**: Hệ thống chỉ làm nhiệm vụ chuyển giao, con người (TA) trực tiếp xử lý. |
| **Hiểu Capability & Limit bằng gì?** | Banner micro-copy: *"AI sẽ đặt câu hỏi gợi mở để bạn tự tư duy, tuyệt đối không cho đáp án trực tiếp."* | Micro-copy tooltip: *"AI giải thích ngắn gọn đúng phạm vi nội dung bạn vừa khoanh vùng."* | Notification: *"Câu hỏi sẽ được chuyển đến Trợ giảng (TA). Cam kết thời gian phản hồi ≤ 30 phút."* |
| **Evidence & Uncertainty thể hiện thế nào?** | **Evidence:** Dòng code gây lỗi & test case fail. <br>**Uncertainty:** Hiển thị câu hỏi xác nhận nếu AI chưa rõ lỗ hổng. | **Evidence:** Highlight lại đúng đoạn code/mốc video user chọn. <br>**Uncertainty:** Cảnh báo nếu vùng chọn quá ngắn/thiếu context. | **Evidence:** Trạng thái ticket & đồng hồ đếm ngược SLA. <br>**Uncertainty:** Cảnh báo trước nếu gửi câu hỏi vào đêm muộn. |
| **User Kiểm soát & Recovery thế nào?** | **Control:** Nút *"Đổi câu hỏi gợi ý"* hoặc *"Xem đáp án"*. <br>**Recovery:** Nút *"Hint không đúng ý"* để AI chọn lại mốc kiến thức. | **Control:** Nút *"Đơn giản hơn"* / *"Cho ví dụ"*. <br>**Recovery:** Nút *"Đóng Pop-up"* để quay lại bài học ngay lập tức. | **Control:** Chỉnh sửa/Bổ sung ticket hoặc nhấp *"Đã tự sửa được"*. <br>**Recovery:** Nút *"Học tiếp bài sau"* trong lúc chờ phản hồi. |

---

## 2. Chi tiết 4 Quyết định Thiết kế theo từng Option

### Option A: Socratic Hints AI *(AI-Led / Guided)*

1. **Expectation (Kỳ vọng & Giới hạn):**
   * *Thông điệp rõ ràng:* Ngay khi nhấp nút *"Cần gợi ý tư duy"*, một thẻ nhỏ hiển thị dòng micro-copy: *"AI sẽ đặt câu hỏi gợi mở để bạn tự phát hiện nguyên nhân. AI không sửa code thay bạn."*
   * *Giới hạn:* Khẳng định AI chỉ hỗ trợ trong phạm vi bài tập React Hooks hiện tại.

2. **Role and Agency (Vai trò & Quyền hạn):**
   * *Phân vai:* User chịu trách nhiệm suy nghĩ, gõ câu trả lời và sửa code; AI chịu trách nhiệm phân tích bug `useEffect` và phân nhỏ bài toán thành các câu hỏi gợi mở.
   * *Mức độ Agency:* **Ask (Moderate Agency)**. AI không bao giờ tự động chèn code sửa vào trình biên dịch (không Act). Rủi ro khi AI đoán sai lỗ hổng là user mất thời gian suy nghĩ lạc hướng, nhưng không bị hỏng bài làm.

3. **Evidence and Uncertainty (Bằng chứng & Độ không chắc chắn):**
   * *Evidence:* AI trích dẫn bằng chứng: *"Test case #2 fail: State `user` không cập nhật khi `props.id` thay đổi ở dòng 14."*
   * *Uncertainty:* Khi AI phân vân giữa 2 nguyên nhân (thiếu Dependency Array hay Closure bug), AI hiển thị: *"Có vẻ bạn đang vướng ở 1 trong 2 khái niệm này. Bạn muốn bắt đầu từ đâu?"* kèm 2 lựa chọn để user xác nhận.

4. **Control and Recovery (Kiểm soát & Phục hồi):**
   * *Control:* User có nút *"Đổi câu hỏi gợi ý"* nếu câu hỏi hiện tại quá khó hiểu.
   * *Recovery:* Nếu AI dẫn dắt sai 3 lần liên tiếp, nút khẩn cấp *"Xem đáp án chi tiết & Giải thích"* sẽ sáng lên để user chủ động thoát khỏi vòng lặp gợi mở.

---

### Option B: In-video Contextual Explainer *(User-Led / Bounded)*

1. **Expectation (Kỳ vọng & Giới hạn):**
   * *Thông điệp rõ ràng:* Tooltip xuất hiện ngay trên vùng bôi đen: *"AI chỉ giải thích đúng đoạn nội dung được chọn, sử dụng thuật ngữ quen thuộc của bài học."*
   * *Giới hạn:* AI từ chối trả lời các câu hỏi mở vượt ngoài phạm vi bôi đen.

2. **Role and Agency (Vai trò & Quyền hạn):**
   * *Phân vai:* User chủ động 100% việc chọn vị trí khó hiểu; AI đóng vai trò là từ điển/giải thích viên thu nhỏ tại chỗ.
   * *Mức độ Agency:* **Don't Act (cho đến khi Trigger)**. AI nằm ẩn hoàn toàn, không tự động bật pop-up khi user dừng video hay gặp lỗi code.

3. **Evidence and Uncertainty (Bằng chứng & Độ không chắc chắn):**
   * *Evidence:* Trong thẻ giải thích, AI trích dẫn lại đoạn code và mốc thời gian tương ứng (ví dụ: *"Đoạn code dòng 8 - tương ứng mốc 04:12 trong video"*).
   * *Uncertainty:* Nếu user bôi đen quá ngắn (ví dụ chỉ bôi đen 1 từ `setCount`), AI báo: *"Vùng chọn quá ngắn để giải thích đúng ngữ cảnh. Bạn hãy bôi đen trọn vẹn dòng lệnh."*

4. **Control and Recovery (Kiểm soát & Phục hồi):**
   * *Control:* User có các phím tắt nhanh trong pop-up: *"Giải thích ngắn hơn"*, *"Cho ví dụ minh họa"*, hoặc *"Dịch sang tiếng Việt"*.
   * *Recovery:* Nút *"X"* (Dismiss) ở góc thẻ giải thích giúp đóng ngay lập tức để tiếp tục xem bài giảng mà không ảnh hưởng giao diện.

---

### Option C: Fast SLA Q&A *(Human Baseline / Non-AI)*

1. **Expectation (Kỳ vọng & Giới hạn):**
   * *Thông điệp rõ ràng:* Form gửi câu hỏi ghi rõ: *"Thắc mắc của bạn sẽ được gửi tới Trợ giảng con người (TA). Phản hồi cam kết trong ≤ 30 phút."*
   * *Giới hạn:* Đây không phải kênh chat tức thì, user cần cung cấp đủ mô tả bế tắc và code lỗi.

2. **Role and Agency (Vai trò & Quyền hạn):**
   * *Phân vai:* User tạo ticket mô tả bế tắc; Trợ giảng người thật (TA) đánh giá và đưa ra câu trả lời.
   * *Mức độ Agency:* **No AI Agency**. 0% tự động sinh nội dung.

3. **Evidence and Uncertainty (Bằng chứng & Độ không chắc chắn):**
   * *Evidence:* Hiển thị rõ tên/avatar TA nhận hỗ trợ, tiến trình ticket (*Đã gửi -> TA đang đọc -> Đã trả lời*) và đồng hồ đếm ngược SLA (30:00).
   * *Uncertainty:* Nếu gửi bài trong khung giờ đêm muộn (23:00 - 06:00), hệ thống đưa ra thông báo: *"Khung giờ này có ít TA trực, thời gian phản hồi có thể kéo dài lên đến 45 phút."*

4. **Control and Recovery (Kiểm soát & Phục hồi):**
   * *Control:* User có thể bổ sung thêm ảnh chụp màn hình/code mới vào ticket đã gửi, hoặc bấm *"Hủy ticket"* nếu không còn cần nữa.
   * *Recovery:* Nút *"Chuyển sang bài học tiếp theo"* giúp user tiếp tục lộ trình học trong thời gian chờ notification từ TA.

---

## 3. Feedback and Data Check

* **Ghi nhớ & Ảnh hưởng phiên làm việc (State & Memory):**
  * **Option A:** Hệ thống ghi nhớ các tương tác sai trong phiên làm việc hiện tại để hạ thấp độ khó của câu hỏi gợi mở tiếp theo. Không lưu trữ thông tin câu hỏi sai sang các bài học khác để tránh tạo định kiến năng lực học viên.
  * **Option B:** Không lưu lịch sử tương tác. Mỗi thao tác bôi đen khoanh vùng là một truy vấn độc lập.
* **Quyền dữ liệu người dùng (Privacy & Data Governance):**
  * Chỉ có thông tin mã nguồn bài tập hiện tại và nhật ký lỗi biên dịch được gửi về hệ thống xử lý. Thông tin cá nhân học viên được ẩn danh. Học viên có quyền nhấn *"Xóa dữ liệu hội thoại"* bất kỳ lúc nào.

---

## 4. Tự kiểm — GATE 3 (Human Control Check)

| Tiêu chí Gate 3 | Option A | Option B | Option C | Đạt? |
| :--- | :---: | :---: | :---: | :---: |
| **Nói rõ User & AI làm gì ở Critical Moment** | ✅ | ✅ | ✅ | **ĐẠT** |
| **Agency phù hợp với hậu quả khi sai** | ✅ (Ask) | ✅ (Don't Act) | ✅ (No AI) | **ĐẠT** |
| **Có ít nhất một đường Kiểm soát (Control)** | ✅ | ✅ | ✅ | **ĐẠT** |
| **Có đường Phục hồi (Recovery) khi AI sai/bế tắc** | ✅ | ✅ | ✅ | **ĐẠT** |

**→ Đã hoàn thành Chặng 3 và đạt chuẩn Gate 3.** Sẵn sàng chuyển sang Chặng 4 (Build ba micro-prototype).