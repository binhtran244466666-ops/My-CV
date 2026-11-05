# AI Log

## Mục đích

File này ghi lại các thay đổi lớn do AI hỗ trợ thực hiện trong dự án. Mỗi mục log cần nêu ngày thực hiện, phạm vi thay đổi, các tệp liên quan và kết quả kiểm tra.

## Lịch sử thay đổi

### 05/11/2026 — Tạo release note phiên bản v1.0.0

- **Phạm vi:** Bổ sung tài liệu phát hành cho website CV/portfolio cá nhân.
- **Tệp liên quan:** [`docs/RELEASENOTE.md`](./RELEASENOTE.md)
- **Nội dung chính:**
  - Ghi nhận phiên bản v1.0.0 và ngày phát hành.
  - Mô tả các chức năng mới của website.
  - Ghi lại các lỗi đã sửa và cải thiện responsive.
  - Nêu các hạn chế còn tồn tại của website tĩnh.
- **Kết quả:** Đã hoàn thành và kiểm tra nội dung file release note.

### 05/11/2026 — Chụp minh chứng kiểm thử responsive

- **Phạm vi:** Chạy website cục bộ và kiểm tra hiển thị toàn trang trên ba kích thước viewport.
- **Môi trường:** Máy chủ Python tại `http://127.0.0.1:8000`.
- **Viewport:** Mobile 375px, tablet 768px và desktop 1440px.
- **Tệp minh chứng:**
  - [`docs/screenshots/responsive-mobile.png`](./screenshots/responsive-mobile.png)
  - [`docs/screenshots/responsive-tablet.png`](./screenshots/responsive-tablet.png)
  - [`docs/screenshots/responsive-desktop.png`](./screenshots/responsive-desktop.png)
- **Tệp cập nhật:** [`docs/tesst_report.md`](./tesst_report.md)
- **Kết quả:** Đã tạo và xác nhận ba ảnh screenshot; cập nhật trạng thái minh chứng responsive thành Đạt.