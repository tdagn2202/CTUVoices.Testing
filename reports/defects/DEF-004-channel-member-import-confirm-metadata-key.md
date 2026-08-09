# DEF-004 — Channel member import confirmation fails on activity metadata validation

## Summary

The Staff member-import preview correctly validates the uploaded XLSX, but confirming the valid rows fails with HTTP 400. No valid member is added.

## Environment

- Date: 2026-08-09
- Web client: `http://localhost:3000`
- Account: `e2e_staff_1` (`STAFF`, course `OWNER`)
- Course: `E2E Staff Course 20260809`
- Channel ID: `channel_20260809111048_dc60d29d`
- Test case: `TC-056`

## Steps to Reproduce

1. Open the E2E course as its Staff owner.
2. Open course management and member import.
3. Upload `test-data/xlsx/channel-member-import-mixed.xlsx`.
4. Confirm that the preview reports one valid row and four invalid rows.
5. Select **Add valid rows**.

## Expected Result

The valid account `e2e_course_student_2` is added once. Existing, duplicate, missing and unknown rows are skipped.

## Actual Result

The confirmation request returns HTTP 400 and the UI displays:

`Metadata key is not allowed for CHANNEL_MEMBER_ADDED: importedMemberCount`

The valid Student remains outside the course.

## Request Evidence

- Method: `POST`
- Endpoint: `/api/channels/channel_20260809111048_dc60d29d/members/import/confirm`
- Status: `400`
- Submitted valid row: `B2600002` / `E2E Course Student 2`
- Screenshot: `reports/evidence/staff-course-cycle-01/TC-056-member-import-failed.png`

## Impact

Staff users can preview bulk imports but cannot complete them. Individual member addition remains functional.
