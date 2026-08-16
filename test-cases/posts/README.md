# Post Operations Test Suite

Documentation and test artifacts for the **Posts Operations (Quản lý & Đăng bài viết)** module of CTU Voices (Web & Mobile Clients).

## Overview

This test suite validates the core post management lifecycle, including creating public text/image posts, handling empty post validations, posting anonymously, draft saving and editing, AI content moderation rejections, submitting post appeals, publishing official course announcements, deleting owned posts, and filtering feeds by post types.

---

## File Structure

- `post-operations-test-cases.xlsx`: Test case suite for post operations (`TC-120` to `TC-129`).
- `../../test-data/xlsx/post-operations-test-data.xlsx`: Corresponding test data sets (`TD_POST_OP_*`).
- `../../traceability/test-case-data-map.csv`: Central traceability mapping matrix.

---

## Suite Summary (`TC-120` to `TC-129`)

| Test Case ID | Feature / Action | Scope | Primary Test Data |
|---|---|---|---|
| `TC-120` | Create a valid public text post | Post Creation | `TD_POST_OP_TEXT_VALID_001` |
| `TC-121` | Prevent publishing an empty post without text/media | Input Validation | `TD_POST_OP_TEXT_EMPTY_001` |
| `TC-122` | Create a post with multiple image attachments | Media Upload | `TD_POST_OP_IMAGES_VALID_001` |
| `TC-123` | Create an Anonymous Post (Đăng bài ẩn danh) | Post Privacy | `TD_POST_OP_ANONYMOUS_VALID_001` |
| `TC-124` | Save, edit, and publish a Post Draft | Draft Lifecycle | `TD_POST_OP_DRAFT_VALID_001` |
| `TC-125` | Handle AI Content Moderation Rejection | Moderation Guard | `TD_POST_OP_TOXIC_CONTENT_001` |
| `TC-126` | Submit an appeal for a rejected post | Post Appeal | `TD_POST_OP_REJECTED_POST_001` |
| `TC-127` | Publish Official Announcement Post in Course Channel | Channel Feed | `TD_POST_OP_ANNOUNCEMENT_VALID_001` |
| `TC-128` | Delete own post as Author | Post Management | `TD_POST_OP_TARGET_MY_POST_001` |
| `TC-129` | Filter feed posts by post type | Feed Filtering | `TD_POST_OP_FILTER_TYPE_001` |

---

## Execution Preconditions

1. **Backend API**: CTU Voices backend service active with AI moderation filter enabled.
2. **User Session**: Authenticated user session for student (`TD_POST_OP_ACCOUNT_STUDENT_001`) or lecturer (`TD_POST_OP_ACCOUNT_LECTURER_001`).
3. **Storage & Media**: Media upload endpoint (`/api/media/upload`) configured with S3/Cloudinary or local dev storage.
