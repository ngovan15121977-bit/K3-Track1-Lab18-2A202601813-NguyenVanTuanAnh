# Prototype Links & Testing Guidelines

**Nhóm:** Chicken Plus  
**Thành viên:** Phạm Bá Huy & Nguyễn Văn Tuấn Anh  
**Case:** AI Support Radar — VLearn / `useEffect` bug

---

## 🔗 Liên kết Prototype A / B / C

> **Lưu ý quan trọng:** Cập nhật link thật sau khi build (Figma / Web / giấy / Loom demo).  
> Hiện tại dùng khung mô tả trạng thái tối thiểu để tester trải nghiệm được khác biệt mechanism.

| Option | Mô tả micro-prototype (2–3 trạng thái) | Link / Artifact |
|--------|----------------------------------------|-----------------|
| **A — Socratic Hints** | (1) Màn IDE + test case fail → nút “Cần gợi ý tư duy” <br>(2) AI hiện câu hỏi 1 → user trả lời <br>(3) Câu hỏi 2 / nút “Đổi hướng” / “Xem đáp án” | *[Điền link Figma / demo]* |
| **B — Contextual Explainer** | (1) Code + video bài giảng <br>(2) User bôi đen dòng `}, []);` → pop-up “Giải thích đoạn này” <br>(3) Giải thích ngắn + nút “Cho ví dụ” / Đóng | *[Điền link Figma / demo]* |
| **C — Fast SLA Q&A** | (1) Form gửi ticket (mô tả + paste code) <br>(2) Màn “Đã gửi — SLA 30:00” + trạng thái <br>(3) Nút “Đã tự sửa được” / “Học bài tiếp” | *[Điền link Figma / demo]* |

**Link tổng hợp (khi có):**  
`[Dán link Figma proto / Web demo / Drive chứa`

**Mã nguồn / board chung (nếu có):**  
Repo này hoặc board nhóm.

---

## ⚙️ Shared Context & Task (dùng chung khi test)

- **Context screen:** Trình học VLearn tích hợp IDE bài tập + video bài giảng React Hooks.
- **Data Fixture (code lỗi dùng chung):**

```javascript
useEffect(() => {
  fetchUserData(userId).then(data => setUser(data));
}, []); // Test case #2 Fail: thiếu userId trong dependency array
```

- **Task cho tester:**  
  “Bạn đang làm bài tập `useEffect`. Test case #2 báo fail vì state `user` không cập nhật khi `userId` đổi. Hãy dùng lần lượt A, rồi B, rồi C để tìm cách hiểu và sửa lỗi. Không cần hoàn thành full product — chỉ trải nghiệm critical interaction.”

- **Desired outcome cần quan sát:**  
  Tester có tự nhận ra thiếu dependency array không? Có hiểu bản chất không? Có muốn tiếp tục học không?

---

## 👀 Observation Focus (khi facilitate)

Ghi **hành vi trước**, diễn giải sau:

1. Tester có đọc hết gợi ý / giải thích hay bỏ qua tìm đáp án tắt?
2. Với A: có trả lời câu hỏi AI hay nhảy sang “Xem đáp án”?
3. Với B: có biết bôi đen đoạn nào không? Có yêu cầu “Cho ví dụ” không?
4. Với C: có kiên nhẫn chờ / hay bỏ ticket để làm việc khác?
5. Sau cả 3: chọn option nào nếu chỉ được giữ 1? Vì sao? Trade-off là gì?

---

## Ghi chú build

- Mỗi option chỉ cần **2–3 trạng thái** quanh critical interaction.
- Dùng chung visual components (IDE giả, code fixture, nút) để so sánh fair.
- Không cần full product; prototype vừa đủ để tester tự dùng được cả A/B/C.
