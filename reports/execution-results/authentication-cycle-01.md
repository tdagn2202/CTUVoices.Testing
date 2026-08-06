# Authentication Test Execution — Cycle 01

## Thông tin vòng chạy

| Thuộc tính | Giá trị |
|---|---|
| Ngày thực hiện | 2026-08-05 |
| Môi trường | Frontend `localhost:3000`; backend `localhost:8080` |
| Backend readiness | `UP` tại `localhost:8081` |
| Phương pháp | Manual end-to-end qua trình duyệt cô lập |
| Phạm vi | Register; Login; Forgot Password; Verify OTP negative; Reset Password negative; Logout |

## Tổng hợp

| Trạng thái | Số lượng |
|---|---:|
| PASSED | 19 |
| FAILED | 2 |
| BLOCKED | 6 |
| NOT_RUN | 10 |
| Tổng | 37 |

## Dữ liệu phát sinh

- Một tài khoản tổng hợp được tạo: `e2e_auth_20260805_001`.
- Email: `e2e.auth.20260805.001@example.com`.
- Tài khoản được giữ lại để tiếp tục Change Password và các test phụ thuộc.
- Logout đã tạo bản ghi revoke cho token của phiên TC-035.

## Defect phát hiện

- `DEF-001`: thông báo lỗi của lần submit trước không được xóa khi HTML validation chặn lần submit mới.
- `DEF-002`: UI cho phép đăng nhập bằng email nhưng backend chỉ xác thực bằng username.

## Test bị chặn

- Locked và unverified login chưa có fixture trạng thái tài khoản.
- Luồng OTP positive chưa có mailbox test nhận OTP.
- Reset token positive và reused-token phụ thuộc luồng OTP.

## Phạm vi chưa thực hiện

- Các trường thiếu riêng lẻ chưa chạy hết vì đã xác nhận cơ chế HTML required ở trường đầu tiên.
- Change Password chưa thực hiện trong cycle này.
- Missing-token và revoked-token logout sẽ thực hiện ở cycle tiếp theo.

Không sửa source code hoặc cấu hình trong vòng chạy này.
