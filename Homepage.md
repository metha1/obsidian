---
cssclasses:
  - home
banner: "![[360_F_886495385_XudXZcfZb7FqTwSWpDjwOEWfsol6Sw6e.jpg]]"
banner_y: 0.5
obsidianUIMode: preview
tag: home
publish: false
---

# QA Command Center

*"Quality is not an act, it is a habit."* — ***Aristotle***

---

```search-bar
only search bar
```

---

## Shortcuts

--- start-multi-column: shortcuts
```column-settings
Number of Columns: 3
Largest Column: standard
Border: off
Shadow: off
```

```button
name Daily Note
type command
action Daily notes: Open today's daily note
```

--- column-break ---

```button
name Bug Report
type command
action Templater: Create new note from template
```

--- column-break ---

```button
name Test Case
type command
action Templater: Create new note from template
```

--- end-multi-column






--- start-multi-column: shortcuts2
```column-settings
Number of Columns: 3
Largest Column: standard
Border: off
Shadow: off
```

```button
name Sprint Note
type command
action Templater: Create new note from template
```

--- column-break ---

```button
name Test Execution
type command
action Templater: Create new note from template
```

--- column-break ---

```button
name All Templates
type command
action Templater: Open insert template modal
```

--- end-multi-column

---

## Activity

--- start-multi-column: activity
```column-settings
Number of Columns: 2
Largest Column: standard
Border: off
Shadow: off
```

> [!clock] Modified Today
> ```dataview
> LIST
> WHERE file.mday = date(today) AND file.name != "Homepage"
> SORT file.mtime DESC
> ```

--- column-break ---

> [!new] Created This Week
> ```dataview
> LIST
> WHERE file.cday >= date(today) - dur(7 days)
> SORT file.ctime DESC
> LIMIT 10
> ```

--- end-multi-column

---

## Current Sprint

> [!sprint] Sprint Info
> ```dataview
> TABLE WITHOUT ID
>     file.link AS "Sprint",
>     start_date AS "Start",
>     end_date AS "End",
>     status AS "Status"
> FROM "Sprints"
> WHERE status = "active"
> SORT file.name DESC
> LIMIT 1
> ```

> [!kanban] Sprint Board
> [[Sprints/Sprint-2026-04-Kanban|Open Kanban Board]]

---

## Sprint Daily Notes

> [!info] Daily Notes — Current Sprint
> ```dataview
> TABLE WITHOUT ID
>     file.link AS "Date",
>     length(file.tasks) AS "Tasks"
> FROM "Daily Notes"
> WHERE sprint = "Sprint-2026-04"
> SORT file.name DESC
> LIMIT 10
> ```

---

## Sprint Bugs

--- start-multi-column: sprint-bugs
```column-settings
Number of Columns: 2
Largest Column: standard
Border: off
Shadow: off
```

> [!bug] Open Bugs — This Sprint
> ```dataview
> TABLE WITHOUT ID
>     file.link AS "Bug",
>     priority AS "P",
>     severity AS "Sev",
>     status AS "Status"
> FROM "Bugs"
> WHERE sprint = "Sprint-2026-04" AND status != "closed" AND status != "verified"
> SORT priority ASC
> ```

--- column-break ---

> [!success] Closed — This Sprint
> ```dataview
> TABLE WITHOUT ID
>     file.link AS "Bug",
>     priority AS "P",
>     status AS "Status"
> FROM "Bugs"
> WHERE sprint = "Sprint-2026-04" AND (status = "closed" OR status = "verified")
> SORT file.mtime DESC
> ```

--- end-multi-column

---

## Sprint Test Execution

> [!check] Test Runs — This Sprint
> ```dataview
> TABLE WITHOUT ID
>     file.link AS "Test Run",
>     date AS "Date",
>     passed AS "Pass",
>     failed AS "Fail",
>     blocked AS "Block"
> FROM "Test Executions"
> WHERE sprint = "Sprint-2026-04"
> SORT date DESC
> ```

> [!warning] Blocked Tests
> ```dataview
> LIST
> FROM "Test Cases"
> WHERE sprint = "Sprint-2026-04" AND status = "blocked"
> SORT file.name ASC
> ```

---

## Sprint Test Cases

> [!abstract] Test Cases — This Sprint
> ```dataview
> TABLE WITHOUT ID
>     file.link AS "Test Case",
>     application AS "App",
>     screen AS "Screen",
>     function AS "Function",
>     priority AS "P",
>     status AS "Status"
> FROM "Test Cases"
> WHERE sprint = "Sprint-2026-04"
> SORT application ASC, screen ASC, function ASC
> ```
