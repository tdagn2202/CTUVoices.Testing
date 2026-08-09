# Staff Course Management — Test Cycle 01

## Environment

- Execution date: 2026-08-09
- Application: CTU Voices web client (`http://localhost:3000`)
- Test account: `e2e_staff_1`
- Test cases: `TC-052`–`TC-060`
- Execution method: Browser-based manual E2E testing with DevTools evidence

## Results

| Test Case | Result | Evidence | Notes |
|---|---|---|---|
| TC-052 | PASS | `reports/evidence/staff-course-cycle-01/TC-052-course-created.png` | Course created; Staff became OWNER. |
| TC-053 | PASS | `reports/evidence/staff-course-cycle-01/TC-053-course-limit-zero.png` | Student limit 0 was rejected by the client. |
| TC-054 | PASS | `reports/evidence/staff-course-cycle-01/TC-054-member-added.png` | Student 1 added using MSSV. |
| TC-055 | PASS | `reports/evidence/staff-course-cycle-01/TC-055-member-validation.png` | Existing and unknown candidates were rejected. |
| TC-056 | FAIL | `reports/evidence/staff-course-cycle-01/TC-056-member-import-failed.png` | HTTP 400; see DEF-004. |
| TC-057 | PASS | `reports/evidence/staff-course-cycle-01/TC-057-regular-course-post.png` | Regular post published. |
| TC-058 | PASS | `reports/evidence/staff-course-cycle-01/TC-058-official-announcement.png` | Official announcement label displayed. |
| TC-059 | PASS | `reports/evidence/staff-course-cycle-01/TC-059-post-pinned.png` | Pin and unpin persisted correctly. |
| TC-060 | PASS | `reports/evidence/staff-course-cycle-01/TC-060-member-authorization.png` | Normal member had no manager-only controls. |

## Residual Test Data

- The E2E course and its posts are intentionally retained because the current web client does not provide course deletion.

## Defects

- `DEF-004`: Bulk member import confirmation fails activity metadata validation.

## Summary

- Passed: 8
- Failed: 1
- Not run: 0
- Result: **8/9**
