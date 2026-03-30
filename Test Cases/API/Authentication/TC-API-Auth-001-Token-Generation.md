---
tags:
  - test-case
  - QA
application: API
screen: Authentication
function: Token Generation
module: Auth
priority: P1
status: draft
sprint: Sprint-2026-04
jira:
type: functional
---

# TC-API-Auth-001: Token Generation

## Preconditions

- API server is running
- Valid client credentials exist

---

## Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|------|--------|-----------------|---------------|--------|
| 1    | POST /auth/login with valid credentials | 200 OK with access token |  |  |
| 2    | Verify token format | JWT format with header.payload.signature |  |  |
| 3    | Verify token expiry | Token expires in configured time |  |  |
| 4    | Use token in Authorization header | Subsequent API calls succeed |  |  |

---

## Test Data

```json
{
  "email": "testuser@example.com",
  "password": "ValidPass123!"
}
```

---

## Notes

-
