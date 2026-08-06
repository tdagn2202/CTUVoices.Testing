# User Profile — Avatar and Student Card OCR Test Suite

## Phạm vi cycle 01

1. Upload, thay thế và xóa ảnh đại diện.
2. Validation dung lượng ảnh đại diện tại ngưỡng 30MB.
3. OCR thẻ sinh viên với MSSV mới.
4. Từ chối MSSV đã thuộc tài khoản khác.
5. Từ chối ảnh không phải thẻ sinh viên.
6. Validation dung lượng ảnh OCR tại ngưỡng 30MB.

## Tài khoản thực thi

- Tài khoản chính: `e2e_profile_1`.
- Baseline: chưa có avatar, MSSV hoặc ảnh thẻ sinh viên.
- Tài khoản `ctu_student` đang sở hữu MSSV `B2203551`, được dùng làm
  business state cho trường hợp trùng MSSV; không cần đăng nhập tài khoản này.

Kết quả cycle 01 được ghi trong workbook
`user-profile-avatar-ocr-test-cases.xlsx` và báo cáo tại
`reports/execution-results/user-profile-avatar-ocr-cycle-01.md`.
