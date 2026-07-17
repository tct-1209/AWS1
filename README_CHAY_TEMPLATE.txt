HƯỚNG DẪN CHẠY TEMPLATE TRẦN CHÂU TRINH

1. Mở thư mục này bằng Visual Studio Code.

2. Chạy website ở máy local:
   hugo server -D --disableFastRender --ignoreCache --cleanDestinationDir

3. Link local mặc định:
   http://localhost:1313/AWS1/

4. Deploy GitHub Pages:
   - Giữ nguyên baseURL trong config.toml nếu repository là AWS1.
   - Push code lên nhánh main.
   - Vào Settings → Pages → Build and deployment → Source.
   - Chọn GitHub Actions.
   - Theo dõi workflow "Deploy Hugo site to GitHub Pages".

5. Link website sau khi deploy:
   https://tct-1209.github.io/AWS1/

LƯU Ý
- Không commit thư mục public vì GitHub Actions sẽ tự build lại.
- Tất cả file nội dung phải được lưu ở định dạng UTF-8.
- Ảnh sử dụng đường dẫn /AWS1/images/... và file thật nằm trong static/images/.

Thông tin sinh viên:
- Trần Châu Trinh
- Số điện thoại: 0365636878
- Email: tranchautrinh.2004@gmail.com
