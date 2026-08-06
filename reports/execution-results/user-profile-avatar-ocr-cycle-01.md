# User Profile — Avatar and Student Card OCR Test Execution, Cycle 01

## Thông tin vòng chạy

| Thuộc tính | Giá trị |
|---|---|
| Ngày thực hiện | 2026-08-06 |
| Tài khoản | `e2e_profile_1` |
| Môi trường | Frontend `localhost:3000`; backend `localhost:8080`; n8n `localhost:5678` |
| Phương pháp | Functional end-to-end qua trình duyệt cô lập |
| Phạm vi | Avatar upload/remove; Student Card OCR; validation 30MB |

Backend liveness và readiness đều `UP`. Health tổng hợp tại thời điểm bắt đầu
hiển thị `DOWN`, nhưng các dịch vụ trong phạm vi kiểm thử vẫn đáp ứng.

## Tổng hợp

| Trạng thái | Số lượng |
|---|---:|
| PASSED | 8 |
| FAILED | 1 |
| BLOCKED | 0 |
| NOT_RUN | 0 |
| Tổng | 9 |

## Kết quả chính

- JPEG và GIF đều được chấp nhận làm avatar.
- Ảnh vượt 30MB bị FE chặn trước khi gửi request ở cả avatar và OCR.
- Avatar được xóa thành công sau chuỗi kiểm thử.
- OCR nhận đúng thẻ test: `B2400000`, `NGUYỄN CAPYBARA`, ngành `Thú y`,
  thời hạn `2024-2028`.
- Thẻ chứa MSSV trùng `B2203551` bị từ chối và không ghi đè hồ sơ hiện tại.
- Ảnh không phải thẻ bị từ chối vì không tìm thấy MSSV hợp lệ.
- File avatar `30,740,000` bytes bị Next.js proxy từ chối ở giới hạn 10MB,
  được ghi nhận tại `DEF-003`.

## Dữ liệu phát sinh và cleanup

- Phiên test đã logout.
- Avatar đã được xóa bằng chức năng của hệ thống.
- Fixture tạm dùng cho Chrome đã được xóa.
- Thông tin OCR positive được giữ lại trên `e2e_profile_1`: MSSV `B2400000`,
  họ tên `NGUYỄN CAPYBARA`, ngành `Thú y`, thời hạn `2024-2028`.
- UI hiện không cung cấp chức năng xóa thẻ/MSSV, vì vậy không thực hiện cleanup
  bằng SQL hoặc chỉnh DB thủ công.

## Defect

- `DEF-003`: Profile upload dưới 30MB bị proxy từ chối ở giới hạn 10MB.

Không sửa source code hoặc cấu hình trong vòng chạy này.
