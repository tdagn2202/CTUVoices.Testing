# ADR-001: Tách tài liệu kiểm thử khỏi mã thực thi

## Trạng thái

Accepted

## Ngày

2026-08-05

## Bối cảnh

CTU Voices cần quản lý test plan, test case thủ công, test data và kết quả phục
vụ báo cáo mà không làm lẫn với mã nguồn ứng dụng và mã kiểm thử tự động.

## Quyết định

Repository `CTUVoices.Testing` lưu tài liệu kiểm thử, test data thủ công, ma trận
truy vết và báo cáo. Repository `CTUVoices` tiếp tục lưu mọi nội dung có khả năng
thực thi như unit test, integration test, API/E2E automation, script seed và
cleanup, Postman runner và performance test.

## Hệ quả

- Báo cáo và dữ liệu kiểm thử thủ công có vòng đời độc lập với source code.
- Test case có thể tham chiếu mã test data mà không chứa logic thực thi.
- Khi tự động hóa một test case, tài liệu giữ nguyên ở đây còn mã thực thi được
  liên kết từ repository `CTUVoices`.
