# DEF-001: Register giữ lại thông báo lỗi cũ khi HTML validation chặn submit

## Trạng thái

OPEN

## Liên quan

- Test case: `TC-003`.
- Trang: `/register`.

## Các bước tái hiện

1. Gửi form với password 5 ký tự để nhận lỗi từ backend.
2. Đổi password thành hợp lệ.
3. Đổi email thành `invalid-email`.
4. Nhấn Đăng ký.

## Kết quả mong đợi

Chỉ hiển thị validation email hiện tại hoặc xóa thông báo backend cũ.

## Kết quả thực tế

Trình duyệt báo email sai định dạng nhưng trang vẫn hiển thị
`Password must be at least 6 characters` từ lần submit trước.

## Evidence

`reports/evidence/TC-003-register-invalid-email.png`
