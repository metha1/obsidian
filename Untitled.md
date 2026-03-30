---
sprint: Sprint-2026-04
start_date: 2026-03-30
end_date: 2026-04-10
status: active
tags:
  - sprint
  - QA
---

# Sprint-2026-04

**Duration:** 2026-03-30 to 2026-04-10
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

## Sprint Kanban

[[Sprints/Sprint-2026-04-Kanban|Open Kanban Board]]

---

## Bug Summary

```dataview
TABLE WITHOUT ID
    file.link AS "Bug",
    priority AS "Priority",
    severity AS "Severity",
    status AS "Status"
FROM "Bugs"
WHERE sprint = "Sprint-2026-04"
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
WHERE sprint = "Sprint-2026-04"
SORT date DESC
```

---

## Daily Notes

```dataview
TABLE WITHOUT ID
    file.link AS "Date",
    length(file.tasks) AS "Tasks"
FROM "Daily Notes"
WHERE sprint = "Sprint-2026-04"
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
