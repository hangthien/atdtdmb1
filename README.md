# Website tĩnh - Hướng dẫn deploy

Trang tĩnh demo cho bài tập: giới thiệu thành viên nhóm và nội dung chính.

Files
- [index.html](index.html#L1) — trang chính.
- [styles.css](styles.css#L1) — style cơ bản.

Nội dung nhanh

1. Tạo repository trên GitHub (ví dụ `buoi1-static-site`).
2. Đẩy mã nguồn từ thư mục hiện tại lên GitHub.
3. Kết nối repository với Cloudflare Pages để deploy tự động.

Lệnh Git (chạy trong thư mục này):

```bash
git init
git branch -M main
git add .
git commit -m "Initial commit: static site"
git remote add origin https://github.com/hangthien/atdtdmb1.git
git push -u origin main
```

Kết nối với Cloudflare Pages

- Đăng nhập vào Cloudflare (tạo tài khoản nếu cần).
- Mở **Pages** → **Create a project** → **Connect to Git** và chọn GitHub.
- Chọn repository đã tạo và nhánh `main`.
- Framework preset: **None** (site tĩnh). Build command: để trống. Build output directory: để trống hoặc `/`.
- Nhấn **Save and Deploy**. Cloudflare sẽ build & deploy và cấp một domain `*.pages.dev`.

Phương án CLI (tùy chọn):

- Cài `wrangler` (Cloudflare):

```bash
npm install -g @cloudflare/wrangler
wrangler login
# Sau đó có thể dùng: wrangler pages publish ./ --project-name=<project>
```

Ghi chú

- Mở local: bạn có thể chạy bằng XAMPP hoặc mở trực tiếp file `index.html`.
- Nếu muốn dùng thư mục con làm root cho Pages, chỉ định `Publish directory` khi tạo project.
