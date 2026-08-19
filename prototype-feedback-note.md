# Group Feedback Synthesis — Day 18

**Nhóm:** Chicken Plus  
**Thành viên:** Nguyễn Văn Tuấn Anh (MHV: `2A202601813`), Phạm Bá Huy (MHV: `2A202601132`)  
**Nguồn:** 3 Feedback Notes độc lập từ 3 Tester ngoài nhóm:
1. **Hoàng Văn Thành** (MHV: `2A202601428`) — Tester 1
2. **Bùi Hữu Nghĩa** (MHV: `2A202601880`) — Tester 2
3. **Nguyễn Quang Minh** (MHV: `2A202601955`) — Tester 3  
**Case:** AI Support Radar trên nền tảng VLearn (`useEffect` React Hooks)  
**Ngày cập nhật:** 19/08/2026  

---

## 1. Bảng Tổng Hợp Đối Chiếu 3 Feedback (Cross-Feedback Matrix)

| Tiêu chí | Feedback 1 (Hoàng Văn Thành - 2A202601428) | Feedback 2 (Bùi Hữu Nghĩa - 2A202601880) | Feedback 3 (Nguyễn Quang Minh - 2A202601955) | Pattern & Khác biệt chung |
| :--- | :--- | :--- | :--- | :--- |
| **Profile Tester** | Học viên có kinh nghiệm, thích bài toán nâng cao. | Học viên trực quan, chú trọng tốc độ sửa lỗi. | Học viên tự học, thích phương pháp gợi mở tư duy. | Đại diện cho các mức độ tiếp thu và phong cách học khác nhau. |
| **First Action** | Đọc Test Runner, kiểm tra cấu trúc code xung quanh. | Chạy Test Runner, bôi đen thử dòng lỗi 15. | Bấm ngay *“Cần gợi ý tư duy”*, đọc kỹ micro-copy. | **100% Tester** nhìn vào bảng lỗi Test Case trước khi dùng AI. |
| **Đánh giá Option A** | AI bị giới hạn, muốn hỏi rộng ra các đoạn code xung quanh. | Thấy hay nhưng mắt phải đảo qua lại để tìm AI phản hồi. | **Rất thích ý tưởng gợi mở**, muốn lấy giải pháp áp dụng ngay. | Option A tạo ấn tượng mạnh về giá trị tư duy lâu dài. |
| **Đánh giá Option B** | Thấy nhanh nhưng chỉ giải quyết được lỗi cục bộ. | **Đánh giá rất OK**, AI giải thích dễ hiểu, tự hiểu ra đáp án. | Dễ hiểu nhưng sợ nếu không biết sai ở đâu thì không bôi đen được. | Option B xuất sắc về độ tức thì và tính thực dụng. |
| **Friction / Vấn đề UI** | Chưa có form feedback, testcase chưa khai thác hết chức năng. | **UI hơi khó nhìn** để nhận biết vị trí AI vừa phản hồi. | **Không biết phải trượt (scroll) xuống** khi AI trả lời dài. | **Điểm nghẽn lớn nằm ở UI/UX hiển thị & điều hướng nội dung.** |
| **Đề xuất nâng cấp** | Thêm Form Feedback, ngữ cảnh khó hơn, hỏi được code liên quan. | Làm nổi bật khu vực AI trả lời để dễ quan sát hơn. | Bổ sung **luồng tin nhắn chat liên tục (message thread)**. | Cần hội thoại tự nhiên, có feedback loop và visual cue rõ ràng. |
| **Lựa chọn & Trade-off** | Muốn mở rộng scope $\leftrightarrow$ Sợ AI lan man. | Chọn **B** (nhanh, dễ hiểu) $\leftrightarrow$ Cần sửa UI cho dễ nhìn. | Chọn **A** (hiểu sâu) $\leftrightarrow$ Cần fix lỗi scroll & làm dạng chat. | **Pattern:** Không ai chọn C; A và B bổ sung hoàn hảo cho nhau. |

---

## 2. Các Pattern Chung & Khác Biệt Giữa 3 Phiên

### 2.1. Pattern chung (Tín hiệu lặp lại)
1. **Giá trị cốt lõi của việc gợi ý tư duy (Socratic AI) được công nhận mạnh:** Nguyễn Quang Minh cực kỳ hào hứng muốn áp dụng thực tế, Hoàng Văn Thành và Bùi Hữu Nghĩa đều ghi nhận AI giải thích đúng trọng tâm bản chất thay vì quăng code làm sẵn.
2. **Option B (Contextual Explainer) là cứu cánh tức thì:** Giải thích trực diện, giúp người học hiểu nhanh vấn đề (như Bùi Hữu Nghĩa đã pass test rất nhanh).
3. **Sự thất thế của Option C:** Cả 3 Tester đều bỏ qua Option C cho tình huống tự học đêm do độ trễ 30 phút làm gãy đà học tập.
4. **Vấn đề giao diện (UI/UX) là rào cản tương tác lớn nhất:** Bùi Hữu Nghĩa khó nhìn thấy vùng AI phản hồi, Nguyễn Quang Minh không biết phải scroll xuống để đọc tiếp.

### 2.2. Khác biệt theo trình độ người học
* **Người học nâng cao (Hoàng Văn Thành):** Cảm thấy "chật chội" khi AI bị khóa chặt trong một đoạn code lỗi, mong muốn ngữ cảnh khó hơn và khả năng trao đổi về các hàm xung quanh.
* **Người học cơ bản (Bùi Hữu Nghĩa & Nguyễn Quang Minh):** Cần sự chỉ dẫn từng bước rõ ràng, giao diện trực quan và cơ chế cuộn/tin nhắn tự nhiên để không bị ngợp.

---

## 3. Next Change (Quyết Định Cải Tiến Cốt Lõi)

**Quyết định nhóm chốt:**

> 🎯 **Nâng cấp Hệ Thống Hybrid A+B với Giao Diện Chat Message Liên Tục & Trực Quan Hóa UI:**
> 1. **Chuyển Option A thành Luồng Chat Message liên tục:** Thay thế các khối tĩnh bằng luồng tin nhắn hội thoại đối thoại từng bước, tích hợp hiệu ứng hiển thị mượt mà và **tính năng Auto-Scroll xuống tin nhắn mới nhất**.
> 2. **Tối ưu hóa UI Vùng Phản Hồi:** Tăng độ tương phản, thêm hiệu ứng highlight và biểu tượng trạng thái rõ ràng để người học nhận biết ngay khi AI trả lời (giải quyết phản hồi của Bùi Hữu Nghĩa).
> 3. **Tích hợp Form Feedback trực tiếp:** Bổ sung nút đánh giá chất lượng gợi ý (Thumbs up/down + ô góp ý nhanh) ngay dưới mỗi phản hồi của AI (theo đề xuất của Hoàng Văn Thành).
> 4. **Giữ Option B như công cụ bổ trợ tại chỗ:** Cho phép người học bôi đen bất kỳ đoạn code nào để xem giải thích nhanh dạng popup mà không làm mất luồng chat chính.

---

## 4. Evidence Dẫn Tới Quyết Định Này

* **Phản hồi Nguyễn Quang Minh (2A202601955):** Khen ý tưởng gợi mở rất hay nhưng gặp lỗi không biết phải trượt (scroll) xuống và mong muốn có đoạn phản hồi liên tục dạng message $\rightarrow$ Căn cứ trực tiếp để làm Auto-Scroll và Chat Message Thread.
* **Phản hồi Bùi Hữu Nghĩa (2A202601880):** Đánh giá Option B giải thích rất dễ hiểu, hiểu được vấn đề và đáp án nhưng phàn nàn UI hơi khó nhìn để check AI phản hồi $\rightarrow$ Căn cứ để tinh chỉnh vùng hiển thị UI nổi bật hơn và giữ vững Option B.
* **Phản hồi Hoàng Văn Thành (2A202601428):** Phản hồi đề tài và câu trả lời AI bị giới hạn, test case chưa phát huy hết chức năng và đề xuất tạo form feedback $\rightarrow$ Căn cứ để bổ sung Form Feedback loop và chuẩn bị mở rộng test cases.

---

## 5. Still Unproven (Điều Vẫn Chưa Được Chứng Minh)

1. **Rủi ro phân tâm khi mở rộng Scope:** Nếu cho phép AI trả lời mở rộng sang các đoạn code xung quanh (theo ý Hoàng Văn Thành), liệu AI có làm người học phân tâm khỏi mục tiêu cốt lõi của bài học hay không?
2. **Cognitive Load trong luồng Chat liên tục:** Giao diện tin nhắn liên tục có khiến người học có cảm giác "lười đọc code" và chỉ chăm chú chat với AI hay không?
3. **Tác động dài hạn (Long-term Retention):** Việc học qua gợi ý tư duy dạng chat có thực sự giúp người học nhớ lâu hơn sau 1-2 tuần so với việc đọc tài liệu truyền thống hay không?

---

## 6. Tự Kiểm — GATE 5: Learning, Not Praise

| Tiêu chí | Trạng thái | Minh chứng cụ thể |
| :--- | :---: | :--- |
| **Có đủ Feedback Notes độc lập từ 3 Tester** | ✅ Đạt | Đầy đủ dữ liệu chi tiết từ Hoàng Văn Thành, Bùi Hữu Nghĩa, Nguyễn Quang Minh. |
| **Nêu bật được Pattern và Khác biệt cụ thể** | ✅ Đạt | Phân tích rõ khác biệt giữa người học nâng cao vs. cơ bản và các lỗi UI chung. |
| **Chốt một Next Change khả thi, gắn liền với Evidence** | ✅ Đạt | Chốt nâng cấp Chat Message liên tục + Auto Scroll + UI Highlight + Form Feedback. |
| **Xác định trung thực điều STILL UNPROVEN** | ✅ Đạt | Thừa nhận chưa kiểm chứng được Cognitive Load và tác động dài hạn. |
| **Không dùng lời khen sáo rỗng** | ✅ Đạt | Mọi kết luận đều bắt nguồn từ hành vi thực tế, chỗ dừng và trade-off của 3 tester. |

**→ Đã hoàn thành tổng hợp nhóm và đạt 100% chuẩn Gate 5.**
