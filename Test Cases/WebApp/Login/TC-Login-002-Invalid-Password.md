---
tags:
  - test-case
  - QA
application: WebApp
screen: Login
function: Invalid Password
module: Authentication
priority: P1
status: draft
sprint: Sprint-2026-04
jira:
type: negative
---

# TC-Login-002: Invalid Password

## Preconditions

- User account exists in the system
- User is on the login page

---

## Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|------|--------|-----------------|---------------|--------|
| 1    | Navigate to login page | Login page loads |  |  |
| 2    | Enter valid email | Email is accepted |  |  |
| 3    | Enter wrong password | Password is masked |  |  |
| 4    | Click Login button | Error message "Invalid credentials" is shown |  |  |
| 5    | Verify no redirect | User remains on login page |  |  |

---

## Test Data

- Email: testuser@example.com
- Password: WrongPass!

---

## Notes

-
