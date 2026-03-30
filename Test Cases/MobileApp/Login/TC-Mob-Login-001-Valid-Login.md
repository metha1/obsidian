---
tags:
  - test-case
  - QA
application: MobileApp
screen: Login
function: Valid Login
module: Authentication
priority: P1
status: draft
sprint: Sprint-2026-04
jira:
type: functional
---

# TC-Mob-Login-001: Valid Login

## Preconditions

- App is installed on device
- User account exists

---

## Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|------|--------|-----------------|---------------|--------|
| 1    | Open the app | Splash screen, then login page |  |  |
| 2    | Enter valid email | Email field accepts input |  |  |
| 3    | Enter valid password | Password is masked |  |  |
| 4    | Tap Login | User is taken to Home Screen |  |  |

---

## Test Data

- Email: testuser@example.com
- Password: ValidPass123!

---

## Notes

- Test on both iOS and Android
