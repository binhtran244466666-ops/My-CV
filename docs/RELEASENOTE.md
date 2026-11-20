# Nhật ký phát hành

Nhật ký này tuân theo cách tổ chức **Keep a Changelog**; phiên bản phát hành tuân thủ **Semantic Versioning**.

## [2.0.0] - 2026-11-20

### Tổng quan

Chuyển kiến trúc portfolio sang HTML5 và CSS3 thuần, loại bỏ JavaScript runtime khỏi website và chuẩn hóa CSS theo hướng Mobile-First. Bản phát hành tập trung vào tương tác CSS, responsive và khả năng vận hành như một website tĩnh không cần bước build.

### Added

- Chuyển màu theme sáng/tối mượt bằng các custom property đăng ký với `@property` và trạng thái checkbox được chọn qua `:has()`.
- Điều hướng nhận biết section theo `:target`, hiệu ứng viền khi đến đích và header sticky có `backdrop-filter`.
- Bộ chọn kỹ năng bằng radio kết hợp `:has()` để làm nổi bật các thẻ dự án khớp nhãn; thêm tùy chọn “Hiện tất cả”.
- Bốn hộp thoại chi tiết dự án mở theo fragment `#project-1` đến `#project-4`, có backdrop và liên kết đóng.
- Khay so sánh trượt từ đáy, hiển thị các dự án được đánh dấu bằng checkbox.
- Form liên hệ nhanh dùng HTML validation; thanh tiến độ CSS cộng dồn 20% cho mỗi trường hợp hợp lệ; fragment `:target` hiển thị thông báo trạng thái.
- Thanh tiến độ cuộn trang dùng `animation-timeline: scroll()` khi trình duyệt hỗ trợ.
- Hỗ trợ `:focus-visible` và `prefers-reduced-motion`; hiệu ứng xòe quạt chỉ áp dụng cho thiết bị có hover và pointer chính xác.

### Changed

- Tái cấu trúc `assets/css/styles.css` thành 12 phân mục, làm rõ design tokens, layout, tương tác và breakpoint.
- Chuẩn hóa cấu trúc nội dung HTML5 ngữ nghĩa, các khu vực điều hướng, nội dung chính, dự án và liên hệ.
- Chuẩn hóa Mobile-First: dưới 768 px dùng danh sách dự án cuộn ngang có scroll snap; từ 768 px dùng hero/lưới dự án/form hai cột; từ 1100 px dùng lưới dự án bốn cột và danh sách liên hệ ba cột.
- Cập nhật tài liệu dự án và kế hoạch làm mới ảnh responsive để phù hợp giao diện 2.0.0.

### Removed

- Gỡ bỏ các tệp/đoạn mã và thẻ `<script>` JavaScript khỏi website; các tương tác giao diện được chuyển sang HTML/CSS.
- Loại bỏ hoàn toàn chế độ/nút gạt `mode-pro` cũ.
- Loại bỏ các phần tử DOM rỗng và class cũ chỉ tồn tại để phục vụ JavaScript.

### Lưu ý triển khai

- Ghi đè bộ ảnh cũ trong `docs/screenshots/` bằng ảnh chụp đúng phiên bản 2.0.0 tại ba viewport: desktop từ 1100 px, tablet 768 px và mobile dưới 768 px.
- Form hiện chỉ kiểm tra dữ liệu bằng trình duyệt và hiển thị thông báo; muốn nhận tin nhắn cần cấu hình backend hoặc dịch vụ biểu mẫu.
- Font, icon và ảnh minh họa dự án có tài nguyên tải từ bên ngoài.
- Cần xác nhận tương thích trên các trình duyệt mục tiêu trước khi phát hành rộng.

## [1.1.0] - 2026-11-08

### Added

- Bổ sung các tương tác portfolio bằng HTML/CSS: theme, làm nổi dự án theo kỹ năng, chi tiết dự án, so sánh dự án và form liên hệ nhanh.
- Bổ sung validation native, trạng thái tiến độ biểu mẫu và quy tắc giảm chuyển động.
- Tạo bộ ảnh minh chứng responsive ở các viewport mobile, tablet và desktop.

### Changed

- Cập nhật nội dung, giao diện responsive và tài liệu bàn giao theo mã nguồn thời điểm phát hành.

## [1.0.0]

### Added

- Phát hành portfolio cá nhân dạng website tĩnh với phần giới thiệu, kỹ năng, dự án và liên hệ.
- Thiết lập nền tảng HTML/CSS responsive, ảnh đại diện cục bộ và điều hướng nội bộ.
