# My CV - Portfolio cá nhân

Website CV/portfolio cá nhân của **Trần Đăng Bình**, giới thiệu thông tin cá nhân, kỹ năng, các dự án tiêu biểu và thông tin liên hệ. Dự án được xây dựng theo hướng tối giản, responsive và có thể triển khai như một website tĩnh.

## Chức năng

- Hiển thị phần giới thiệu và vai trò Frontend Developer.
- Điều hướng nhanh tới các phần: Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Trình bày kỹ năng với HTML5, CSS3, JavaScript, responsive design, Git/GitHub và Figma.
- Hiển thị danh sách các dự án tiêu biểu:
  - Landing Page Sản Phẩm
  - Ứng dụng Todo List
  - Weather Dashboard
  - Blog Cá Nhân
- Giao diện responsive cho điện thoại, máy tính bảng và máy tính để bàn.
- Hỗ trợ cuộn mượt, bố cục Flexbox/Grid và ảnh đại diện cục bộ.

## Công nghệ sử dụng

- **HTML5**: cấu trúc nội dung và semantic markup.
- **CSS3**: giao diện, biến CSS, Flexbox, CSS Grid, media queries và responsive design.
- **JavaScript**: hiện được giới thiệu trong phần kỹ năng; phiên bản hiện tại chưa có tệp JavaScript riêng.
- **Docker/Nginx**: tùy chọn để phục vụ website tĩnh trong môi trường container.

## Cấu trúc dự án

```text
My-CV/
├── index.html
├── README.md
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── img/
│       └── AVATAR.png
└── BAOCAO-A2.1.docx
```

## Yêu cầu môi trường

Website không yêu cầu cài Node.js, npm, cơ sở dữ liệu hoặc backend.

- Trình duyệt hiện đại: Chrome, Edge, Firefox hoặc Safari.
- Tùy chọn:
  - **Python 3** để chạy máy chủ tĩnh cục bộ.
  - **Docker Desktop** hoặc Docker Engine để chạy bằng container.
- Kết nối Internet là cần thiết để tải một số ảnh minh họa dự án đang dùng URL bên ngoài.

## Cài đặt

### Windows

Mở PowerShell và chạy:

```powershell
git clone <URL_REPOSITORY>
cd My-CV
```

Nếu không dùng Git, có thể tải mã nguồn dưới dạng ZIP, giải nén và mở thư mục `My-CV`.

### macOS

Mở Terminal và chạy:

```bash
git clone <URL_REPOSITORY>
cd My-CV
```

### Linux

Mở Terminal và chạy:

```bash
git clone <URL_REPOSITORY>
cd My-CV
```

> Thay `<URL_REPOSITORY>` bằng URL repository thực tế. Vì đây là website tĩnh, bước cài đặt phụ thuộc chỉ là tải mã nguồn về máy.

## Cấu hình

Không có tệp `.env` hoặc cấu hình backend. Có thể tùy chỉnh trực tiếp:

- Nội dung, tiêu đề trang, mô tả SEO và thông tin tác giả trong `index.html`.
- Màu sắc, font chữ, khoảng cách và breakpoint trong `assets/css/styles.css`.
- Ảnh đại diện tại `assets/img/AVATAR.png`.
- Liên kết dự án, email, GitHub và Facebook trong phần tương ứng của `index.html`.

Khi thay ảnh đại diện, nên giữ đường dẫn tương đối:

```html
<img src="./assets/img/AVATAR.png" alt="Ảnh đại diện của Trần Đăng Bình">
```

## Chạy thử

### Cách nhanh: mở trực tiếp trong trình duyệt

Nhấp đúp vào `index.html`, hoặc dùng lệnh tương ứng:

**Windows PowerShell**

```powershell
Start-Process .\index.html
```

**macOS**

```bash
open index.html
```

**Linux**

```bash
xdg-open index.html
```

Một số tính năng trình duyệt có thể hạn chế khi mở bằng giao thức `file://`. Nên dùng máy chủ cục bộ cho quá trình phát triển.

### Chạy bằng Python trên Windows, macOS hoặc Linux

Từ thư mục gốc của dự án, chạy:

```bash
python -m http.server 8000
```

Nếu máy dùng lệnh `python3`, chạy:

```bash
python3 -m http.server 8000
```

Mở trình duyệt tại [http://localhost:8000](http://localhost:8000). Nhấn `Ctrl+C` trong cửa sổ terminal để dừng máy chủ.

## Chạy bằng Docker

### Chạy nhanh bằng Nginx

Từ thư mục gốc `My-CV`, chạy lệnh sau.

**Windows PowerShell, macOS hoặc Linux**

```bash
docker run --rm --name my-cv -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

Sau đó mở [http://localhost:8080](http://localhost:8080). Nhấn `Ctrl+C` để dừng container.

Nếu dùng Windows PowerShell và `${PWD}` không được Docker nhận đúng, dùng đường dẫn tuyệt đối:

```powershell
docker run --rm --name my-cv -p 8080:80 -v "D:\duong-dan\My-CV:/usr/share/nginx/html:ro" nginx:alpine
```

Trên macOS/Linux, có thể dùng đường dẫn hiện tại dạng tuyệt đối:

```bash
docker run --rm --name my-cv -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Lệnh trên dùng image `nginx:alpine`, ánh xạ cổng `8080` của máy vào cổng HTTP `80` trong container và mount mã nguồn ở chế độ chỉ đọc.

## Triển khai

Vì là website tĩnh, có thể triển khai thư mục dự án lên GitHub Pages, Netlify, Vercel, Nginx hoặc bất kỳ máy chủ web tĩnh nào. Đảm bảo giữ nguyên cấu trúc thư mục tương đối của `index.html` và `assets/`.

## Thông tin liên hệ

- **Họ tên:** Trần Đăng Bình
- **Email:** [binhdangtran2202@gmail.com](mailto:binhdangtran2202@gmail.com)
- **GitHub:** [binhtran244466666-ops](https://github.com/binhtran244466666-ops)
- **Facebook:** [tran.binh.29554](https://www.facebook.com/tran.binh.29554)

## Bản quyền

© 2026 Trần Đăng Bình. Thiết kế và xây dựng bằng HTML5 và CSS3.