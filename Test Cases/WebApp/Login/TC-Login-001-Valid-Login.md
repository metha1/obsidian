---
tags:
  - test-case
  - QA
application: WebApp
screen: Login
function: Valid Login
module: Authentication
priority: P1
status: draft
sprint: Sprint-2026-04
jira:
type: functional
---

# TC-Login-001: Valid Login

## Preconditions

- User account exists in the system
- User is on the login page

---

## Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|------|--------|-----------------|---------------|--------|
| 1    | Navigate to login page | Login page loads with email and password fields |  |  |
| 2    | Enter valid email | Email is accepted |  |  |
| 3    | Enter valid password | Password is masked |  |  |
| 4    | Click Login button | User is redirected to Dashboard |  |  |

---

## Test Data

- Email: testuser@example.com
- Password: ValidPass123!

---

## Notes

-

---

## Linked Bugs

```dataview
LIST
FROM "Bugs"
WHERE contains(file.outlinks, this.file.link)
```
