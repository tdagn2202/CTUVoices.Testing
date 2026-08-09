# Admin Management — Test Cycle 01

## Environment

- Execution date: 2026-08-09
- Application: CTU Voices web client (`http://localhost:3000`)
- Test account: `ctuvoices_admin`
- Test cases: `TC-061`–`TC-069`
- Execution method: Browser-based manual E2E testing with DevTools evidence

## Results

| Test Case | Result | Evidence | Notes |
|---|---|---|---|
| TC-061 | PASS | `reports/evidence/admin-management-cycle-01/TC-061-user-search-filter.png` | Search and Student filter returned consistent results. |
| TC-062 | PASS | `reports/evidence/admin-management-cycle-01/TC-062-user-blocked.png` | BLOCKED persisted; final status restored to ACTIVE. |
| TC-063 | PASS | `reports/evidence/admin-management-cycle-01/TC-063-user-staff-role.png` | Staff role persisted; final role restored to STUDENT. |
| TC-064 | PASS | `reports/evidence/admin-management-cycle-01/TC-064-user-verified.png` | User verified with B2600003. |
| TC-065 | PASS | `reports/evidence/admin-management-cycle-01/TC-065-statistics-overview.png` | Metrics and seven-day charts rendered. |
| TC-066 | PASS | `reports/evidence/admin-management-cycle-01/TC-066-rag-pdf-uploaded.png` | PDF uploaded with ingestion disabled. |
| TC-067 | PASS | `reports/evidence/admin-management-cycle-01/TC-067-rag-file-validation.png` | Unsupported and empty files were rejected. |
| TC-068 | PASS | `reports/evidence/admin-management-cycle-01/TC-068-rag-retrieval.png` | 2/2 PDFs, 15 chunks; all known facts retrieved. |
| TC-069 | PASS | `reports/evidence/admin-management-cycle-01/TC-069-rag-cleanup.png` | Returned to 1/1 PDF and 14 chunks. |

## Residual Test Data

- RAG database records and Cloudinary assets may remain after UI deactivation; all artifacts use explicit E2E names.

## Defects

- None.

## Summary

- Passed: 9
- Failed: 0
- Not run: 0
- Result: **9/9**
