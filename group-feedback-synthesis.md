# Group Feedback Synthesis — Day 18

**Nhóm:** Chicken Plus  
**Thành viên:** Nguyễn Văn Tuấn Anh (2A202601813), Phạm Bá Huy (2A202601132)  
**Nguồn:** 2 Feedback Notes từ 2 phiên A/B/C (mỗi thành viên facilitate 1 tester ngoài nhóm)  
**Case:** AI Support Radar — VLearn / `useEffect`

> Lưu ý: Nhóm chỉ 2 thành viên → có 2 Feedback Notes (không phải 3). Synthesis dựa trên 2 phiên thật + evidence Day 17.

---

## 1. Pattern chung giữa các phiên

| Pattern | Mô tả ngắn | Xuất hiện ở option |
|---------|------------|---------------------|
| Muốn hiểu bản chất, không chỉ “sửa cho pass” | Tester đánh giá cao khi được dẫn dắt suy nghĩ thay vì nhận đáp án sẵn | A mạnh |
| Cần tốc độ khi đang “đang code dở” | Không muốn chờ lâu; sẵn sàng đổi cách nếu chậm | B thắng về tốc độ; C yếu |
| Khó tự khoanh đúng chỗ hổng | Với B, tester đôi khi không chắc nên bôi đen đoạn nào | B (risk đã dự đoán) |
| Không chấp nhận độ trễ 30 phút trong context ban đêm / giữa bài | Ticket TA hữu ích về độ tin cậy nhưng không khớp moment “kẹt ngay bây giờ” | C |
| A và B bổ sung nhau hơn là đối lập | Muốn gợi mở tư duy + có “lối tắt” giải thích đúng chỗ khi cần | A + B |

---

## 2. Khác biệt đáng chú ý

- Một tester ưu tiên **A** (hiểu sâu) khi không bị áp lực thời gian.
- Tester khác ưu tiên **B** (nhanh, sát ngữ cảnh) khi đang muốn “xong bài để đi ngủ”.
- Cả hai đều **không chọn C** làm option chính cho tình huống tự học đêm — C được xem là “kênh dự phòng khi AI không giải quyết được”.

---

## 3. Next Change (một thay đổi tiếp theo)

**Quyết định nhóm:**

> **Kết hợp A + B thành một luồng linh hoạt:**  
> Mặc định mở **Socratic Hints (A)**. Trong luồng gợi mở, luôn hiện nút phụ **“Giải thích đúng đoạn này” (B)** để user có thể bôi đen / nhảy sang giải thích phạm vi hẹp khi cảm thấy câu hỏi AI quá vòng vo hoặc khi đã đoán ra chỗ nghi ngờ.  
> Giữ **C** như kênh escalation (gửi TA) khi cả A và B vẫn không đủ — không đặt C làm lựa chọn đầu.

**Lý do dựa trên feedback:**
- User muốn vừa không bị “cho đáp án sẵn” vừa không bị kẹt quá lâu.
- Risk của B (chọn sai đoạn) được giảm nếu trước đó A đã giúp user định hướng “mình đang thiếu gì”.
- Risk của A (tốn thời gian / AI đoán sai) được giảm nhờ lối thoát B.

**Không làm ở bước này:** Xây full product; tuyên bố solution đã validated; bỏ hoàn toàn C.

---

## 4. Still Unproven (điều vẫn chưa được chứng minh)

1. **Khi AI (Option A) đoán sai 2–3 lần liên tiếp**, user có bỏ cuộc / mất tin / chuyển sang Google/ChatGPT ngoài không? (Chưa quan sát đủ lần fail của AI.)
2. **User hoàn toàn mới với React / chưa từng nghe “dependency array”** có dùng được A và B không, hay cần onboarding / ví dụ mạnh hơn?
3. **Silent drop-out:** Hypothesis Day 17 còn claim hậu quả dài hạn (bỏ học / hổng dây chuyền). 2 Practice Notes + 2 test phiên đều chưa thấy ai nói đến việc bỏ khóa — chỉ thấy mất thời gian và nản ngắn hạn.
4. **So sánh với AI ngoài (ChatGPT/Gemini):** Chưa test A/B cạnh tranh trực tiếp với việc paste code sang ChatGPT trong cùng session.
5. **Số lượng tester còn ít** (2 phiên) → pattern trên là tín hiệu, chưa phải validation.

---

## 5. Liên kết lại Hypothesis Problem

Hypothesis vẫn đứng vững: pain chính là **chẩn đoán đúng lỗ hổng + nhận giải thích đúng tầm** trong lúc tự học một mình.  
A và B cùng nhắm pain đó với hai cách chia agency khác nhau; C đo baseline con người.  
Next Change (A+B hybrid) là bước iteration hợp lý từ feedback, **không** phải tuyên bố product–market fit.

---

## 6. Tự kiểm Gate 5

| Tiêu chí | Đạt? |
|----------|------|
| Có Feedback Notes từ tester ngoài nhóm | ✅ (2 notes, tương ứng 2 thành viên) |
| Tách pattern / khác biệt | ✅ |
| Có **một** Next Change rõ, không nói quá evidence | ✅ |
| Có **Still Unproven** | ✅ |
| Không tuyên bố “đã validated” | ✅ |
