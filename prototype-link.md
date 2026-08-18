# Prototype Links & Testing Guidelines

**Nhóm:** Chicken Plus  
**Thành viên:** Phạm Bá Huy & Nguyễn Văn Tuấn Anh  
**Case:** AI Support Radar — VLearn / `useEffect` bug

---

## 🔗 Liên kết Prototype A / B / C

**Prototype web interactive (chung nhóm — build chính bởi Phạm Bá Huy):**

| Mục | Link |
|-----|------|
| **Folder prototype trên GitHub** | https://github.com/phambahuycv/K4-Track1-Lab17-2A202601132-PhamBaHuy/tree/main/prototype |
| **Repo chứa prototype** | https://github.com/phambahuycv/K4-Track1-Lab17-2A202601132-PhamBaHuy |
| **Cách mở** | Clone repo → mở `prototype/index.html` bằng Chrome/Edge, hoặc chạy `npx -y serve prototype` |

| Option | Tên | Critical interaction | Control / Recovery |
|--------|-----|----------------------|--------------------|
| **A** | Socratic Hints AI (AI-Led) | Nút “💡 Cần gợi ý tư duy” → câu hỏi gợi mở nhiều lượt | Đổi câu hỏi / Hint không đúng ý / 🚨 Xem đáp án chi tiết |
| **B** | Contextual Explainer (User-Led) | Bôi đen dòng code 15 (`}, []);`) hoặc mốc video 04:12 → “🔍 Giải thích đoạn này” | Cho ví dụ / Giải thích ngắn hơn / ✕ Đóng & Tự sửa |
| **C** | Fast SLA Q&A (Human TA) | “🙋 Gửi câu hỏi cho TA” → ticket + SLA ≤ 30 phút | Bổ sung ghi chú / Đã tự sửa được (Hủy) / Học tạm Bài 13 |

**9 Test Cases** (3 option × 3 scenario: Happy Path / Uncertainty / Control-Recovery) nằm trong:
- `prototype/README.md` của repo Huy
- Thanh “🧪 9 Test Cases” + guide bar trên giao diện prototype

---

## ⚙️ Shared Context & Task (dùng chung khi test)

- **Context:** Tự học trực tuyến một mình buổi tối bài *“React Hooks: useEffect & Data Fetching”*.
- **Data Fixture (code lỗi):**

```javascript
useEffect(() => {
  fetchUserData(userId).then(data => setUser(data));
}, []); // Test Case #2 FAILED: State user không đổi khi props thay đổi
```

- **Task cho tester (outcome, không chỉ nút):**  
  “Code đang bị lỗi Test Case #2. Hãy dùng lần lượt từng phương án (A → B → C) để tìm cách **hiểu nguyên nhân** và **sửa code** để vượt qua bài test.”

- **Desired outcome cần quan sát:**  
  Tester có tự nhận ra thiếu dependency array không? Có hiểu bản chất không? Có muốn tiếp tục học không?

---

## 👀 Observation Focus (khi facilitate)

Ghi **hành vi trước**, diễn giải sau (tối đa 5 điểm):

1. **First action** — bấm gì đầu tiên?
2. **Hesitation / misunderstanding** — chỗ dừng, do dự, hiểu sai.
3. **Evidence đọc hay bỏ qua** — có đọc gợi ý / giải thích / SLA không?
4. **Correction / recovery** — dùng nút đổi hướng, đóng, hủy ticket, xem đáp án không?
5. **Option chọn + trade-off** — sau cả 3, chọn A/B/C? Vì sao? Đánh đổi gì?

**Luật facilitation (theo đề):**
- Tester tự điều khiển; không narrate icon.
- Cùng một task cho A/B/C.
- Không hỏi “Bạn thích không?”.
- Khi tester hỏi cách dùng → “Theo bạn, nó nên hoạt động như thế nào?”

**Ba câu cứu hộ:**
- “Bạn cứ nói to suy nghĩ của mình nhé.”
- “Bạn sẽ làm gì tiếp theo?”
- “Theo bạn, nó nên hoạt động như thế nào?”

---

## Ghi chú build & reset

- Common context ~70% (video 04:12, editor, test suite, task).
- Chỉ critical interaction khác rõ giữa A/B/C.
- Nút **🔄 Reset Scenario** trên prototype để quay về trạng thái ban đầu (code lỗi, Test #2 FAIL, xóa ticket/dialog).
- Facilitator Notes: bật/tắt bằng nút “📋 Facilitator Notes” (không hiện cho tester).
