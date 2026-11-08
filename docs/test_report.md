# Báo cáo kiểm thử phần mềm — My CV

## 1. Thông tin chung

| Thông tin | Chi tiết |
|---|---|
| Tên dự án | My CV — Portfolio cá nhân |
| Phiên bản đánh giá | v1.1.0 |
| Ngày kiểm thử | 08/11/2026 |
| Phạm vi | HTML, CSS, responsive, tương tác không JavaScript runtime và tài liệu bàn giao |
| Môi trường | Máy chủ Python cục bộ, trình duyệt Chromium, viewport 390×844, 768×1024 và 1440×900 |
| URL kiểm thử | `http://127.0.0.1:8000/index.html` |
| Người thực hiện | QA/QC Engineer |

### Quy ước

- **Đạt:** Đã kiểm tra và có kết quả phù hợp.
- **Cần cải thiện:** Có triển khai nhưng còn giới hạn hoặc chưa có kiểm thử tự động đầy đủ.

## 2. Tổng quan kết quả

| # | Nhóm tiêu chí | Trạng thái | Kết quả |
|---:|---|---|---|
| 1 | Cấu trúc và nội dung chính | Đạt | Trang có 4 section chính, header, footer, điều hướng nội bộ và metadata cơ bản. |
| 2 | Tương tác HTML/CSS | Đạt | Theme, lọc kỹ năng, chi tiết dự án, so sánh và form được triển khai không cần JavaScript runtime. |
| 3 | Responsive và hiển thị | Đạt | Đã chụp lại ảnh full-page ở 3 viewport mục tiêu từ bản mã nguồn hiện tại. |
| 4 | Liên hệ và validation | Đạt có điều kiện | Form có 5 trường bắt buộc và validation native; chưa có backend gửi dữ liệu. |
| 5 | Tài nguyên bên ngoài | Cần cải thiện | Ảnh dự án, Google Fonts và Font Awesome phụ thuộc Internet. |
| 6 | Tự động hóa chất lượng | Cần cải thiện | Chưa có lint, CI, Lighthouse hoặc bộ test hồi quy tự động trong repository. |

**Kết luận:** Bản v1.1.0 đạt yêu cầu cho demo/bàn giao website tĩnh. Cần xác nhận thêm trên các trình duyệt mục tiêu và bổ sung backend nếu form cần gửi dữ liệu thật.

## 3. Ca kiểm thử chức năng

| ID | Ca kiểm thử | Kết quả | Minh chứng |
|---|---|---|---|
| TC-01 | Mở trang qua máy chủ tĩnh | Đạt | HTTP status `200`; tiêu đề `Trần Đăng Bình · Frontend Developer`. |
| TC-02 | Điều hướng tới Giới thiệu, Kỹ năng, Dự án, Liên hệ | Đạt | Các liên kết `#about`, `#skills`, `#projects`, `#contact` có trong `index.html`. |
| TC-03 | Chuyển ngày/đêm | Đạt | Checkbox `#theme-switch` đổi trạng thái và bộ màu hiển thị bằng CSS. |
| TC-04 | Chọn kỹ năng JavaScript | Đạt | Label `sk-js` được chọn; các thẻ dự án JavaScript được làm nổi bật. |
| TC-05 | Khôi phục toàn bộ dự án | Đạt | Label `sk-none` đưa bộ lọc về trạng thái “Hiện tất cả”. |
| TC-06 | Mở chi tiết dự án | Đạt | Liên kết `#project-1` mở đúng hộp chi tiết; có liên kết đóng về `#projects`. |
| TC-07 | Mở form liên hệ nhanh | Đạt | Panel form hiển thị khi chọn `#quick-message-toggle`. |
| TC-08 | Validation form rỗng/không hợp lệ | Đạt | Trình duyệt chặn gửi khi thiếu trường bắt buộc hoặc email không hợp lệ. |
| TC-09 | Validation form hợp lệ | Đạt | Form hợp lệ sau khi điền tên, email, chủ đề, nội dung và checkbox đồng ý. |
| TC-10 | Hình ảnh và avatar | Đạt có điều kiện | Avatar cục bộ tải được; ảnh dự án cần Internet do dùng Unsplash. |

## 4. Kiểm thử responsive và minh chứng

| Viewport | Trạng thái | Ảnh minh chứng |
|---|---|---|
| Mobile 390×844 | Đạt | [responsive-mobile.png](./screenshots/responsive-mobile.png) |
| Tablet 768×1024 | Đạt | [responsive-tablet.png](./screenshots/responsive-tablet.png) |
| Desktop 1440×900 | Đạt | [responsive-desktop.png](./screenshots/responsive-desktop.png) |

Đã xác nhận các điểm chính: header và navigation hiển thị, hero có avatar, nút CTA không mất nội dung, các chip kỹ năng hiển thị, thẻ dự án có thể cuộn ngang trên mobile và bố cục chuyển sang nhiều cột ở viewport lớn. Ảnh được chụp full-page sau khi tắt animation/transition và ẩn scrollbar để minh chứng rõ ràng, ổn định.

## 5. Kiểm tra mã nguồn và khả năng triển khai

| Hạng mục | Trạng thái | Ghi chú |
|---|---|---|
| HTML semantic | Đạt | Có `header`, `nav`, `main`, `section`, `article`, `footer`, `dialog`. |
| Metadata và accessibility cơ bản | Đạt có điều kiện | Có `lang`, description, label, alt và focus style; cần audit WCAG đầy đủ. |
| CSS responsive | Đạt | Có custom properties, Flexbox, Grid, breakpoint và reduced-motion. |
| Dependency/runtime | Đạt | Không có `package.json`, backend hoặc JavaScript runtime. |
| Triển khai tĩnh | Đạt | Có thể dùng Python, Nginx/Docker, GitHub Pages, Netlify hoặc Vercel. |
| Hiệu năng | Cần cải thiện | Chưa có số đo Lighthouse/Core Web Vitals; ảnh ngoài có thể ảnh hưởng thời gian tải. |
| Bảo mật | Đạt có điều kiện | Không có dữ liệu nhạy cảm hoặc backend; cần cấu hình HTTPS/security headers ở môi trường triển khai. |

## 6. Vấn đề và đề xuất

1. Tích hợp endpoint/backend nếu form liên hệ cần gửi và lưu dữ liệu.
2. Lưu bản sao cục bộ hoặc thêm fallback cho ảnh dự án, font và icon bên ngoài.
3. Chạy kiểm tra WCAG, Lighthouse và thử nghiệm trên Chrome, Edge, Firefox, Safari.
4. Bổ sung lint/CI và checklist hồi quy cho các thay đổi HTML/CSS tiếp theo.

## 7. Tiêu chí nghiệm thu đề xuất

- Không có lỗi nghiêm trọng ở navigation, theme, lọc kỹ năng, chi tiết dự án và form validation.
- Không có vỡ bố cục hoặc cuộn ngang ngoài chủ đích của danh sách dự án trên mobile.
- Avatar, CSS và HTML tải thành công trên môi trường triển khai.
- Nội dung cá nhân, liên kết liên hệ và tài nguyên bên ngoài được chủ sở hữu xác nhận.
- Có kết quả kiểm thử trình duyệt, responsive, accessibility và hiệu năng trước khi phát hành chính thức.
