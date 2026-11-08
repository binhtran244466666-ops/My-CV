# Nhật ký AI

## Mục đích

Ghi lại các thay đổi được AI hỗ trợ thực hiện, phạm vi ảnh hưởng, minh chứng và kết quả kiểm tra của dự án My-CV.

## Lịch sử thay đổi

### 08/11/2026 — Đồng bộ hồ sơ phát hành với bản giao diện mới

- **Phạm vi:** Cập nhật toàn bộ tài liệu bàn giao và ảnh minh chứng theo mã nguồn mới nhất trên nhánh `main`.
- **Mã nguồn đối chiếu:**
  - [`index.html`](../index.html)
  - [`styles.css`](../assets/css/styles.css)
- **Các thay đổi được ghi nhận:**
  - Chuyển các tương tác chính sang HTML/CSS thuần, không cần tệp JavaScript runtime.
  - Bổ sung công tắc ngày/đêm bằng checkbox và CSS `:has()`.
  - Bổ sung lọc kỹ năng, làm nổi bật dự án liên quan và nút khôi phục “Hiện tất cả”.
  - Bổ sung hộp chi tiết dự án mở bằng `:target`.
  - Bổ sung chọn dự án để so sánh bằng checkbox.
  - Bổ sung form liên hệ nhanh với kiểm tra bắt buộc native của trình duyệt và thanh tiến độ.
  - Bổ sung hiệu ứng responsive, animation và hỗ trợ `prefers-reduced-motion`.
- **Tài liệu cập nhật:**
  - [`RELEASENOTE.md`](./RELEASENOTE.md)
  - [`test_report.md`](./test_report.md)
- **Minh chứng cập nhật:**
  - [`responsive-mobile.png`](./screenshots/responsive-mobile.png) — viewport 390×844.
  - [`responsive-tablet.png`](./screenshots/responsive-tablet.png) — viewport 768×1024.
  - [`responsive-desktop.png`](./screenshots/responsive-desktop.png) — viewport 1440×900.
- **Kết quả kiểm tra:** Máy chủ cục bộ trả HTTP 200; kiểm tra trình duyệt xác nhận tiêu đề trang, 4 section chính, 4 hộp chi tiết, công tắc theme, lọc kỹ năng, liên kết chi tiết và validation form.

### 08/11/2026 — Chụp lại bộ screenshot chuyên nghiệp

- **Phạm vi:** Thay mới ba ảnh responsive bằng ảnh full-page từ phiên bản đang chạy trên máy chủ cục bộ.
- **Thiết lập chụp:** Mobile 390px, tablet 768px và desktop 1440px; tắt animation/transition trong lúc chụp, ẩn scrollbar và giữ trang ở trạng thái giao diện tối mặc định.
- **Tệp cập nhật:**
  - [`responsive-mobile.png`](./screenshots/responsive-mobile.png)
  - [`responsive-tablet.png`](./screenshots/responsive-tablet.png)
  - [`responsive-desktop.png`](./screenshots/responsive-desktop.png)
- **Kết quả:** Ảnh rõ nội dung, không còn hiện tượng lặp viewport; mỗi ảnh thể hiện đầy đủ các khu vực chính từ header đến phần liên hệ theo breakpoint tương ứng.

### 05/11/2026 — Tạo hồ sơ phát hành ban đầu

- **Phạm vi:** Tạo release note, báo cáo kiểm thử và ảnh responsive cho bản portfolio tĩnh ban đầu.
- **Kết quả:** Đã được thay thế và đồng bộ lại theo bản cập nhật ngày 08/11/2026.
