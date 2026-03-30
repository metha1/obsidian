---
sprint: Sprint-XX
start_date: YYYY-MM-DD
end_date: YYYY-MM-DD
status: active
tags:
  - sprint
  - QA
---

# Sprint-XX

**Duration:** {{start_date}} to {{end_date}}
**Status:** Active

---

## Sprint Goals

1.
2.
3.

---

## Test Scope

### In Scope
-

### Out of Scope
-

### Environments
-

---

## Sprint Board

> [!todo] To Do
> ```dataview
> TASK
> FROM "Daily Notes"
> WHERE sprint = this.sprint AND !completed
> ```

> [!doing] In Progress
> ```dataview
> LIST
> FROM "Test Cases"
> WHERE sprint = this.sprint AND status = "in-progress"
> ```

> [!done] Done
> ```dataview
> LIST
> FROM "Test Cases"
> WHERE sprint = this.sprint AND status = "done"
> ```

---

## Bug Summary

```dataview
TABLE WITHOUT ID
    file.link AS "Bug",
    priority AS "Priority",
    severity AS "Severity",
    status AS "Status"
FROM "Bugs"
WHERE sprint = this.sprint
SORT priority ASC
```

---

## Test Execution Summary

```dataview
TABLE WITHOUT ID
    file.link AS "Test Run",
    date AS "Date",
    passed AS "Passed",
    failed AS "Failed",
    blocked AS "Blocked"
FROM "Test Executions"
WHERE sprint = this.sprint
SORT date DESC
```

---

## Daily Notes

```dataview
TABLE WITHOUT ID
    file.link AS "Date",
    length(file.tasks) AS "Tasks"
FROM "Daily Notes"
WHERE sprint = this.sprint
SORT file.name ASC
```

---

## Sprint Retrospective

### What went well
-

### What didn't go well
-

### Action items
- [ ]

---

## Metrics

| Metric | Count |
|--------|-------|
| Total Test Cases | |
| Passed | |
| Failed | |
| Blocked | |
| Bugs Raised | |
| Bugs Closed | |
| Bug Reopen Rate | |

