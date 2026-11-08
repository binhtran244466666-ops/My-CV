# Release Note

## Phiên bản v1.1.0

- **Ngày phát hành:** 08/11/2026
- **Phạm vi:** Cập nhật giao diện, tương tác và tài liệu bàn giao theo mã nguồn mới nhất.

### Điểm mới

- Thêm công tắc chuyển giao diện ngày/đêm bằng HTML/CSS thuần.
- Thêm hiệu ứng gợn sáng, avatar nổi, đèn LED và các animation có kiểm soát.
- Cho phép chọn kỹ năng để làm nổi bật các dự án liên quan; có nút “Hiện tất cả”.
- Thêm 4 hộp chi tiết dự án mở/đóng bằng liên kết `:target`.
- Thêm chọn nhiều dự án vào khay so sánh bằng checkbox.
- Thêm form liên hệ nhanh gồm họ tên, email, chủ đề, nội dung và xác nhận đồng ý.
- Hiển thị tiến độ điền form và dùng validation bắt buộc native của trình duyệt.
- Bổ sung hỗ trợ `prefers-reduced-motion` để giảm chuyển động khi người dùng yêu cầu.
- Làm mới ảnh minh chứng ở ba viewport: mobile 390×844, tablet 768×1024 và desktop 1440×900.

### Thay đổi kỹ thuật

- Không bổ sung dependency, backend hoặc tệp JavaScript runtime.
- Tương tác được triển khai bằng checkbox/radio, pseudo-class `:has()`, `:target` và validation HTML.
- Giữ ảnh đại diện cục bộ tại `assets/img/AVATAR.png`; ảnh minh họa dự án vẫn tải từ Unsplash.

### Đã xác nhận

- Máy chủ tĩnh cục bộ phục vụ `index.html` thành công với HTTP 200.
- Trang có 4 section chính: Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Có 4 hộp chi tiết tương ứng với 4 dự án.
- Theme, lọc kỹ năng, mở chi tiết dự án và form liên hệ hoạt động trong trình duyệt.
- Ảnh responsive được chụp lại từ bản mã nguồn hiện tại.

### Hạn chế còn tồn tại

- Form liên hệ hiện chỉ hiển thị thông báo “Tính năng đang phát triển”, chưa gửi dữ liệu tới backend.
- Ảnh minh họa dự án và font/icon được tải từ domain bên ngoài, nên phụ thuộc kết nối Internet.
- Chưa có pipeline lint/CI hoặc báo cáo Lighthouse tự động trong repository.
- Hỗ trợ `:has()`, `dialog` và một số animation phụ thuộc trình duyệt hiện đại.
