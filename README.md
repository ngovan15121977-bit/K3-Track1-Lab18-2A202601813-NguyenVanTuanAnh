# Track 1 - Day 18: Multiple Prototypes — Human–AI Design

**Họ và tên:** Nguyễn Văn Tuấn Anh  
**Mã học viên (MHV):** 2A202601813  
**Nhóm:** Chicken Plus (2 thành viên)  
**Đồng đội:** Phạm Bá Huy (MHV: 2A202601132)  
**Case Study:** AI Support Radar trên nền tảng VLearn (Chẩn đoán & hỗ trợ bế tắc bài tập `useEffect`)  
**Repo GitHub:** `ngovan15121977-bit/K3-Track1-Lab18-2A202601813-NguyenVanTuanAnh`

---

## 1. Thông tin cá nhân và nhóm

- **MHV:** 2A202601813
- **Họ tên:** Nguyễn Văn Tuấn Anh
- **Tên nhóm:** Chicken Plus
- **Thành viên:**
  1. Nguyễn Văn Tuấn Anh — 2A202601813
  2. Phạm Bá Huy — 2A202601132
- **Case:** AI Support Radar / Diagnostic support khi học viên bị kẹt bài tập React Hooks (`useEffect`) trên VLearn

---

## 2. Hypothesis Problem (Day 18)

> Khi đang tự học lập trình trực tuyến một mình và gặp một bài tập hoặc khái niệm không hiểu (lỗi state trong React Hooks, hoặc bí hướng giải thuật), **học viên** gặp khó khăn trong việc **tự chẩn đoán đúng lỗ hổng kiến thức của mình và nhận giải thích đúng tầm hiểu biết để tiếp tục bài học**, vì **công cụ tự xoay sở hiện có (Google, ChatGPT/Gemini) hoặc đưa thẳng đáp án hoàn chỉnh khiến mất quá trình tư duy, hoặc giải thích bằng thuật ngữ mới ngoài tầm hiểu — trong khi không có ai bên cạnh để hỏi ngay như khi học trên lớp**, dẫn đến **mất 30–60 phút bế tắc, cảm giác nản lòng, và hổng kiến thức dây chuyền sang các bài học tiếp theo**.

**Evidence liên kết Day 17:**
- Teo (phỏng vấn bởi Huy): mất ~40 phút, trải qua 3 lần thử sai mới nhận ra thiếu kiến thức nền; hỏi ChatGPT thì phát sinh thêm thuật ngữ lạ.
- Thành (phỏng vấn bởi Tuấn Anh): nhận đáp án đầy đủ từ AI nhưng mất tư duy, phải tự “ép” AI giải thích từng bước.

**Điều vẫn chưa được chứng minh:** Claim “âm thầm bỏ học” (silent drop-out) chưa có evidence trực tiếp từ 2 Practice Notes.

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

- **Option chính chịu trách nhiệm:** Option A (Socratic Hints AI) — thiết kế luồng hỏi gợi mở, expectation micro-copy, control/recovery.
- **Shared work:**
  - Cùng Huy chốt Hypothesis Problem từ 2 Practice Notes Day 17 (Evidence Huddle).
  - Cùng xây Comparison Contract (user, situation, task, content fixture `useEffect` bug).
  - Tham gia Human–AI Design Pass cho cả 3 options (Expectation, Agency, Evidence/Uncertainty, Control & Recovery).
  - Viết / chuẩn hóa Design Sheet và các artifact Day 18.
  - Dùng chung **prototype web A/B/C** do Huy build (repo `phambahuycv/K4-Track1-Lab17-.../prototype`) — có 9 test cases + facilitator notes + reset path.
- **Facilitation & quan sát:** Facilitate 1 phiên A/B/C test với tester ngoài nhóm; ghi `prototype-feedback-note.md`.
- **Tổng hợp:** Đóng góp vào `group-feedback-synthesis.md` (pattern, Next Change, Still Unproven).

---

## 5. Prototype Feedback (tóm tắt)

**Phiên do tôi facilitate:** 1 tester ngoài nhóm trải nghiệm cả A → B → C với cùng task (sửa bug `useEffect` thiếu dependency array).

**Observation chính (xem chi tiết trong `prototype-feedback-note.md`):**
- Option A: Tester đọc hết 2–3 câu hỏi gợi mở, tự nhận ra thiếu dependency → sửa được code; cảm thấy “hiểu hơn” nhưng mất thời gian hơn.
- Option B: Nhanh, sát chỗ bôi đen; nhưng tester đôi khi không chắc mình nên bôi đen đoạn nào.
- Option C: Tin tưởng độ chính xác cao, nhưng không muốn chờ 30 phút khi đang “đang code dở”.

**Group Synthesis (xem `group-feedback-synthesis.md`):**
- **Next Change:** Kết hợp A + B — AI gợi mở Socratic + cho phép user bôi đen để “nhảy” sang giải thích phạm vi khi cần.
- **Still Unproven:** Chưa đủ data về việc user có bỏ cuộc khi AI đoán sai 2–3 lần liên tiếp; chưa test với user không quen React.

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
Track1_Day18_2A202601813_NguyenVanTuanAnh/
├── README.md
├── three-option-design-sheet.md
├── prototype-link.md
├── prototype-feedback-note.md
├── group-feedback-synthesis.md
├── ai-support-log.md
└── (tham khảo) Day18_CP1 / CP2 / CP3 — bản làm việc chi tiết các chặng
```

---

**Tự kiểm 5 Gate**

| Gate | Trạng thái |
|------|------------|
| 1. Evidence Continuity | Đạt — Hypothesis nối quote Day 17 + ghi rõ điều chưa biết |
| 2. Meaningful Options | Đạt — A/B/C khác mechanism & role split |
| 3. Human Control | Đạt — mỗi option có Expectation, Agency, Evidence/Uncertainty, Control & Recovery |
| 4. Test-ready | Cần cập nhật link prototype thật; Feedback Note đã có cấu trúc quan sát |
| 5. Learning | Đạt — có Feedback Note + Synthesis + Next Change + Still Unproven |
