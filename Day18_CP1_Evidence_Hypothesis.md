# Day 18 — Chặng 1: Evidence Huddle & Hypothesis Problem

**Nhóm:** Chicken Plus
**Thành viên:**
1. Phạm Bá Huy (MHV: 2A202601132) — phỏng vấn Teo (MHV: 2A202601814)
2. Nguyễn Văn Tuấn Anh (MHV: 2A202601813) — phỏng vấn Thành (MHV: 2A202601428)

**Case study:** AI Support Radar trên nền tảng học trực tuyến VLearn — Khảo sát trải nghiệm và bế tắc của Học viên (Learner).

> Lưu ý: nhóm chỉ có **2 thành viên** → thực tế là **2 Practice Notes** (không phải 3 như template chung của bài lab). Bảng evidence dưới đây dùng đúng 2 note thật, không bịa thêm note thứ ba.

---

## 1. Evidence huddle

| Practice Note | User đã thực sự làm/nói gì? (FACT) | Điều nhóm đang diễn giải (INTERPRETATION) |
|---|---|---|
| **1 — Teo** (React Hooks/`useEffect`, phỏng vấn: Huy) | *"Lần thứ ba tôi mới nhận ra là mình đang thiếu một kiến thức nào đó, chứ không đơn giản là sai code."* Xem lại video 3 lần trong ~20–30 phút trước khi nhận ra vấn đề không phải lỗi cú pháp. Sau đó Google từ khóa chung chung ("React state không cập nhật là như thế nào"), hỏi ChatGPT kèm đoạn code, mất ~40 phút tổng cộng để tự hiểu và giải quyết. | Nhóm diễn giải đây là hiện tượng "unconscious incompetence" — user không nhận biết bế tắc ngay lập tức, cần nhiều lần thử sai mới xác định đúng bản chất vấn đề (thiếu kiến thức nền, không phải lỗi code). |
| **2 — Thành** (Tree Algorithm/VSCode, phỏng vấn: Tuấn Anh) | *"Ngay cái hướng đi để phát triển bài toán mình cũng không thể nghĩ ra được... mình phải hỏi thêm những câu chi tiết hơn, như từng input, output cụ thể."* Hỏi ChatGPT/Gemini, nhận code đáp án hoàn chỉnh, sau đó chủ động hỏi tiếp để tự bóc tách logic từng bước. | Nhóm diễn giải Thành nhận biết bế tắc gần như *ngay lập tức* (khác Teo), và pain chính của Thành là AI cho đáp án đầy đủ làm "triệt tiêu tư duy" — không phải thiếu kiến thức nền cụ thể mà thiếu tiến trình dẫn dắt/tư duy từng bước. |
| **3** | *(không có — chỉ 2 thành viên, 2 Practice Notes thật)* | — |

### Thảo luận nhanh

- **Situation/behavior/workaround xuất hiện nhiều hơn một lần:**
  Cả Teo và Thành đều **hỏi ChatGPT/Gemini như bước xử lý chính**, và cả hai đều gặp thất bại từ AI ngoài — chỉ khác kiểu thất bại: Teo bị *rối thêm vì thuật ngữ mới ngoài tầm hiểu*, Thành bị *mất tư duy vì nhận đáp án đầy đủ ngay lập tức*. Đây là pattern lặp lại rõ nhất giữa hai note.

- **Evidence mâu thuẫn hoặc làm nhóm bất ngờ:**
  Teo cần 3 lần thử mới nhận ra mình bị kẹt (self-awareness trễ, "unconscious incompetence"); Thành nhận ra bế tắc gần như ngay lập tức nhưng bế tắc ở *hướng đi giải quyết*, không phải ở *một khái niệm cụ thể bị hiểu sai*. Đây không hẳn là mâu thuẫn, mà là **hai dạng "stuck" khác nhau** — nhóm cần cẩn thận không gộp chung thành một hiện tượng duy nhất khi thiết kế giải pháp.

- **Điều gì vẫn chỉ là suy đoán của nhóm:**
  Cả 2 note đều **không** có ai nói mình từng nghĩ đến việc bỏ học hẳn. Cụm từ "âm thầm bỏ học" (silent drop-out) xuất hiện trong Problem Hypothesis bản trước là **suy luận của nhóm**, chưa có evidence trực tiếp từ phỏng vấn — cần gắn nhãn rõ đây là giả thuyết, không phải finding đã kiểm chứng.

- **Hypothesis Problem nào đủ cụ thể để dùng làm điểm xuất phát:**
  Có. Cả 2 note đều cho đủ user, situation, job, barrier, consequence cụ thể để chốt Hypothesis Problem bên dưới.

---

## 2. Chốt Hypothesis Problem

**Cấu trúc:** Khi [situation], [user] gặp khó khăn trong việc [job] vì [barrier], dẫn đến [consequence].

### Hypothesis Problem nhóm tiếp tục

> Khi đang tự học lập trình trực tuyến một mình và gặp một bài tập hoặc khái niệm không hiểu (lỗi state trong React Hooks, hoặc bí hướng giải thuật Cây), **học viên** gặp khó khăn trong việc **tự chẩn đoán đúng lỗ hổng kiến thức của mình và nhận giải thích đúng tầm hiểu biết để tiếp tục bài học**, vì **công cụ tự xoay sở hiện có (Google, ChatGPT/Gemini) hoặc đưa thẳng đáp án hoàn chỉnh khiến mất quá trình tư duy, hoặc giải thích bằng thuật ngữ mới ngoài tầm hiểu — trong khi không có ai bên cạnh để hỏi ngay như khi học trên lớp**, dẫn đến **mất 30–60 phút bế tắc, cảm giác nản lòng, và hổng kiến thức dây chuyền sang các bài học tiếp theo**.

### Evidence ban đầu hỗ trợ giả thuyết

> Teo mất ~40 phút, trải qua 3 lần thử sai trước khi tự nhận ra vấn đề, và khi hỏi ChatGPT thì vấn đề phát sinh thêm 2–3 câu hỏi mới do thuật ngữ lạ. Thành nhận đáp án đầy đủ từ AI nhưng không hiểu bản chất, phải tự "ép" AI giải thích từng input/output. Cả hai đều dùng AI ngoài như bước xử lý đầu tiên/chính, và cả hai đều thất bại theo hai cách khác nhau của cùng một nguyên nhân gốc: AI không hiệu chỉnh mức độ giải thích theo đúng chỗ hổng kiến thức thật sự của người học.

### Điều vẫn chưa được chứng minh

> Chưa có evidence nào cho thấy tình trạng này dẫn đến "âm thầm bỏ học" (silent drop-out) — cả Teo và Thành đều xử lý xong vấn đề và tiếp tục học, không ai đề cập đến việc cân nhắc bỏ khóa. Cũng chưa rõ liệu pattern này có đúng với các môn học khác ngoài lập trình/giải thuật — nhóm hiện chỉ có 2 data point, cùng thuộc nhóm ngành kỹ thuật/lập trình.

---

## Tự kiểm — GATE 1 (Evidence continuity)

| Tiêu chí | Đạt? | Ghi chú |
|---|---|---|
| Có user | ✅ | Học viên tự học lập trình trực tuyến |
| Có situation | ✅ | Đang gặp bài tập/khái niệm không hiểu giữa buổi tự học một mình |
| Có job | ✅ | Tự chẩn đoán đúng lỗ hổng kiến thức + nhận giải thích đúng tầm hiểu để tiếp tục học |
| Có barrier | ✅ | AI ngoài đưa đáp án hoàn chỉnh HOẶC dùng thuật ngữ lạ; không có ai để hỏi ngay |
| Có consequence | ✅ | Mất 30–60 phút, nản lòng, hổng kiến thức dây chuyền |
| ≥1 observation Day 17 | ✅ | Quote trực tiếp của Teo và Thành (mục 1) |
| ≥1 điều chưa biết | ✅ | Claim "âm thầm bỏ học" chưa có evidence trực tiếp |

**→ CP1 đã qua Gate 1.** Sẵn sàng dùng làm điểm xuất phát cho Chặng 2.

---

## Phụ lục — 3 Solution Options đã chọn cho Chặng 2 (từ Solution Parking Lot của Huy)

Không lấy 3 ý tưởng ngẫu nhiên, mà chọn 3 ý tưởng đại diện cho 3 cách chia việc User–AI khác nhau trên cùng một Hypothesis Problem — từ AI chủ động dẫn dắt nhiều nhất, đến AI hỗ trợ có giới hạn, đến hoàn toàn không có AI (baseline con người).

*Bỏ qua "Peer Study Pods" và "Live TA Office Hours" vì cả hai đều lệch task (cần lịch hẹn trước, không giải quyết đúng khoảnh khắc "đang bị kẹt giữa bài học") — không cùng JTBD với Teo/Thành.*

| | **Option A — Socratic Hints AI** | **Option B — In-video Contextual Explainer** | **Option C — Fast SLA Q&A** |
|---|---|---|---|
| Nguồn (Parking Lot #) | #1 | #3 | #2 |
| User làm gì | Trả lời chuỗi câu hỏi dẫn dắt do AI đưa ra (không nhận đáp án ngay) | Bôi đen/tap vào đúng đoạn video, slide hoặc dòng code đang không hiểu | Gõ câu hỏi cụ thể về chỗ đang kẹt, gửi đi và chờ |
| AI làm gì | Chủ động suy đoán lỗ hổng kiến thức nền từ hành vi/lỗi, đặt câu hỏi gợi mở từng bước | Chỉ giải thích đúng phạm vi đoạn được chọn, không mở rộng sang khái niệm mới lạ | Không có AI. Trợ giảng người thật trả lời trong ≤30 phút |
| Ai giữ quyền quyết định | AI dẫn dắt trình tự câu hỏi; user quyết định khi nào dừng/bỏ qua hint | User quyết định phạm vi (chọn đúng chỗ); AI chỉ phản hồi trong phạm vi đó | Con người (TA) toàn quyền chẩn đoán và trả lời |
| Agency của AI | Cao — AI chủ động chẩn đoán và điều hướng | Trung bình — AI phản ứng theo lựa chọn của user, phạm vi hẹp | Không có AI — baseline con người, tốc độ cam kết (SLA) |
| Rủi ro cần test | AI đoán sai lỗ hổng → hint lạc đề, user mất niềm tin | User chọn sai đoạn (không biết mình thiếu gì để bôi đen) → explainer không chạm đúng vấn đề | 30 phút vẫn là "mất đà" so với đang code dở; user có chờ nổi không? |

**Comparison Contract (dùng chung cho cả A/B/C khi test):**
- **User context:** Học viên tự học lập trình trực tuyến một mình, ban đêm, không có ai bên cạnh — giống hoàn cảnh thật của Teo và Thành.
- **Task & content dùng chung:** Tái hiện đúng tình huống thật của Teo — đoạn code React `useEffect` có bug (state không cập nhật khi chuyển component), giống ví dụ giảng viên nhưng chạy không đúng. Cả A, B, C gắn vào cùng một đoạn video bài giảng + cùng đoạn code lỗi này.
- **Desired outcome cần quan sát:** User tự nhận diện được mình đang thiếu kiến thức gì (không chỉ sửa được lỗi), và có thể tiếp tục bài học mà không cần đáp án làm sẵn.
- **Behaviour cần ghi lại khi test:** user có đọc hết hint/explainer hay bỏ qua tìm đáp án tắt; user có tin tưởng gợi ý hay hoài nghi; với Option C, user có đủ kiên nhẫn chờ hết SLA hay bỏ giữa chừng.
