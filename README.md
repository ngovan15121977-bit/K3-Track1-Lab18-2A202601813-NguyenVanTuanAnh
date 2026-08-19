# Track 1 - Day 18: Multiple Prototypes — Human–AI Design

**Họ và tên:** Phạm Bá Huy  
**Mã học viên (MHV):** 2A202601132  
**Nhóm:** Chicken Plus (2 thành viên)  
**Đồng đội:** Nguyễn Văn Tuấn Anh (MHV: 2A202601813)  
**Case Study:** AI Support Radar trên nền tảng VLearn (Chẩn đoán & hỗ trợ bế tắc bài tập `useEffect`)  
**Repo GitHub:** `phambahuycv/K4-Track1-Lab17-2A202601132-PhamBaHuy`

---

## 1. Thông tin cá nhân và nhóm

- **MHV:** 2A202601132
- **Họ tên:** Phạm Bá Huy
- **Tên nhóm:** Chicken Plus
- **Thành viên:**
  1. Phạm Bá Huy — 2A202601132 (Lead / Technical & Prototyping)
  2. Nguyễn Văn Tuấn Anh — 2A202601813 (Design & Research)
- **Case:** AI Support Radar / Diagnostic support khi học viên bị kẹt bài tập React Hooks (`useEffect`) trên VLearn

---

## 2. Hypothesis Problem (Day 18)

> Khi đang tự học lập trình trực tuyến một mình và gặp một bài tập hoặc khái niệm không hiểu (lỗi state trong React Hooks, hoặc bí hướng giải thuật), **học viên** gặp khó khăn trong việc **tự chẩn đoán đúng lỗ hổng kiến thức của mình và nhận giải thích đúng tầm hiểu biết để tiếp tục bài học**, vì **công cụ tự xoay sở hiện có (Google, ChatGPT/Gemini) hoặc đưa thẳng đáp án hoàn chỉnh khiến mất quá trình tư duy, hoặc giải thích bằng thuật ngữ mới ngoài tầm hiểu — trong khi không có ai bên cạnh để hỏi ngay như khi học trên lớp**, dẫn đến **mất 30–60 phút bế tắc, cảm giác nản lòng, và hổng kiến thức dây chuyền sang các bài học tiếp theo**.

**Evidence liên kết Day 17:**
- Teo (phỏng vấn bởi Huy): mất ~40 phút, trải qua 3 lần thử sai mới nhận ra thiếu kiến thức nền; hỏi ChatGPT thì phát sinh thêm thuật ngữ lạ.
- Thành (phỏng vấn bởi Tuấn Anh): nhận đáp án đầy đủ từ AI nhưng mất tư duy, phải tự “ép” AI giải thích từng bước.

**Điều vẫn chưa được chứng minh:** Claim “âm thầm bỏ học” (silent drop-out) chưa có evidence trực tiếp từ các Practice Notes.

---

## 3. Three Solution Options

| Option | Tên | Cơ chế chính | Link prototype |
|--------|-----|--------------|----------------|
| **A** | Socratic Hints AI | AI chẩn đoán bug → chuỗi câu hỏi gợi mở, không cho đáp án sẵn | [prototype/](https://github.com/phambahuycv/K4-Track1-Lab17-2A202601132-PhamBaHuy/tree/main/prototype) |
| **B** | Contextual Explainer | User bôi đen đoạn code/video → AI giải thích đúng phạm vi được chọn | Cùng link trên (tab Option B) |
| **C** | Fast SLA Q&A | Gửi ticket cho TA người thật, cam kết phản hồi ≤ 30 phút (0% generative AI) | Cùng link trên (tab Option C) |

**Prototype chung nhóm:**  
https://github.com/phambahuycv/K4-Track1-Lab17-2A202601132-PhamBaHuy/tree/main/prototype  

Cách mở: clone repo → mở `prototype/index.html` bằng trình duyệt (hoặc `npx -y serve prototype`).  
Có sẵn **9 Test Cases** (3 option × Happy Path / Uncertainty / Control-Recovery). Chi tiết: `prototype-link.md` + `prototype/README.md` trong repo Huy.

Chi tiết so sánh mechanism, agency, trade-off và Human–AI Decision Table: xem file `three-option-design-sheet.md`.

---

## 4. Đóng góp của tôi trong nhóm

- **Lập trình & Xây dựng Prototype chung (Technical & Prototyping Lead):**
  - Trực tiếp thiết kế và lập trình toàn bộ **khung giao diện 70% Shared Core** (VLearn Platform Layout, Monaco Editor `UserProfile.jsx`, Video Player mốc `04:12`, và Test Runner mô phỏng).
  - Hiện thực hóa 3 luồng Critical Interaction cho cả 3 Option (Option A: Socratic Hints AI đối thoại từng bước; Option B: Contextual Explainer bôi đen code/video pop-up; Option C: Fast SLA Q&A tạo ticket có bộ đếm ngược SLA 30 phút).
  - Tích hợp **bộ chuyển đổi tab A/B/C**, nút **Reset Scenario**, và xây dựng thanh điều hướng trực tiếp **9 Test Cases** chuẩn mực để phục vụ kiểm thử.
- **Shared work (Cùng Tuấn Anh):**
  - Cùng phân tích dữ liệu Day 17 (Evidence Huddle), xác định các khoảng trống dữ liệu và thống nhất chốt **Hypothesis Problem**.
  - Xây dựng **Comparison Contract** đảm bảo giữ nguyên 70% nền tảng (Target User, Situation, Task, Content Fixture `useEffect`).
  - Tham gia **Human–AI Design Pass** cho cả 3 options (xác định Expectation, Agency Act/Ask/Don't Act, Evidence & Uncertainty, Control & Recovery).
  - Xây dựng các tài liệu Chặng 1 đến Chặng 6 (`CP1_D18.md` đến `CP6_D18.md`) và hoàn thiện `three-option-design-sheet.md`.
- **Facilitation & Quan sát thực địa:**
  - Chuẩn bị kịch bản và chủ trì phiên kiểm thử thực tế với Tester ngoài nhóm (Hoàng Văn Thành, Bùi Hữu Nghĩa, Nguyễn Quang Minh) tuân thủ nghiêm ngặt 6 Luật Facilitation và 3 câu cứu hộ.
  - Ghi nhận biên bản quan sát hành vi Fact-First và tổng hợp 4 tầng tư duy (Observed / Interpreted / Decided / Still Unproven) vào file `prototype-feedback-note.md`.
- **Tổng hợp & Chốt định hướng cải tiến nhóm:**
  - Cùng nhóm xây dựng `group-feedback-synthesis.md`, phân tích Cross-Feedback Matrix, xác định các điểm nghẽn UI (lỗi cuộn trang, vùng AI phản hồi khó nhìn) và chốt **Next Change** (Hybrid A+B dạng Chat Message Streaming liên tục + Auto-Scroll + Form Feedback).

---

## 5. Prototype Feedback (tóm tắt)

**Tổng hợp từ 3 Tester ngoài nhóm (Hoàng Văn Thành, Bùi Hữu Nghĩa, Nguyễn Quang Minh):**

**Observation chính (xem chi tiết trong `prototype-feedback-note.md`):**
- **Tester 1 (Hoàng Văn Thành - 2A202601428):** Đánh giá AI trả lời đúng trọng tâm nhưng bị giới hạn trong 1 bug hẹp; mong muốn ngữ cảnh khó hơn, hỏi được code xung quanh và đề xuất thêm Form Feedback.
- **Tester 2 (Bùi Hữu Nghĩa - 2A202601880):** Khen Option B giải thích rất dễ hiểu, giúp hiểu bản chất và tự pass test nhanh; phản hồi UI hơi khó nhìn để check vị trí AI phản hồi.
- **Tester 3 (Nguyễn Quang Minh - 2A202601955):** Rất thích ý tưởng gợi mở tư duy (Option A), muốn mang đi áp dụng; gặp lỗi UI không biết phải trượt (scroll) xuống; đề xuất luồng tin nhắn chat liên tục.

**Group Synthesis (xem `group-feedback-synthesis.md`):**
- **Next Change:** Nâng cấp giải pháp Hybrid A+B: Chuyển Option A sang dạng **Chat Message liên tục có Auto-Scroll**, làm nổi bật vùng AI phản hồi, tích hợp **Form Feedback** đánh giá gợi ý và giữ Option B làm công cụ giải thích tức thì tại chỗ.
- **Still Unproven:** Cần kiểm chứng rủi ro phân tâm khi AI mở rộng phạm vi giải thích code xung quanh và tải nhận thức (cognitive load) khi học viên chat liên tục với AI.

---

## 6. AI Support Log

Xem file riêng `ai-support-log.md`.

Tóm tắt:
- AI dùng để: gợi ý cấu trúc markdown, canned code fixture `useEffect`, rà soát 3 options có khác mechanism thật sự không, gợi ý từ khóa Agency (Act/Ask/Don’t Act).
- Không dùng AI để bịa quote, observation hay feedback.
- Phần feedback và reflection là từ phiên test thật / tổng hợp nhóm.

---

## Cấu trúc repo

```text
K4-Track1-Lab17-2A202601132-PhamBaHuy/
├── README.md
├── three-option-design-sheet.md
├── prototype-link.md
├── prototype-feedback-note.md
├── group-feedback-synthesis.md
├── ai-support-log.md
├── prototype/ (index.html, style.css, app.js, README.md)
└── interview/ (CP1_D18.md, CP2_D18.md, CP3_D18.md, CP4_D18.md, CP5_D18.md, CP6_D18.md, notes.md, recording-link.md)
```

---

**Tự kiểm 5 Gate**

| Gate | Trạng thái |
|------|------------|
| 1. Evidence Continuity | Đạt — Hypothesis nối quote Day 17 + ghi rõ điều chưa biết |
| 2. Meaningful Options | Đạt — A/B/C khác mechanism & role split |
| 3. Human Control | Đạt — mỗi option có Expectation, Agency, Evidence/Uncertainty, Control & Recovery |
| 4. Test-ready | Đạt — Prototype web A/B/C hoàn chỉnh kèm 9 Test Cases + Reset Path |
| 5. Learning | Đạt — Có 3 Feedback Notes + Synthesis + Next Change + Still Unproven |
