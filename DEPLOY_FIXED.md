# Deploy bản đã sửa lên GitHub Pages

Project đã được sửa cho repository `AWS1`:

- `baseURL`: `https://tct-1209.github.io/AWS1/`
- Ảnh dùng đường dẫn `/AWS1/images/...`
- Logo trở về trang chủ bằng permalink của Hugo, không còn hard-code `/aws/`
- Nội dung tiếng Việt được lưu chuẩn UTF-8
- Font dùng bộ font hệ thống hỗ trợ đầy đủ dấu tiếng Việt
- Thư mục `public` cũ có đường dẫn localhost đã được làm sạch

## Cách cập nhật

Sao chép toàn bộ file trong thư mục này vào project Git hiện tại, nhưng giữ lại thư mục `.git` của project đang dùng. Sau đó chạy:

```bash
git add .
git commit -m "Fix GitHub Pages paths and Vietnamese encoding"
git push origin main
```

Trong GitHub, mở **Settings → Pages → Build and deployment → Source** và chọn **GitHub Actions**.

Sau khi workflow `Deploy Hugo site to GitHub Pages` hoàn tất, mở:

`https://tct-1209.github.io/AWS1/`
