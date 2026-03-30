---
tags:
  - test-case
  - QA
application: WebApp
screen: User Management
function: Create User
module: Admin
priority: P2
status: draft
sprint: Sprint-2026-04
jira:
type: functional
---

# TC-User-001: Create User

## Preconditions

- Admin user is logged in
- User Management page is accessible

---

## Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|------|--------|-----------------|---------------|--------|
| 1    | Navigate to User Management | User list page loads |  |  |
| 2    | Click "Add User" button | Create user form appears |  |  |
| 3    | Fill in required fields | All fields accept input |  |  |
| 4    | Click Save | Success message shown, user appears in list |  |  |

---

## Test Data

- Name: Test User
- Email: newuser@example.com
- Role: Viewer

---

## Notes

-
