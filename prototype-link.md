# Prototype Links & Testing Guidelines

**Nhóm:** Chicken Plus  
**Thành viên:** Phạm Bá Huy & Nguyễn Văn Tuấn Anh

---

## 🔗 Liên kết Prototype

* **Link Prototype tổng hợp A/B/C (Figma/Interactive Web):** `https://figma.com/proto/vlearn-day18-chicken-plus-abc-testing`
* **Mã nguồn Repo Prototype:** `https://github.com/ngovan15121977-bit/K3-Track1-Lab18-2A202601813-NguyenVanTuanAnh`

---

## ⚙️ Shared Context & Task Details

* **Common Context Screen:** Trình học VLearn tích hợp IDE bài tập `useEffect` và video bài giảng React Hooks.
* **Data Fixture (Code lỗi dùng chung):**
  ```javascript
  useEffect(() => {
    fetchUserData(userId).then(data => setUser(data));
  }, []); // Test case #2 Fail: thiếu userId