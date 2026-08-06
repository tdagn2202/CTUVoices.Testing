# CTUVoices.Testing

Kho tài liệu kiểm thử cho hệ thống CTU Voices. Repository này quản lý Test
Plan, test case end-to-end thực hiện thủ công, test data, ma trận truy vết và
kết quả kiểm thử phục vụ báo cáo.

Các thành phần thực thi như unit test, integration test, script seed/cleanup,
Postman runner và load test tiếp tục được quản lý trong repository `CTUVoices`.

## Cấu trúc

- `docs/test-plans/`: kế hoạch kiểm thử.
- `docs/requirements/`: yêu cầu và nguồn truy vết.
- `docs/decisions/`: quyết định tổ chức hoạt động kiểm thử.
- `test-cases/`: test case chia theo cụm chức năng.
- `test-data/xlsx/`: dữ liệu kiểm thử dạng Excel.
- `test-data/media/`: ảnh, video và tài liệu mẫu.
- `test-data/rag-documents/`: tài liệu dùng cho kiểm thử RAG.
- `traceability/`: ánh xạ yêu cầu, test case và test data.
- `reports/`: kết quả thực thi, defect và evidence.

## Quy ước

- Test case ID sử dụng `TC-XXX`, ví dụ `TC-001` và `TC-012`.
- Test data ID sử dụng `TD_<FEATURE>_<TYPE>_<SEQUENCE>`.
- Một test case chỉ kiểm tra một hành vi chính.
- Cột kết quả thực tế và đánh giá để trống trước khi thực thi.
- Test case được nhóm theo chức năng, không nhóm theo lớp hoặc endpoint kỹ thuật.

## Trạng thái hiện tại

Authentication Cycle 01 đã được thực thi trên localhost. Kết quả hiện tại gồm
19 `PASSED`, 2 `FAILED`, 6 `BLOCKED` và 10 `NOT_RUN`; xem báo cáo tại
`reports/execution-results/authentication-cycle-01.md`.
