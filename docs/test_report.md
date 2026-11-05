# Báo cáo kiểm thử phần mềm — My CV

## 1. Tiêu đề báo cáo & Thông tin chung

| Thông tin | Chi tiết |
|---|---|
| Tên dự án | My CV — Portfolio cá nhân |
| Phiên bản đánh giá | v1.0.0 |
| Ngày kiểm thử | 05/11/2026 |
| Người thực hiện | QA/QC Engineer |
| Người đánh giá | Chưa chỉ định |
| Phạm vi | Kiểm tra mã nguồn, tài liệu, cấu trúc website tĩnh và mức độ sẵn sàng bàn giao |
| Môi trường dự kiến | Trình duyệt hiện đại trên desktop/tablet/mobile; máy chủ tĩnh Python hoặc Nginx |
| Phương pháp | Review tĩnh kết hợp checklist đối chiếu yêu cầu và kiểm tra minh chứng trong repository |

### Quy ước trạng thái

- **Đạt:** Đã đáp ứng yêu cầu hoặc có minh chứng phù hợp.
- **Chưa đạt:** Chưa đáp ứng yêu cầu hoặc phát hiện lỗi cần xử lý trước khi bàn giao.
- **Cần cải thiện:** Có triển khai nhưng còn thiếu, chưa đủ minh chứng hoặc còn rủi ro cần theo dõi.

## 2. Bảng tổng quan trạng thái

| # | Nhóm tiêu chí | Trạng thái | Tóm tắt |
|---:|---|---|---|
| 1 | Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng | Đạt | Các khu vực CV, điều hướng nội bộ và nội dung chính đã được triển khai. |
| 2 | Giao diện, trải nghiệm người dùng và khả năng tương thích | Cần cải thiện | Có responsive bằng CSS, nhưng cần kiểm thử trực tiếp trên nhiều trình duyệt/kích thước màn hình. |
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | Cần cải thiện | Website tĩnh, ít điểm lỗi; chưa có kết quả đo hiệu năng hoặc kiểm thử lỗi đầy đủ. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | Đạt | Không có backend, cơ sở dữ liệu hoặc thông tin bí mật trong cấu hình; vẫn cần rà soát liên kết bên ngoài. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | Cần cải thiện | Cấu trúc đơn giản, có README và release note; cần bổ sung kiểm tra tự động và chuẩn hóa tên file báo cáo. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | Cần cải thiện | Có hướng dẫn Python/Docker/Nginx nhưng chưa có biên bản chạy thử, ảnh chụp hoặc kết quả test tự động. |

**Kết luận sơ bộ:** Có thể bàn giao ở mức bản demo/website tĩnh sau khi xác nhận thủ công các liên kết, hình ảnh và hiển thị trên môi trường mục tiêu. Chưa nên xem là bản nghiệm thu hoàn toàn nếu chưa bổ sung minh chứng kiểm thử trình duyệt và hiệu năng.

## 3. Nội dung kiểm tra chi tiết

### 3.1. Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng cụ thể |
|---|---|---|
| Hiển thị thông tin giới thiệu cá nhân và vai trò nghề nghiệp | Đạt | Có phần Hero với tên, vai trò Frontend Developer và mô tả trong `index.html`. |
| Điều hướng tới các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ | Đạt | Thanh điều hướng sử dụng liên kết nội bộ `#about`, `#skills`, `#projects`, `#contact`. |
| Hiển thị danh sách kỹ năng | Đạt | Có HTML5, CSS3/Flexbox/Grid, JavaScript, Responsive Design, Git/GitHub và Figma. |
| Hiển thị bốn dự án tiêu biểu | Đạt | Có Landing Page Sản Phẩm, Todo List, Weather Dashboard và Blog Cá Nhân. |
| Nút “Xem dự án” và “Liên hệ tôi” hoạt động theo đúng mục tiêu | Đạt | Liên kết tới khu vực `#projects` và `#contact`. |
| Hiển thị thông tin liên hệ | Đạt | Có email, GitHub và Facebook ở phần Liên hệ. |
| Chức năng tương tác nâng cao bằng JavaScript | Cần cải thiện | README xác nhận chưa có tệp JavaScript riêng; không có form gửi dữ liệu hoặc xử lý động. |
| Liên kết “Xem chi tiết” dẫn tới trang dự án tương ứng | Cần cải thiện | Các liên kết hiện trỏ tới trang bên ngoài, chưa có trang chi tiết riêng cho từng dự án. |

### 3.2. Giao diện, trải nghiệm người dùng và khả năng tương thích

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng cụ thể |
|---|---|---|
| Bố cục responsive trên mobile, tablet và desktop | Đạt | `styles.css` áp dụng mobile-first, Flexbox/Grid và media query theo breakpoint. Đã chụp từ website chạy cục bộ: [mobile 390×844](./screenshots/responsive-mobile.png), [tablet 768×1024](./screenshots/responsive-tablet.png), [desktop 1440×900](./screenshots/responsive-desktop.png). |
| Thanh điều hướng có thể xuống dòng trên màn hình hẹp | Đạt | `.header-inner` và `.nav-list` sử dụng `flex-wrap: wrap`. |
| Hình ảnh không gây tràn khung | Đạt | Quy tắc `img { max-width: 100%; height: auto; }` và `body { overflow-x: hidden; }`. |
| Điều hướng cuộn mượt | Đạt | `html { scroll-behavior: smooth; }`. |
| Khả năng đọc và tương phản màu | Cần cải thiện | Bảng màu hiện tại có nhiều màu tương phản mạnh; cần xác nhận bằng công cụ WCAG/kiểm tra trực quan trên thiết bị thực. |
| Khả năng truy cập cơ bản | Cần cải thiện | Có `lang="vi"`, nhãn điều hướng và `alt` cho ảnh; cần kiểm tra focus keyboard, thứ tự heading và độ tương phản đầy đủ. |
| Tương thích Chrome, Edge, Firefox và Safari | Cần cải thiện | README nêu trình duyệt mục tiêu nhưng chưa có biên bản kiểm thử trên từng trình duyệt. |
| Hiển thị khi mất Internet | Cần cải thiện | Ảnh dự án dùng URL bên ngoài nên có thể không hiển thị khi không có mạng hoặc nguồn ảnh thay đổi. |

### 3.3. Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng cụ thể |
|---|---|---|
| Mở trang trực tiếp bằng `index.html` | Đạt | README có hướng dẫn mở file trực tiếp trên Windows, macOS và Linux. |
| Chạy bằng máy chủ tĩnh Python | Đạt | Có hướng dẫn `python -m http.server 8000`. |
| Chạy bằng Nginx/Docker | Đạt | README có lệnh chạy image `nginx:alpine` và ánh xạ cổng. |
| Hiển thị khi thiếu tài nguyên cục bộ | Cần cải thiện | Chưa có kiểm thử lỗi khi `styles.css` hoặc `avatar.jpg` bị thiếu/đổi đường dẫn. |
| Xử lý lỗi runtime | Đạt | Không có JavaScript hoặc backend nên không phát sinh luồng lỗi runtime phức tạp trong phạm vi hiện tại. |
| Thời gian tải và kích thước tài nguyên | Cần cải thiện | Chưa có số liệu Lighthouse, WebPageTest hoặc đo tải trên mạng chậm. |
| Tối ưu ảnh và tài nguyên bên ngoài | Cần cải thiện | Một số ảnh lấy từ URL bên ngoài; cần cân nhắc nén ảnh, lazy loading hoặc lưu bản sao cục bộ. |

### 3.4. Bảo mật, quản lý cấu hình và dữ liệu

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng cụ thể |
|---|---|---|
| Không chứa thông tin xác thực hoặc khóa bí mật | Đạt | Website không có `.env`, backend, cơ sở dữ liệu hoặc thông tin đăng nhập. |
| Dữ liệu người dùng và dữ liệu nhạy cảm | Đạt | Không thu thập hoặc lưu trữ dữ liệu người dùng trong phiên bản hiện tại. |
| Quản lý cấu hình | Đạt | Nội dung và giao diện được cấu hình trực tiếp trong `index.html` và `assets/css/styles.css`; phù hợp với website tĩnh. |
| Liên kết tới tài nguyên bên ngoài | Cần cải thiện | Cần rà soát tính tin cậy, tính ổn định và chính sách của các domain ảnh/liên kết dự án bên ngoài. |
| Bảo vệ khi triển khai HTTPS | Cần cải thiện | HTTPS phụ thuộc nền tảng triển khai; repository chưa cung cấp cấu hình bắt buộc HTTPS hoặc security headers. |
| Kiểm tra lỗ hổng phụ thuộc | Đạt | Không có `package.json` hoặc thư viện runtime cần cài đặt; vẫn cần rà soát image Nginx khi triển khai Docker. |

### 3.5. Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng cụ thể |
|---|---|---|
| Cấu trúc repository rõ ràng | Đạt | Có `index.html`, `assets/css/styles.css`, `assets/img/avatar.jpg` và thư mục `docs`. |
| HTML semantic và metadata cơ bản | Đạt | Có `header`, `nav`, `main`, `section`, `article`, `footer`, `lang`, `description` và `author`. |
| CSS có tổ chức và tái sử dụng | Đạt | Có custom properties, quy ước spacing, container, layout Flexbox/Grid và breakpoint. |
| Tính nhất quán nội dung thương hiệu | Cần cải thiện | Cần rà soát lại nội dung hiển thị trong header và thông tin cá nhân trước khi bàn giao chính thức. |
| Tài liệu cài đặt/chạy/triển khai | Đạt | `README.md` có hướng dẫn cho Windows, macOS, Linux, Python và Docker/Nginx. |
| Tài liệu phát hành | Đạt | `docs/RELEASENOTE.md` ghi nhận phiên bản v1.0.0, chức năng, lỗi đã sửa và hạn chế. |
| Nhật ký thay đổi do AI | Đạt | `docs/AI_LOG.md` ghi lại thay đổi tài liệu phát hành. |
| Kiểm tra lint/format tự động | Cần cải thiện | Chưa có cấu hình hoặc kết quả chạy HTML/CSS validator, formatter hay CI trong repository. |

### 3.6. Khả năng triển khai, kiểm thử và cung cấp minh chứng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng cụ thể |
|---|---|---|
| Triển khai dạng website tĩnh | Đạt | Có thể triển khai lên GitHub Pages, Netlify, Vercel, Nginx hoặc máy chủ tĩnh khác. |
| Tài liệu triển khai có thể thực hiện được | Đạt | README cung cấp lệnh chạy Python và Docker/Nginx, bao gồm ví dụ cho Windows. |
| Kiểm thử trên môi trường sạch | Cần cải thiện | Chưa có log hoặc biên bản xác nhận clone repository và chạy từ đầu trên máy sạch. |
| Bộ test hồi quy | Cần cải thiện | Chưa có test case tự động; cần kiểm tra lại navigation, ảnh, liên kết và responsive sau mỗi thay đổi. |
| Minh chứng ảnh chụp/video kết quả | Đạt | Đã lưu ảnh chụp thực tế tại `docs/screenshots/`: [responsive-mobile.png](./screenshots/responsive-mobile.png), [responsive-tablet.png](./screenshots/responsive-tablet.png) và [responsive-desktop.png](./screenshots/responsive-desktop.png). |
| Minh chứng hiệu năng và accessibility | Cần cải thiện | Chưa có báo cáo Lighthouse, điểm Core Web Vitals hoặc kết quả kiểm tra WCAG. |
| Quy trình xử lý lỗi sau bàn giao | Cần cải thiện | Cần thống nhất nơi ghi nhận issue, mức độ ưu tiên và tiêu chí đóng lỗi. |

## 4. Đánh giá tổng kết & Đề xuất

### 4.1. Nhận định chung

Website đã đáp ứng tốt phạm vi cốt lõi của một portfolio CV tĩnh: nội dung chính đầy đủ, điều hướng nội bộ hoạt động, cấu trúc HTML/CSS rõ ràng và có hướng dẫn triển khai. Sản phẩm phù hợp để bàn giao bản demo hoặc bản phát hành nội bộ.

Mức độ sẵn sàng bàn giao hiện tại: **Có điều kiện — cần xác nhận bổ sung trước nghiệm thu chính thức**.

### 4.2. Vấn đề cần khắc phục trước khi bàn giao chính thức

1. Kiểm tra và xác nhận lại toàn bộ nội dung cá nhân, tiêu đề thương hiệu và thông tin liên hệ.
2. Kiểm tra tất cả liên kết “Xem chi tiết”, email, GitHub và Facebook; thay các liên kết mẫu bằng URL chính thức nếu cần.
3. Kiểm thử thủ công trên Chrome, Edge, Firefox và Safari ở các kích thước mobile, tablet và desktop.
4. Chạy Lighthouse hoặc công cụ tương đương để đo Performance, Accessibility, Best Practices và SEO.
5. Cân nhắc lưu ảnh dự án cục bộ hoặc bổ sung phương án dự phòng khi tài nguyên bên ngoài không khả dụng.
6. Bổ sung checklist hồi quy, ảnh chụp minh chứng và kết quả kiểm thử vào hồ sơ bàn giao.

### 4.3. Tiêu chí chấp nhận đề xuất

- Không còn lỗi chức năng mức nghiêm trọng đối với điều hướng, hiển thị nội dung và liên kết liên hệ.
- Không xuất hiện cuộn ngang hoặc vỡ bố cục ở các viewport mục tiêu.
- Tất cả tài nguyên bắt buộc tải thành công trên môi trường triển khai thực tế.
- Nội dung cá nhân và URL bên ngoài được chủ sở hữu xác nhận.
- Có minh chứng kiểm thử trình duyệt, responsive, accessibility và hiệu năng cơ bản.
