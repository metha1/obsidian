# QA Command Center — Obsidian Vault

A ready-to-use Obsidian vault for Software QA Engineers. Track daily testing, sprints, bugs, test cases, and test executions from a single dashboard.

---

## Quick Start

1. Download/clone this vault
2. Open it in [Obsidian](https://obsidian.md/) (File > Open Vault)
3. Install the required community plugins (see below)
4. Enable the CSS snippets in Settings > Appearance > CSS Snippets
5. Restart Obsidian — the Homepage opens automatically

---

## Required Plugins

Install these from **Settings > Community Plugins > Browse**:

| Plugin | Purpose |
|--------|---------|
| **Dataview** | Powers all dashboard tables and queries |
| **Calendar** | Sidebar calendar widget — click a date to create/open daily notes |
| **Templater** | Dynamic templates with date variables |
| **Homepage** | Auto-opens Homepage.md on startup in Reading View |
| **Buttons** | Shortcut buttons on the dashboard |
| **Multi-Column Markdown** | Side-by-side column layouts |
| **Home Tab** | Search bar on the homepage |
| **Banners** | Banner image at the top of the homepage |
| **Kanban** | Drag-and-drop sprint task board |

---

## Vault Structure

```
.
├── Homepage.md                    # Main dashboard (open in Reading View)
├── Daily Notes/                   # Daily testing logs (one per day)
├── Sprints/                       # Sprint notes + Kanban boards
├── Bugs/                          # Bug/defect reports
├── Test Cases/                    # Organized by Application > Screen > Function
│   ├── WebApp/
│   │   ├── Login/
│   │   ├── Dashboard/
│   │   └── User Management/
│   ├── MobileApp/
│   │   ├── Login/
│   │   └── Home Screen/
│   └── API/
│       ├── Authentication/
│       └── Users/
├── Test Executions/               # Batch test run logs
├── Test Plans/                    # Strategy documents
├── Templates/                    # Note templates
│   ├── Daily Testing Note.md
│   ├── Sprint Note.md
│   ├── Bug Report.md
│   ├── Test Case.md
│   └── Test Execution Log.md
└── Attachments/                   # Images, screenshots, files
    └── banners/                   # Homepage banner images
```

---

## How to Use

### Daily Testing

1. Click the **Daily Note** button on the Homepage, or click a date on the Calendar sidebar
2. A daily note is created from the template with standup fields, test execution log, and end-of-day summary
3. Fill in your standup notes, log test results, and note any bugs found
4. All daily notes appear in the "Sprint Daily Notes" section on the Homepage

### Sprint Management

1. Click **Sprint Note** to create a new sprint
2. Set `status: active` in the frontmatter — it shows up on the Homepage
3. Open the linked **Kanban Board** to track tasks visually (Backlog > To Do > In Progress > Blocked > Done)
4. When the sprint ends, change `status` to `completed` and create a new sprint

### Bug Reporting

1. Click **Bug Report** to create a new bug
2. Fill in the frontmatter fields:
   - `sprint`: link it to the current sprint (e.g., `Sprint-2026-04`)
   - `priority`: P1, P2, P3, P4
   - `severity`: critical, major, minor, trivial
   - `status`: open, in-progress, fixed, closed, verified
3. Bugs appear in the Sprint Bugs section on the Homepage

### Test Cases

1. Click **Test Case** to create a new test case
2. Save it in the right folder: `Test Cases/[App]/[Screen]/TC-Name.md`
3. Fill in the frontmatter fields:
   - `application`: WebApp, MobileApp, API, etc.
   - `screen`: Login, Dashboard, User Management, etc.
   - `function`: what the test verifies
   - `sprint`: link to the sprint
   - `status`: draft, ready, in-progress, done, blocked
4. Test cases are grouped by App > Screen > Function on the Homepage

### Test Execution

1. Click **Test Execution** to log a batch test run
2. Record pass/fail/blocked counts in the frontmatter
3. Fill in the results table with individual test case outcomes
4. Test runs appear in the Sprint Test Execution section

---

## Homepage Sections

| Section | What it shows |
|---------|--------------|
| **Shortcuts** | Quick-create buttons for daily notes, bugs, test cases, sprints |
| **Activity** | Notes modified today and created this week |
| **Current Sprint** | Active sprint info + Kanban board link |
| **Sprint Daily Notes** | Daily notes linked to the current sprint |
| **Sprint Bugs** | Open vs closed bugs for the current sprint |
| **Sprint Test Execution** | Test runs and blocked tests for the current sprint |
| **Sprint Test Cases** | Test cases by App/Screen/Function for the current sprint |

### Right Sidebar
- **Calendar** — click any date to open/create a daily note
- **Local Graph** — visual map of note connections for the current file

---

## Starting a New Sprint

1. Create a new sprint note from the template
2. Create a new Kanban board (copy `Sprint-2026-04-Kanban.md` and rename)
3. Update the `status` field:
   - New sprint: `status: active`
   - Old sprint: `status: completed`
4. Update the sprint references in `Homepage.md`:
   - Search for `Sprint-2026-04` and replace with your new sprint name (e.g., `Sprint-2026-05`)
5. Tag new daily notes, bugs, and test cases with the new sprint name

---

## Frontmatter Reference

### Daily Note
```yaml
date: "2026-03-30"
tags: [daily, QA]
sprint: Sprint-2026-04
```

### Sprint Note
```yaml
sprint: Sprint-2026-04
start_date: 2026-03-30
end_date: 2026-04-10
status: active          # active | completed
tags: [sprint, QA]
```

### Bug Report
```yaml
tags: [bug, QA]
sprint: Sprint-2026-04
priority: P1            # P1 | P2 | P3 | P4
severity: critical      # critical | major | minor | trivial
status: open            # open | in-progress | fixed | closed | verified
module: Authentication
jira: PROJ-123
environment: staging
build: v2.1.0
date_found: "2026-03-30"
```

### Test Case
```yaml
tags: [test-case, QA]
application: WebApp     # WebApp | MobileApp | API
screen: Login
function: Valid Login
module: Authentication
priority: P1
status: draft           # draft | ready | in-progress | done | blocked
sprint: Sprint-2026-04
jira: PROJ-456
type: functional        # functional | negative | regression | smoke | integration
```

### Test Execution Log
```yaml
tags: [test-execution, QA]
date: "2026-03-30"
sprint: Sprint-2026-04
build: v2.1.0
environment: staging
passed: 15
failed: 3
blocked: 2
```

---

## CSS Snippets

Located in `.obsidian/snippets/`:

| Snippet | Purpose |
|---------|---------|
| `dashboard.css` | Homepage styling — gradient title, dark cards, button styles, calendar accent, callout colors |
| `folder-style.css` | Sidebar folder descriptions and color-coded borders |

Enable them in **Settings > Appearance > CSS Snippets**.

---

## Settings

- **Readable line length** is disabled (`app.json`) so content uses full width
- **Daily notes** are configured to save in `Daily Notes/` with format `YYYY-MM-DD`
- **Homepage plugin** opens `Homepage.md` in Reading View on startup
- **Calendar** starts weeks on Monday

---

## Tips

- Always view the Homepage in **Reading View** (click the book icon or Ctrl+E) for the dashboard to render properly
- Use the Calendar sidebar to quickly navigate between daily notes
- The Local Graph in the right sidebar shows how your current note connects to others
- Use `Ctrl+P` to open the command palette for quick access to any action
- Link bugs to test cases using `[[TC-Name]]` wiki links for traceability
- Add screenshots to bug reports by dragging images into the note (saved to `Attachments/`)
