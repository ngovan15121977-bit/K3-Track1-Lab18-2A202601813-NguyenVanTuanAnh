# Prototype Feedback Note — Phiên A/B/C

**Facilitator:** Nguyễn Văn Tuấn Anh (MHV: 2A202601813)  
**Nhóm:** Chicken Plus  
**Tester:** Người ngoài nhóm (học viên / bạn cùng ngành, đã từng học React cơ bản)  
**Ngày test:** Day 18 (sau buổi lab)  
**Thứ tự trải nghiệm:** A → B → C (cùng context, task, content fixture)

---

## 1. Context & Task đã dùng

- **Context:** Tự học ban đêm, IDE VLearn + video React Hooks, test case #2 fail.
- **Task:** Tìm nguyên nhân state `user` không cập nhật khi `userId` đổi và sửa để pass test.
- **Code fixture:** `useEffect(..., [])` thiếu `userId`.

---

## 2. Quan sát hành vi (Fact trước, diễn giải sau)

### Option A — Socratic Hints AI

| Loại | Ghi nhận |
|------|----------|
| **Hành vi** | Tester bấm “Cần gợi ý tư duy”. Đọc câu hỏi 1 (về dependency). Gõ trả lời ngắn. Đọc câu hỏi 2. Sau đó tự sửa `}, [userId]);`. Không bấm “Xem đáp án”. |
| **Quote gần đúng** | “Câu hỏi này làm mình nghĩ lại đúng chỗ mình hay quên.” |
| **Thời gian cảm nhận** | Lâu hơn B, nhưng “cảm giác hiểu hơn”. |
| **Trade-off tester nói** | “Hiểu sâu nhưng nếu đang vội deadline thì hơi mất thời gian.” |

### Option B — Contextual Explainer

| Loại | Ghi nhận |
|------|----------|
| **Hành vi** | Tester bôi đen đoạn `}, []);` → bấm “Giải thích đoạn này”. Đọc pop-up. Sửa code khá nhanh. Có thử bôi đen chỉ 1 từ (`setUser`) → thấy cảnh báo “vùng chọn quá ngắn”. |
| **Quote gần đúng** | “Nhanh và đúng chỗ mình khoanh. Nhưng lúc đầu mình không chắc nên bôi đen dòng nào.” |
| **Thời gian cảm nhận** | Nhanh nhất trong 3 option. |
| **Trade-off** | “Nếu mình chọn sai đoạn thì giải thích sẽ lệch.” |

### Option C — Fast SLA Q&A

| Loại | Ghi nhận |
|------|----------|
| **Hành vi** | Tester điền form, paste code, gửi ticket. Nhìn đồng hồ SLA 30:00. Không ngồi chờ; chuyển sang “Học bài tiếp” / hỏi “có cách nào nhanh hơn không?”. |
| **Quote gần đúng** | “Tin TA hơn AI, nhưng 30 phút lúc đang code dở là dài. Mình sẽ tìm cách khác trước.” |
| **Trade-off** | Độ chính xác cao ↔ mất đà học. |

---

## 3. So sánh sau khi trải nghiệm cả 3

- **Nếu chỉ được giữ 1 option:** Tester nghiêng về **B** khi cần sửa nhanh; nghiêng về **A** khi muốn “hiểu để lần sau không sai”.
- **Không chọn C** cho tình huống “đang kẹt giữa bài ban đêm” vì độ trễ.
- **Pattern:** User muốn vừa **nhanh** vừa **không bị triệt tiêu tư duy**. A và B bổ sung nhau hơn là loại trừ.

---

## 4. Ghi chú facilitator

- Không giải thích trước mechanism; chỉ đưa task và để tester tự khám phá.
- Quan sát ưu tiên hành vi (bấm gì, bỏ qua gì, sửa code khi nào) hơn là câu “bạn thích option nào”.
- Một điểm bất ngờ: với B, tester cần gợi ý nhẹ về “bôi đen cả dòng dependency” — cho thấy risk “user không biết mình thiếu gì để khoanh vùng” là có thật (khớp hypothesis).

---

## 5. Liên kết evidence Day 17

- Hành vi “mất thời gian thử sai rồi mới nhận ra thiếu kiến thức” (Teo) → Option A hỗ trợ đúng pain này.
- Hành vi “AI đưa đáp án đầy đủ → mất tư duy” (Thành) → Option A cố ý không cho đáp án sẵn; Option B giới hạn phạm vi.
- Option C là baseline con người để đo trade-off thời gian vs độ tin cậy.
