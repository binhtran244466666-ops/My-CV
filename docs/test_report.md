# Báo cáo kiểm thử QA/QC — My-CV v2.0.0

## 1. Thông tin chung

| Hạng mục | Chi tiết |
|---|---|
| Sản phẩm | Portfolio CV cá nhân — website tĩnh |
| Phiên bản | 2.0.0 — Pure HTML5 & CSS3 |
| Ngày thực hiện đợt kiểm tra này | 20/11/2026 |
| Mục tiêu | Xác minh các tương tác CSS, bố cục responsive, validation biểu mẫu và các điểm accessibility cơ bản trước khi bàn giao. |
| Phạm vi | `index.html` và `assets/css/styles.css`; chỉ kiểm tra hành vi trình duyệt, không sửa mã nguồn giao diện. |
| Trình duyệt đã chạy | Chromium tích hợp trong môi trường kiểm thử; phiên bản trình duyệt không được cung cấp. |
| Viewport đã chạy | 375 × 900, 768 × 900 và 1440 × 900 px; viewport được đặt bằng browser automation. |
| Cách chạy | Mở trực tiếp `index.html` bằng URL `file://`; tài nguyên từ CDN cần kết nối Internet. |
| Người thực hiện | Kiểm tra chức năng và responsive bằng trình duyệt tích hợp. |

### Ma trận tương thích

| Trình duyệt/công cụ | Mục tiêu | Trạng thái của đợt kiểm tra |
|---|---|---|
| Chromium/Chrome | Bản hiện hành có `:has()` và `@property` | Đã kiểm tra bằng Chromium tích hợp; không có thông tin phiên bản chính xác. |
| Microsoft Edge | Bản hiện hành có các tính năng CSS cần thiết | Chưa chạy riêng trên Edge. |
| Firefox | Bản hiện hành có các tính năng CSS cần thiết | Chưa chạy riêng trên Firefox. |
| Safari | Bản hiện hành có các tính năng CSS cần thiết | Chưa chạy riêng trên Safari. |
| DevTools Device Toolbar | Mô phỏng mobile/tablet/desktop | Chưa dùng trực tiếp Device Toolbar; các chiều rộng tương ứng được mô phỏng bằng browser automation. |

**Cách đọc trạng thái:** `PASS` chỉ áp dụng cho ca đã chạy trong Chromium. Những trình duyệt/công cụ chưa chạy không được tính là PASS. Do đó tỷ lệ bên dưới là tỷ lệ của các ca đã thực thi, không phải xác nhận bao phủ toàn bộ ma trận trình duyệt.

## 2. Kết quả tổng quan

| Nhóm | Số ca | PASS | Kết quả |
|---|---:|---:|---|
| Giao diện và responsive | 4 | 4 | PASS |
| Tương tác thuần CSS | 4 | 4 | PASS |
| Biểu mẫu liên hệ | 4 | 4 | PASS |
| Hiệu ứng và tiếp cận cơ bản | 4 | 4 | PASS |
| **Tổng các ca đã thực thi** | **16** | **16** | **100% PASS** |

Các ca trên đã chạy trên Chromium tích hợp. Tỷ lệ này không bao gồm kiểm thử Firefox, Safari, Edge riêng, audit accessibility toàn diện hoặc validator HTML/CSS độc lập.

## 3. Ca kiểm thử chi tiết

| ID | Hạng mục | Kịch bản thao tác | Kết quả mong đợi | Trạng thái |
|---|---|---|---|---|
| UI-01 | Mobile 375 px | Mở trang ở viewport rộng 375 px; cuộn ngang khu vực dự án. | Bố cục mobile một cột; lưới dự án có `scroll-snap-type: x mandatory` và cuộn trong vùng dự án. | **PASS** |
| UI-02 | Tablet 768 px | Đặt viewport rộng 768 px. | Hero, lưới dự án và biểu mẫu chuyển sang bố cục hai cột. | **PASS** |
| UI-03 | Desktop 1440 px | Đặt viewport rộng 1440 px. | Bốn thẻ dự án nằm trên một hàng; danh sách liên hệ ba cột. | **PASS** |
| UI-04 | Tràn ngang | So sánh độ rộng cuộn trang với viewport ở 375, 768 và 1440 px. | Không tràn ngang ở cấp trang; vùng dự án mobile vẫn cuộn ngang có chủ đích. | **PASS** |
| CSS-01 | Sáng/tối | Bật/tắt nhãn chuyển theme và chờ chuyển màu hoàn tất. | Bộ màu đổi từ theme tối sang sáng; thao tác không cần JavaScript. | **PASS** |
| CSS-02 | Lọc kỹ năng | Lần lượt chọn HTML5, CSS3, JavaScript, Responsive Design, Git & GitHub và Figma; chọn lại “Hiện tất cả”. | Dự án khớp nhãn được làm nổi; không khớp bị làm mờ; “Hiện tất cả” khôi phục độ hiển thị. Không có dự án gắn nhãn Git & GitHub nên lựa chọn này không làm nổi thẻ nào. | **PASS** |
| CSS-03 | Chi tiết dự án | Mở lần lượt `#project-1`, `#project-2`, `#project-3`, `#project-4`; đóng từng hộp thoại. | Mỗi fragment hiển thị đúng hộp thoại; liên kết đóng đưa về danh sách dự án. | **PASS** |
| CSS-04 | Khay so sánh | Chọn một dự án, sau đó bỏ chọn. | Khay trượt lên khi có lựa chọn; nội dung tương ứng xuất hiện; khay ẩn sau khi bỏ chọn cuối cùng. | **PASS** |
| FORM-01 | Panel tin nhắn nhanh | Bật rồi tắt công tắc mở form. | Panel mở/đóng theo trạng thái checkbox với chuyển đổi CSS Grid. | **PASS** |
| FORM-02 | Validation native | Kiểm tra form trống, nhập email sai định dạng, rồi điền đủ trường bằng dữ liệu hợp lệ. | Trường bắt buộc và email được kiểm tra bởi trình duyệt; form không hợp lệ khi thiếu dữ liệu/email sai và hợp lệ khi đủ dữ liệu, chọn đồng ý. | **PASS** |
| FORM-03 | Thanh tiến độ | Nhập hợp lệ từng trường: tên, email, chủ đề, nội dung, đồng ý. | Thanh tiến độ lần lượt đạt 20%, 40%, 60%, 80% và 100%. | **PASS** |
| FORM-04 | Trạng thái sau gửi | Gửi form hợp lệ bằng dữ liệu kiểm thử. | URL nhận fragment `#message-status`; thông báo trạng thái được hiển thị. | **PASS** |
| A11Y-01 | Thiết bị có chuột | Ở desktop, hover lên lưới dự án. | Bốn thẻ áp dụng hiệu ứng xòe quạt; thẻ được hover nổi bật hơn. | **PASS** |
| A11Y-02 | Giảm chuyển động | Bật giả lập `prefers-reduced-motion: reduce`. | Thời lượng animation/transition giảm về mức gần như tức thời. | **PASS** |
| A11Y-03 | Bàn phím | Dùng Tab để chuyển focus tới công tắc theme. | Phần tử nhận focus và nhãn điều khiển có viền `:focus-visible`. | **PASS** |
| A11Y-04 | Runtime và cấu trúc | Kiểm tra DOM sau khi tải; tìm script và selector giao diện cũ. | Không có thẻ `<script>` và không có class/nút gạt legacy; trang và stylesheet hiển thị trong Chromium. | **PASS** |

## 4. Phạm vi chưa được xác nhận

- Chưa có lượt chạy trực tiếp trên Edge, Firefox hoặc Safari; hỗ trợ thực tế cần được xác nhận theo phiên bản trình duyệt triển khai.
- Chưa dùng DevTools Device Toolbar trên thiết bị giả lập; kiểm tra responsive của báo cáo này sử dụng viewport automation.
- Chưa chạy validator HTML/CSS độc lập, kiểm thử WCAG đầy đủ, Lighthouse hoặc đo Core Web Vitals. Việc trang render trong Chromium không thay thế các kiểm tra này.
- Form hiện dùng validation native và điều hướng tới thông báo; không gửi dữ liệu tới máy chủ. Không xem trạng thái `#message-status` là xác nhận đã nhận tin nhắn.
- Bộ lọc Git & GitHub hiện chưa có thẻ dự án được gắn nhãn tương ứng; đây là giới hạn dữ liệu/tag của danh sách hiện tại.
- Font, icon và ảnh dự án phụ thuộc dịch vụ ngoài; cần xác nhận tải tài nguyên trong môi trường triển khai thực tế.

## 5. Kết luận chất lượng

**Kết quả: 16/16 ca đã thực thi PASS (100%) trên Chromium tích hợp.** Các hành vi cốt lõi, ba mốc responsive, validation và trạng thái CSS đã được kiểm tra tại phiên bản mã nguồn hiện tại.

Phiên bản có thể triển khai như **website tĩnh cho môi trường trình duyệt hiện đại đã hỗ trợ các tính năng CSS cần thiết**. Kết luận “Production Ready” ở phạm vi triển khai rộng chỉ nên chốt sau khi hoàn thành ma trận Edge/Firefox/Safari, kiểm tra tài nguyên mạng và xác nhận yêu cầu backend (nếu cần gửi form thật). Không có CI/linter hay báo cáo hiệu năng tự động trong repository hiện tại.
