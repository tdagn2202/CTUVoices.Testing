# Test Plan: CTU Voices Functional End-to-End Testing

## 1. Thông tin tài liệu

| Thuộc tính | Giá trị |
|---|---|
| Hệ thống | CTU Voices |
| Loại kiểm thử chính | Functional end-to-end testing thủ công |
| Môi trường mục tiêu | Localhost / môi trường test cục bộ |
| Trạng thái | ACTIVE |
| Ngày khởi tạo | 2026-08-05 |

## 2. Mục tiêu

Xác nhận từng chức năng của CTU Voices hoạt động đúng theo yêu cầu nghiệp vụ,
validation, phân quyền và chuyển đổi trạng thái quan sát được từ góc nhìn người
dùng. Kết quả được ghi nhận theo từng test case để phục vụ báo cáo.

## 3. Phạm vi

Các cụm chức năng dự kiến:

1. Authentication.
2. User Profile và Student Card OCR.
3. Posts và Post Drafts.
4. Post Interactions.
5. User Interactions.
6. Channels.
7. Chat.
8. Notifications.
9. Search and Trends.
10. Reports and Moderation.
11. RAG Chatbot.
12. Administration.

Performance, load, unit và integration testing không phải nội dung chính của
đợt kiểm thử thủ công này. Khi cần thực thi tự động, mã và script nằm trong
repository `CTUVoices`.

## 4. Chiến lược kiểm thử

- Kiểm thử lần lượt theo từng cụm chức năng.
- Trong mỗi cụm, kiểm thử từng hành vi độc lập.
- Bao phủ trường hợp positive, negative, boundary, authorization và business
  state khi phù hợp.
- Thực hiện theo thứ tự phụ thuộc: Authentication trước các chức năng yêu cầu
  phiên đăng nhập.
- Ghi kết quả thực tế, trạng thái và evidence ngay sau mỗi lần thực thi.

## 5. Định dạng test case

Mỗi test case gồm:

- Test Case ID theo định dạng `TC-XXX`.
- Cụm chức năng và chức năng cụ thể.
- Mô tả và điều kiện tiên quyết.
- Test data được tham chiếu bằng `TD_*`.
- Các bước thực hiện.
- Kết quả mong đợi.
- Kết quả thực tế.
- Trạng thái `NOT_RUN`, `PASSED`, `FAILED` hoặc `BLOCKED`.
- Ghi chú và đường dẫn evidence.

## 6. Quản lý test data

Test data thủ công được quản lý chủ yếu dưới dạng `.xlsx`. Media và tài liệu RAG
được lưu ở thư mục riêng, sau đó được tham chiếu từ workbook bằng mã test data.
Script sinh hoặc nạp dữ liệu, nếu cần, phải nằm trong repository code.

## 7. Điều kiện bắt đầu

- Chức năng thuộc cụm kiểm thử đã chạy được trên localhost.
- Test case của cụm đã được review.
- Test data cần thiết đã có trạng thái `READY`.
- Điều kiện tiên quyết và tài khoản sử dụng đã được xác định.
- Có cách nhận biết và dọn dữ liệu phát sinh sau kiểm thử.

## 8. Điều kiện kết thúc

- Tất cả test case trong phạm vi có trạng thái cuối cùng.
- Test case thất bại có defect hoặc ghi chú giải thích.
- Kết quả thực tế và evidence cần thiết đã được lưu.
- Dữ liệu phát sinh đã được xử lý theo kế hoạch cleanup.
- Có bản tổng hợp kết quả cho cụm chức năng.

## 9. Quy tắc đánh giá

| Trạng thái | Ý nghĩa |
|---|---|
| NOT_RUN | Chưa thực hiện |
| PASSED | Kết quả thực tế khớp kết quả mong đợi |
| FAILED | Kết quả thực tế không khớp kết quả mong đợi |
| BLOCKED | Không thể thực hiện do thiếu điều kiện hoặc lỗi phụ thuộc |

## 10. Thứ tự thực hiện

Cụm đầu tiên là Authentication, lần lượt gồm Register, Login, Forgot Password,
Verify Reset OTP, Reset Password, Change Password và Logout. Chỉ bắt đầu thực
thi sau khi test case và test data của cụm này được hoàn thiện và review.
