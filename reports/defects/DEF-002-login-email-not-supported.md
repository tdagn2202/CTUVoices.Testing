# DEF-002: Login bằng email không hoạt động dù nhãn UI cho phép

## Trạng thái

OPEN

## Liên quan

- Test case: `TC-011`.
- Trang: `/login`.

## Các bước tái hiện

1. Tạo tài khoản có username `e2e_auth_20260805_001` và email
   `e2e.auth.20260805.001@example.com`.
2. Mở trang Login.
3. Nhập email hợp lệ và đúng password.
4. Nhấn Đăng nhập.

## Kết quả mong đợi

Đăng nhập thành công vì trường được ghi là `Email hoặc tên đăng nhập`.

## Kết quả thực tế

API trả `401` và giao diện hiển thị `Invalid username or password`. Cùng mật
khẩu đó đăng nhập bằng username thành công.

## Evidence

`reports/evidence/TC-011-login-by-email.png`
