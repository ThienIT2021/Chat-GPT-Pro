
# LicSys Demo (index.html + admin.html)

Demo quản lý và kích hoạt key chạy **hoàn toàn trên trình duyệt** (localStorage).

## Cách chạy nhanh
**Khuyến nghị dùng server cục bộ để đảm bảo cùng origin (localStorage dùng chung):**

### Cách 1: Python 3 (Windows/macOS/Linux)
```bash
cd licsys-demo
python -m http.server 5500
# Mở trình duyệt: http://localhost:5500/admin.html và http://localhost:5500/index.html
```

### Cách 2: Node (serve / http-server)
```bash
npm i -g serve
serve -p 5500 licsys-demo
```

> Tránh mở file trực tiếp dạng `file:///.../index.html` và `file:///.../admin.html` vì tùy trình duyệt, hai trang có thể **không dùng chung localStorage**.

## Quy trình thử nhanh
1) Mở `admin.html` → đăng nhập: **admin / admin123** (đổi mật khẩu ở mục Tài khoản).
2) Sang tab khác mở `index.html` → copy **Device ID**.
3) Quay lại `admin.html` → nhập tên user, thời hạn (giờ) → **Tạo key**.
4) Nhấn **Thêm thiết bị** cho key vừa tạo → dán **Device ID** đã copy.
5) Trả mã key cho người dùng → ở `index.html` nhập key → **Kích hoạt**.
6) Trang người dùng sẽ hiển thị **Tên user, mã key, thời gian còn lại, trạng thái**. Khi hết hạn sẽ tự thoát về màn hình nhập key.

## Lưu ý
- Đây là bản demo. Sản xuất cần backend an toàn (DB, xác thực, chống giả mạo...). 
- Xoá dữ liệu demo: mở DevTools Console và chạy `localStorage.clear(); sessionStorage.clear();`.
