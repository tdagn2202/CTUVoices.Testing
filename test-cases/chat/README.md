# Chat Test Suite (Android App)

## Phạm vi chức năng (Android Chat Module)

Bộ test case cho chức năng Trò chuyện trực tuyến (Real-time Chat) trên ứng dụng di động Android (`ctu_voices_android`), bao gồm 10 kịch bản kiểm thử thủ công từ `TC-100` đến `TC-109`:

1. **Gửi tin nhắn văn bản (TC-100)**: Gửi tin nhắn direct hợp lệ đến tài khoản liên hệ.
2. **Kiểm tra Validation tin nhắn rỗng (TC-101)**: Ngăn chặn gửi tin nhắn chỉ chứa khoảng trắng hoặc rỗng.
3. **Gửi đính kèm hình ảnh (TC-102)**: Chọn và gửi file ảnh JPEG (< 10MB) từ thư viện Android.
4. **Đồng bộ tin nhắn real-time (TC-103)**: Nhận tin nhắn đến tức thì khi đang mở màn hình chat qua WebSocket.
5. **Cập nhật Badge tin nhắn chưa đọc (TC-104)**: Tăng số đếm tin nhắn chưa đọc tại danh sách cuộc trò chuyện và tab bar.
6. **Xóa Trạng thái Chưa đọc (TC-105)**: Tự động đánh dấu đã đọc và xóa badge khi người dùng mở cuộc trò chuyện.
7. **Tìm kiếm Cuộc trò chuyện (TC-106)**: Lọc danh sách trò chuyện theo tên hoặc username liên hệ.
8. **Chặn liên lạc người dùng bị Block (TC-107)**: Ngăn gửi và nhận tin nhắn đối với tài khoản nằm trong danh sách chặn.
9. **Xử lý Mất kết nối Mạng & Gửi lại (TC-108)**: Giữ trạng thái tin nhắn chờ khi offline và cho phép gửi lại khi khôi phục kết nối.
10. **Xóa lịch sử cuộc trò chuyện (TC-109)**: Xóa cuộc trò chuyện khỏi danh sách trên ứng dụng Android.

## Điều kiện trước khi thực thi

- Backend Spring Boot (`ctu_voices`) và MySQL đang hoạt động.
- Dịch vụ WebSocket/Real-time messaging phục vụ chat đang reachable từ Android Studio Emulator.
- Ứng dụng Expo Android (`ctu_voices_android`) được khởi chạy trên Android Studio Emulator hoặc thiết bị thật.
- Chuẩn bị đầy đủ các tài khoản test đã khai báo trong workbook test data: `test-data/xlsx/android-chat-test-data.xlsx`.

## Tài liệu liên quan

- Workbook Test Case: `test-cases/chat/android-chat-test-cases.xlsx`
- Workbook Test Data: `test-data/xlsx/android-chat-test-data.xlsx`
- Ma trận Truy vết Test Case - Test Data: `traceability/test-case-data-map.csv`
