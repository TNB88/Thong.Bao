# Thông báo từ xa cho các ứng dụng Bình Pro

Mỗi ứng dụng đọc một file JSON riêng. Sửa hoặc bật file nào chỉ ảnh hưởng ứng dụng đó:

| Ứng dụng | File cấu hình |
|---|---|
| Rổ Phim+ | `ro-phim-plus.json` |
| Kodi 21.3 | `kodi-21-3.json` |
| Phim Rạp | `phim-rap.json` |
| Phim 4K v2.6.1 TorBox + HH3D | `phim4k-2-6-1-torbox-hh3d.json` |
| Phim 4K v2.6.6 TorBox | `phim4k-2-6-6-torbox.json` |
| TVQ8 1.0.10 v58 | `tvq8.json` |

## Bật thông báo

1. Mở đúng file của ứng dụng.
2. Đổi `enabled` thành `true`.
3. Sửa `title` và `message`.
4. Đổi `id` sang giá trị mới mỗi khi muốn app hiện một thông báo mới, ví dụ `phim-rap-2026-09-06-01`.
5. Commit thay đổi vào nhánh `main`.

## Tắt thông báo

Đổi `enabled` thành `false` rồi commit. App sẽ tải cấu hình mới khi được mở lại và sẽ không hiện hộp thoại.

## Ý nghĩa trường

- `enabled`: công tắc bật/tắt riêng của app.
- `id`: mã duy nhất của thông báo. Khi `show_once=true`, cùng một `id` chỉ hiện một lần trên thiết bị.
- `title`: tiêu đề hộp thoại.
- `message`: nội dung thông báo.
- `button_text`: chữ trên nút mở liên kết.
- `button_url`: liên kết HTTPS hoặc Telegram; để trống thì không hiện nút này.
- `close_text`: chữ trên nút đóng.
- `show_once`: `true` chỉ hiện một lần cho mỗi `id`; `false` hiện lại ở lần khởi động tiến trình tiếp theo.
- `dismissible`: cho phép đóng bằng nút Back/chạm ngoài hộp thoại.

Mỗi app có file riêng; sửa file nào chỉ ảnh hưởng app đó. TVQ8 dùng `tvq8.json`. Không xóa hoặc đổi tên file vì URL đã được khóa trong thư viện native của từng APK.
