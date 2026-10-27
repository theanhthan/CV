# Portfolio CV - Thân Thế Anh

Trang portfolio/CV cá nhân giới thiệu Thân Thế Anh, định hướng Frontend Developer. Dự án được xây dựng dưới dạng website tĩnh bằng HTML và CSS, phù hợp để giới thiệu thông tin cá nhân, kỹ năng, dự án và cách liên hệ.

## Chức năng

- Hiển thị phần giới thiệu và ảnh đại diện.
- Trình bày danh sách kỹ năng và các dự án tiêu biểu.
- Điều hướng nhanh đến Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Cung cấp liên kết email, GitHub và LinkedIn.
- Bố cục responsive cho điện thoại, máy tính bảng và máy tính.
- Có thể mở trực tiếp trong trình duyệt hoặc chạy qua máy chủ web tĩnh.

## Công nghệ

- HTML5: cấu trúc nội dung và các vùng ngữ nghĩa.
- CSS3: giao diện, Flexbox, CSS Grid, biến CSS và responsive design.
- Nginx (tùy chọn): phục vụ website khi chạy bằng Docker.

Website không dùng framework, không có bước biên dịch và không cần cài thư viện npm. JavaScript được nhắc đến trong danh sách kỹ năng trên trang, nhưng hiện không có tệp JavaScript nào được dùng để vận hành website.

## Cấu trúc dự án

```text
CV-main/
├── index.html
├── README.md
└── assets/
	├── css/
	│   └── styles.css
	└── img/
		└── avatar.jpg
```

## Yêu cầu môi trường

Để xem trang, bạn chỉ cần một trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari.

Để chạy máy chủ cục bộ, cài Python 3 (không bắt buộc nếu bạn mở trực tiếp `index.html`). Để dùng phần Docker, cần cài Docker Desktop trên Windows/macOS hoặc Docker Engine trên Linux và đảm bảo Docker đang hoạt động.

## Cài đặt

Tải hoặc sao chép dự án về máy, sau đó mở thư mục `CV-main` trong VS Code hoặc terminal. Nếu lấy mã nguồn bằng Git:

```bash
git clone <URL_REPOSITORY>
cd CV-main
```

Thay `<URL_REPOSITORY>` bằng địa chỉ repository thực tế. Dự án hiện không cần cài thêm package.

## Cấu hình và cá nhân hóa

1. Mở `index.html` và cập nhật tên, chức danh, phần giới thiệu, kỹ năng, dự án và thông tin liên hệ.
2. Thay email mẫu `an.nguyen@example.com` cùng các liên kết GitHub/LinkedIn mẫu bằng thông tin thật. Các liên kết mạng xã hội hiện đang là `#` nên chưa dẫn đến trang cá nhân.
3. Thay `assets/img/avatar.jpg` bằng ảnh đại diện của bạn. Giữ nguyên tên và đường dẫn tệp, hoặc cập nhật thuộc tính `src` trong `index.html` cho khớp.
4. Chỉnh màu sắc, kích thước và bố cục trong `assets/css/styles.css`. Các màu và thông số giao diện được khai báo tập trung trong khối `:root` ở đầu tệp.

Không cần tệp `.env` hay cấu hình riêng để chạy website.

## Chạy thử

### Mở trực tiếp

Mở `index.html` bằng trình duyệt. Cách này phù hợp để xem nhanh giao diện; máy chủ cục bộ được khuyến nghị khi chỉnh sửa và kiểm tra dự án.

### Windows

Mở PowerShell tại thư mục dự án rồi chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, dùng:

```powershell
python -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000) trong trình duyệt. Nhấn `Ctrl+C` trong PowerShell để dừng máy chủ.

### macOS

Mở Terminal, chuyển đến thư mục dự án và khởi động máy chủ:

```bash
cd /duong-dan/toi/CV-main
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Nhấn `Ctrl+C` để dừng máy chủ.

### Linux

Mở terminal tại thư mục dự án (hoặc dùng `cd` để chuyển đến đó), sau đó chạy:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Nếu chưa có Python 3, cài Python 3 bằng trình quản lý gói của bản phân phối Linux bạn đang dùng. Nhấn `Ctrl+C` để dừng máy chủ.

### Docker

Cần cài và khởi động Docker trước. Chạy lệnh sau từ thư mục gốc của dự án để Nginx phục vụ các tệp hiện tại ở cổng `8080`:

**Windows PowerShell:**

```powershell
docker run --rm --name cv-portfolio -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS/Linux:**

```bash
docker run --rm --name cv-portfolio -p 8080:80 -v "$PWD:/usr/share/nginx/html:ro" nginx:alpine
```

Mở [http://localhost:8080](http://localhost:8080). Thư mục dự án được gắn ở chế độ chỉ đọc vào container, vì vậy các chỉnh sửa tệp trên máy sẽ được Nginx phục vụ mà không cần tạo Dockerfile. Nhấn `Ctrl+C` trong terminal để dừng và xóa container.

Nếu cổng `8080` đang được sử dụng, đổi phần `8080:80` thành một cổng khác, ví dụ `8081:80`, rồi mở `http://localhost:8081`.

## Thông tin liên hệ

- Tác giả: Thân Thế Anh
- Email hiển thị trên trang: `an.nguyen@example.com` (địa chỉ mẫu, cần thay bằng email thật)
- GitHub và LinkedIn: các đường dẫn hiện là thông tin mẫu; cập nhật trong phần Liên hệ của `index.html`.

## Giấy phép

Chưa khai báo giấy phép sử dụng cho dự án. Hãy bổ sung tệp `LICENSE` nếu muốn công khai điều kiện sử dụng hoặc phân phối mã nguồn.
