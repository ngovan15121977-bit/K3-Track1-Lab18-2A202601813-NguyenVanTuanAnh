# AI Support Log — Day 18

**Học viên:** Nguyễn Văn Tuấn Anh (MHV: 2A202601813)  
**Nhóm:** Chicken Plus  
**Bài lab:** Track 1 – Day 18 (Multiple Prototypes – Human–AI design)

---

## 1. AI đã giúp tôi ở đâu?

- Gợi ý cấu trúc file Markdown theo đúng yêu cầu nộp (README 6 phần, Design Sheet, Feedback Note, Synthesis).
- Tạo / chỉnh **canned code fixture** `useEffect` thiếu dependency array để dùng chung cho A/B/C.
- Rà soát 3 options có thật sự khác về **mechanism** và **role split** (không chỉ khác layout/wording).
- Gợi ý từ khóa chuẩn cho Human–AI Decision Table: Expectation, Agency (Act / Ask / Don’t Act), Evidence & Uncertainty, Control & Recovery.
- Gợi ý câu hỏi dẫn dắt / observation focus khi chuẩn bị test prompt.
- Hỗ trợ chuẩn hóa bảng so sánh và diễn đạt tiếng Việt rõ ràng hơn.

**Công cụ đã dùng:** ChatGPT / Claude / Gemini (tùy phiên).

---

## 2. AI sai, hời hợt hoặc làm các options giống nhau ở đâu?

- Lần đầu AI đề xuất 3 option chỉ khác **cách hiện UI** (chat vs sidebar vs modal) → không đủ “meaningful options”. Nhóm đã từ chối và quay lại chia theo **agency** (AI-led / User-led / Human baseline).
- AI có xu hướng viết Expectation / Recovery **quá chung** (“user có thể quay lại”) — thiếu nút / hành động cụ thể. Đã sửa thành nút rõ: “Đổi hướng gợi ý”, “Xem đáp án mẫu”, “Đóng pop-up”, “Đã tự sửa được”.
- Khi gợi ý canned output, AI đôi khi giải thích bằng thuật ngữ nâng cao (đúng pain mà hypothesis đang giải) — đã chỉnh lại micro-copy và giải thích Option B giới hạn trong thuật ngữ bài học.
- AI không cảnh báo đủ mạnh về việc **không được bịa feedback**. Đã tự giữ nguyên tắc: mọi quote / observation trong Feedback Note phải từ phiên test thật.

---

## 3. Tôi đã tự sửa hoặc quyết định lại điều gì?

- **Chốt 3 option theo agency** (Socratic / Contextual / SLA TA) thay vì theo giao diện.
- Viết lại Hypothesis Problem nối trực tiếp 2 Practice Notes Day 17 (Teo + Thành) và ghi rõ phần **chưa chứng minh** (silent drop-out).
- Tự viết / chỉnh Human–AI Decision Table cho từng option, đặc biệt Control & Recovery.
- Facilitate phiên test, ghi hành vi trước khi diễn giải; không để AI viết hộ Feedback Note.
- Cùng nhóm chốt **Next Change = hybrid A+B**, giữ C làm escalation — không tuyên bố validated.
- Tách AI Support Log ra file riêng; không nhét vào Design Sheet hay Feedback Note.

---

## 4. Cam kết tính trung thực

- Không dùng AI để tạo quote, observation hoặc user feedback không tồn tại.
- Không viết lại evidence đến mức không còn phân biệt lời user với diễn giải.
- Không chọn option thay tester hoặc thay nhóm.
- Phần đóng góp cá nhân và reflection trong README / Feedback Note là do người nộp viết.

---

**Tỷ lệ ước lượng:**  
Thiết kế & quyết định (Hypothesis, Options, Human–AI, Next Change) ≈ 70–80% nhóm + cá nhân; AI chủ yếu hỗ trợ cấu trúc, diễn đạt và rà soát.
