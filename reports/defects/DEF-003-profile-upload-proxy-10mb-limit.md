# DEF-003: Profile upload dưới 30MB bị proxy từ chối ở giới hạn 10MB

## Trạng thái

OPEN

## Liên quan

- Test case: `TC-040`.
- Chức năng: User Profile — Avatar upload.
- Môi trường: frontend `localhost:3000`, backend `localhost:8080`.

## Mô tả

FE công bố và kiểm tra giới hạn ảnh profile là 30MB. Tuy nhiên, một ảnh
`30,740,000` bytes, nhỏ hơn giới hạn `31,457,280` bytes của ứng dụng, bị lớp
proxy của Next.js từ chối ở giới hạn `10,485,760` bytes.

## Các bước tái hiện

1. Đăng nhập bằng `e2e_profile_1`.
2. Mở Trang cá nhân → Chỉnh sửa hồ sơ.
3. Chọn đổi ảnh đại diện.
4. Upload `TD_PROFILE_AVATAR_BOUNDARY_UNDER_30MB_001.jpg`.

## Kết quả mong đợi

Request được chuyển đến backend và avatar được cập nhật vì file không vượt
30MB.

## Kết quả thực tế

- FE gửi `PUT /api/users/me/avatar`.
- Response: HTTP `400`.
- Thông báo: `File size too large. Got 30740000. Maximum is 10485760.`
- Avatar không được cập nhật.

## Evidence

`reports/evidence/TC-040-avatar-under-30mb.png`

## Ảnh hưởng

Các file từ trên 10MB đến 30MB vượt qua validation FE nhưng không thể hoàn tất
upload end-to-end. Giới hạn quan sát được không thống nhất giữa FE, proxy và
backend.

## Ghi chú xử lý

Chưa thay đổi source hoặc cấu hình trong vòng kiểm thử. Việc điều chỉnh giới
hạn proxy cần được planning và triển khai riêng trong repository code.
