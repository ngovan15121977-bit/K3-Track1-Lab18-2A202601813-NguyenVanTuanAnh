# Three-option Design Sheet — Day 18
**Nhóm:** Chicken Plus  
**Thành viên:** Nguyễn Văn Tuấn Anh (2A202601813), Phạm Bá Huy (2A202601132)  
**Case:** AI Support Radar — VLearn / bài tập React Hooks (`useEffect`)

---

## 1. Hypothesis Problem (điểm xuất phát)

Khi đang tự học lập trình trực tuyến một mình và gặp một bài tập hoặc khái niệm không hiểu (lỗi state trong React Hooks…), **học viên** gặp khó khăn trong việc **tự chẩn đoán đúng lỗ hổng kiến thức và nhận giải thích đúng tầm hiểu biết để tiếp tục bài học**, vì **công cụ hiện có (Google, ChatGPT/Gemini) hoặc đưa đáp án hoàn chỉnh khiến mất tư duy, hoặc giải thích bằng thuật ngữ ngoài tầm — trong khi không có ai bên cạnh để hỏi ngay**, dẫn đến **mất 30–60 phút bế tắc, nản lòng, hổng kiến thức dây chuyền**.

**Evidence Day 17 hỗ trợ:**
- Teo: ~40 phút, 3 lần thử sai mới nhận ra thiếu kiến thức; ChatGPT đưa thuật ngữ lạ.
- Thành: nhận đáp án đầy đủ → mất tư duy; phải tự hỏi tiếp từng bước.

**Vẫn chưa chứng minh:** Silent drop-out; pattern có lặp với môn ngoài lập trình hay không.

---

## 2. Comparison Contract (giữ nguyên cho A/B/C)

| Thành phần | Giá trị dùng chung |
|------------|--------------------|
| **Target User** | Học viên tự học lập trình Web/React trên VLearn |
| **Situation** | Tự làm bài tập một mình vào ca đêm, test case fail, không có ai hỗ trợ trực tiếp |
| **Task** | Tìm nguyên nhân state `user` không cập nhật khi đổi `userId` và sửa code để pass Test Case #2 |
| **Desired Outcome** | Tự nhận diện lỗi thiếu Dependency Array, sửa đúng code và hiểu bản chất, không phụ thuộc đáp án sẵn |
| **Content Fixture** | `useEffect(() => { fetchUserData(userId).then(data => setUser(data)); }, []);` — thiếu `userId` trong dependency array |

---

## 3. Ma trận 3 Solution Options

| Yếu tố | **Option A: Socratic Hints AI** | **Option B: Contextual Explainer** | **Option C: Fast SLA Q&A** |
|--------|--------------------------------|------------------------------------|----------------------------|
| **Cơ chế (Mechanism)** | AI chẩn đoán lỗi → chuỗi câu hỏi gợi mở, không cho đáp án trực tiếp | User bôi đen vị trí bị kẹt (code/video) → AI giải thích đúng phạm vi đó | Chuyển câu hỏi cho TA người thật, SLA ≤ 30 phút |
| **User làm gì?** | Bấm “Cần gợi ý tư duy”, đọc câu hỏi, gõ trả lời / sửa code | Bôi đen dòng code hoặc mốc video → bấm “Giải thích đoạn này” | Soạn mô tả bế tắc + đính kèm code → gửi ticket → chờ |
| **AI / Hệ thống làm gì?** | Phân tích bug, đoán lỗ hổng kiến thức, điều hướng câu hỏi gợi mở | Giải thích ngắn gọn đúng phạm vi chọn; không mở rộng khái niệm lạ | **0% generative AI** — đóng gói ticket + định tuyến đến TA |
| **Trigger** | Nút “💡 Cần gợi ý tư duy” | Highlight text + pop-up “🔍 Giải thích đoạn này” | Nút “🙋 Gửi câu hỏi cho TA” |
| **Ai giữ quyền quyết định?** | AI dẫn dắt trình tự câu hỏi; User quyết định trả lời hay dừng | User toàn quyền chọn phạm vi; AI thụ động phản hồi trong phạm vi | TA người thật toàn quyền chẩn đoán và trả lời |
| **Trade-off chính** | Hiểu sâu nhưng tốn thời gian; rủi ro AI đoán sai → ức chế | Nhanh, sát chỗ ngứa; rủi ro user chọn sai vị trí | Chính xác cao; phải chờ → đứt đà học |

### Distance Check
- **A ≠ B:** A = AI chủ động chẩn đoán + dẫn dắt; B = User chủ động khoanh vùng, AI chỉ phản hồi thụ động.
- **B ≠ C:** B = AI tức thì theo ngữ cảnh; C = không AI, chuyển sang con người có độ trễ.
- **A ≠ C:** A = tương tác real-time Người–AI; C = bất đồng bộ Người–Người (human baseline).

---

## 4. Human–AI Decision Table

| Decision | Option A (Socratic Hints) | Option B (Contextual Explainer) | Option C (Fast SLA Q&A) |
|----------|---------------------------|---------------------------------|-------------------------|
| **Expectation** | Micro-copy: “AI sẽ đặt câu hỏi gợi mở giúp bạn tự suy nghĩ, không cho đáp án.” | Micro-copy: “AI giải thích ngắn gọn đúng nội dung bạn khoanh vùng.” | Notification: “Gửi tới TA. Cam kết phản hồi ≤ 30 phút.” |
| **Role & Agency** | **Ask (Moderate):** AI gợi mở khi user bấm nút; không tự chèn code sửa | **Don’t Act (Low):** AI ẩn hoàn toàn đến khi user bôi đen kích hoạt | **Don’t Act (No AI):** 0% generative AI, con người xử lý |
| **Evidence & Uncertainty** | Chỉ ra dòng code fail test case; hiện câu hỏi xác nhận nếu chưa rõ lỗ hổng | Highlight lại đúng đoạn user chọn; cảnh báo nếu đoạn quá ngắn | Đồng hồ đếm ngược SLA + trạng thái ticket; cảnh báo nếu đêm muộn ít TA |
| **Control & Recovery** | Control: “Đổi hướng gợi ý”. Recovery: “Xem đáp án mẫu” (khẩn cấp) | Control: “Cho ví dụ” / “Đơn giản hơn”. Recovery: “✖ Đóng pop-up” | Control: Sửa ticket / “Đã tự sửa được”. Recovery: “Học bài tiếp” trong lúc chờ |

### Chi tiết Control & Recovery (rút gọn)

**Option A**
- Expectation rõ: AI không sửa code thay user.
- Control: đổi câu hỏi nếu quá khó / lạc đề.
- Recovery: sau 2–3 lần gợi mở không khớp → hiện nút đáp án + giải thích.

**Option B**
- Expectation: chỉ giải thích đúng phạm vi bôi đen.
- Control: yêu cầu ví dụ / rút gọn.
- Recovery: đóng pop-up ngay, quay lại bài học không bị kẹt UI.

**Option C**
- Expectation: đây là kênh TA, không phải chat tức thì.
- Control: bổ sung ticket hoặc hủy khi đã tự xử lý.
- Recovery: tiếp tục học bài khác trong lúc chờ.

---

## 5. Tự kiểm Gate 2 & Gate 3

| Tiêu chí | Đạt? |
|----------|------|
| Cùng user / situation / task / desired outcome | ✅ |
| Khác mechanism / role split (không chỉ UI/màu/wording) | ✅ |
| Mỗi option nói rõ User làm gì, AI làm gì, ai quyết định | ✅ |
| Có Expectation + Agency phù hợp + Evidence/Uncertainty + Control/Recovery | ✅ |
