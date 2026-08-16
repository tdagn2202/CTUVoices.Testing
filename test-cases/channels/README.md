# Course Channel Test Suite

Documentation and test artifacts for the **Course Channel (Kênh môn học)** module of CTU Voices (Web Staff Management and Android Mobile Client).

## Overview

This test suite validates the end-to-end functionality of Course Channels across user roles (Student, Owner/Lecturer, Co-admin/Teaching Assistant) including channel discovery, join request lifecycle, member management, shared content filtering, notification preferences, and pinned announcements.

---

## File Structure

- `android-course-channel-test-cases.xlsx`: Mobile test cases for Android application (`TC-110` to `TC-119`).
- `staff-course-management-test-cases.xlsx`: Web staff management test cases (`TC-052` to `TC-060`).
- `../../test-data/xlsx/android-course-channel-test-data.xlsx`: Corresponding test data sets (`TD_ANDROID_COURSE_*`).

---

## Suite Summary (`TC-110` to `TC-119`)

| Test Case ID | Feature / Action | Scope | Primary Test Data |
|---|---|---|---|
| `TC-110` | Discover and search course channels | Discovery Search | `TD_ANDROID_COURSE_SEARCH_VALID_001` |
| `TC-111` | Send join request to private channel | Join Request | `TD_ANDROID_COURSE_PRIVATE_TARGET_001` |
| `TC-112` | Approve pending join request | Channel Management | `TD_ANDROID_COURSE_PENDING_REQUEST_001` |
| `TC-113` | Reject pending join request | Channel Management | `TD_ANDROID_COURSE_REJECT_REQUEST_001` |
| `TC-114` | Promote member to Co-admin role | Member Roster | `TD_ANDROID_COURSE_MEMBER_TO_PROMOTE_001` |
| `TC-115` | Filter shared files and links | Shared Content | `TD_ANDROID_COURSE_WITH_MEDIA_001` |
| `TC-116` | Update notification preferences | Channel Settings | `TD_ANDROID_COURSE_TARGET_001` |
| `TC-117` | Leave course channel | Student Membership | `TD_ANDROID_COURSE_TARGET_001` |
| `TC-118` | Pin and unpin announcement post | Feed Moderation | `TD_ANDROID_COURSE_POST_TO_PIN_001` |
| `TC-119` | Add member directly by Student Code (MSSV) | Member Import/Add | `TD_ANDROID_COURSE_STUDENT_MSSV_001` |

---

## Execution Preconditions

1. **Backend Server**: Active CTU Voices API service running locally or on staging.
2. **Android App**: Expo / Android build signed in with designated student (`TD_ANDROID_COURSE_STUDENT_001`) or lecturer/owner (`TD_ANDROID_COURSE_OWNER_001`) accounts.
3. **Database Seeding**: Ensure target test channels and sample posts/requests are seeded.
