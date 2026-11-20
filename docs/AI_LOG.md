# Nhật ký làm việc cùng AI

## Mục đích và nguyên tắc ghi nhận

Tài liệu tóm lược các giai đoạn AI hỗ trợ dự án My-CV, phục vụ đối chiếu báo cáo `BAOCAO-A2.1.docx`. Các mục **Prompt/Chỉ thị** bên dưới là diễn giải ngắn gọn theo phạm vi công việc, không phải bản chép nguyên văn hội thoại. Phần lịch sử trước đợt tài liệu hóa được tổng hợp từ cấu trúc và mã nguồn hiện tại; không gán ngày, kết quả kiểm thử hoặc prompt cụ thể khi không có bản ghi đối chứng.

AI hỗ trợ phân tích, đề xuất và biên soạn; tác giả chịu trách nhiệm đối chiếu nội dung, kiểm tra mã và xác nhận hành vi trên trình duyệt. Các ghi nhận kiểm thử nêu rõ môi trường đã chạy, không suy diễn thành xác nhận tương thích trên trình duyệt chưa thử.

## Giai đoạn 1 — Khởi tạo portfolio Mobile-First và Design Tokens

**Mục tiêu**

Thiết lập nền tảng portfolio cá nhân dễ đọc trên màn hình nhỏ, có cấu trúc rõ ràng và hệ biến thiết kế dùng lại.

**Prompt/Chỉ thị đã dùng (tóm lược)**

“Xây dựng cấu trúc portfolio cá nhân bằng HTML/CSS, tổ chức phần giới thiệu, kỹ năng, dự án và liên hệ; bắt đầu từ bố cục mobile-first và gom màu sắc/khoảng cách thành design tokens.”

**Kết quả AI hỗ trợ**

Hỗ trợ phác thảo cấu trúc nội dung, đề xuất tổ chức section và quy tắc responsive; đưa ra hướng dùng CSS custom properties để quản lý màu sắc, khoảng cách và giới hạn chiều rộng.

**Kiểm duyệt và tinh chỉnh của tác giả**

Đối chiếu các phần với nội dung cá nhân, liên kết và ảnh thực tế; kiểm tra việc giữ nguyên khả năng đọc ở viewport nhỏ trước khi mở rộng breakpoint. Đây là mô tả quy trình theo hiện trạng dự án, không khẳng định một bộ kiểm thử lịch sử nếu không có log chạy kèm.

## Giai đoạn 2 — Chuyển tương tác sang Pure CSS

**Mục tiêu**

Loại bỏ nhu cầu JavaScript runtime khỏi tương tác của website portfolio nhưng vẫn giữ các thao tác xem nội dung cần thiết.

**Prompt/Chỉ thị đã dùng (tóm lược)**

“Đề xuất cách triển khai theme, lọc dự án, điều hướng hộp thoại, so sánh và trạng thái biểu mẫu bằng HTML/CSS; tận dụng `:has()`, `:target`, `@property`, radio/checkbox và validation native.”

**Kết quả AI hỗ trợ**

Hỗ trợ phân rã trạng thái tương tác thành checkbox/radio và fragment URL; gợi ý dùng `@property` cho chuyển màu, `:has()` cho lựa chọn tổ tiên, `:target` cho hộp thoại/trạng thái và `:valid` cho tiến độ biểu mẫu.

**Kiểm duyệt và tinh chỉnh của tác giả**

Đối chiếu selector với ID/class trong HTML và giới hạn hỗ trợ trình duyệt; giữ nội dung form thông báo rõ tính năng chưa gửi dữ liệu tới backend. Khi kiểm tra phiên bản hiện tại trên Chromium, tiến độ form đạt 20% theo từng trường và 100% khi đủ năm trường hợp lệ. Các trình duyệt khác chưa được xác nhận trong đợt kiểm tra này.

## Giai đoạn 3 — Tái cấu trúc và làm sạch mã nguồn

**Mục tiêu**

Làm rõ trách nhiệm từng khu vực CSS, giữ cấu trúc semantic và loại bỏ phần tương tác JavaScript/DOM cũ không còn phù hợp.

**Prompt/Chỉ thị đã dùng (tóm lược)**

“Rà soát HTML/CSS hiện có, tổ chức stylesheet theo nhóm chức năng, kiểm tra responsive và loại bỏ mã/class/nút điều khiển cũ không còn dùng.”

**Kết quả AI hỗ trợ**

Hỗ trợ rà soát bố cục CSS Mobile-First, phân nhóm stylesheet thành 12 phần và lập danh sách những trạng thái cần kiểm tra: theme, kỹ năng, modal, compare tray, form, focus và giảm chuyển động.

**Kiểm duyệt và tinh chỉnh của tác giả**

Tác giả cần đối chiếu từng thay đổi với giao diện thật, kiểm tra các ID neo và các nhãn điều khiển tương ứng. Trong bản nguồn được đối chiếu cho phiên bản tài liệu này, không có thẻ `<script>`, class/nút `mode-pro` cũ hay điều khiển legacy trong DOM. “Pure CSS” mô tả runtime của portfolio; một số thẻ dự án vẫn ghi JavaScript như công nghệ của sản phẩm được giới thiệu.

## Giai đoạn 4 — Chuẩn hóa tài liệu dự án

**Mục tiêu**

Đồng bộ README, báo cáo QA/QC, release note và nhật ký AI với mã nguồn hiện tại và lịch sử phát hành 2.0.0.

**Prompt/Chỉ thị đã dùng (tóm lược)**

“Đọc trực tiếp `index.html` và `assets/css/styles.css`, chỉ cập nhật bốn tài liệu, ghi rõ tính năng, breakpoint, test case, lịch sử nâng cấp và phạm vi kiểm thử có minh chứng.”

**Kết quả AI hỗ trợ**

Biên soạn README tiếng Việt với badge, cây thư mục và đường dẫn screenshot; tổng hợp release note theo Keep a Changelog; lập test report theo nhóm và ghi chú điều kiện triển khai; cấu trúc nhật ký AI theo bốn giai đoạn.

**Kiểm duyệt và tinh chỉnh của tác giả**

Đối chiếu tên dự án, ID, selector và breakpoint trực tiếp với HTML/CSS; giữ nguyên hai tệp nguồn giao diện. Kiểm tra trình duyệt tích hợp Chromium tại viewport 375, 768 và 1440 px, bao gồm theme, bộ lọc, bốn modal, compare tray, form, giảm chuyển động, focus bàn phím và hiệu ứng hover. Báo cáo chỉ tính 16 ca đã thực thi; không ghi nhận Edge/Firefox/Safari hoặc validator HTML/CSS độc lập là đã chạy. Tác giả cần chụp lại ba ảnh trong `docs/screenshots/` và hoàn thành kiểm thử các trình duyệt còn lại trước khi xác nhận phát hành rộng.

## Tệp được đồng bộ

- [`README.md`](../README.md) — hướng dẫn sử dụng và giới thiệu sản phẩm.
- [`test_report.md`](./test_report.md) — kết quả và giới hạn kiểm thử.
- [`RELEASENOTE.md`](./RELEASENOTE.md) — lịch sử phát hành.
