# OrangeHRM QA Testing Project

Manual QA testing project on [OrangeHRM](https://opensource-demo.orangehrmlive.com/) (an open-source HR management platform), covering Authentication, PIM (Personnel Information Management), and Leave Management modules — managed end-to-end using **Jira** (epics, stories, defect tracking) and **Testworthy** (test case management and execution).

## Key Findings (at a glance)
- **52 test cases** executed across 3 modules
- **42 passed / 6 failed / 4 pending** — **87.5% pass rate**
- Notable defect: employee name field in PIM accepts invalid special characters (`@`, `$`, numbers) with no validation — see [OHRM-43](#) for full details
- Identified and consolidated 2 duplicate defect reports that stemmed from a single root cause, rather than leaving them as separate tickets

## Scope
**In scope:** Login/Authentication, PIM (add/search/edit employee records), Leave Management (apply, view balance, approval workflow).
**Out of scope:** Admin, Time/Attendance, Recruitment, Performance, Buzz, Claims — excluded to keep this project focused and fully completable within a realistic timeframe.

## Tools Used
| Tool | Purpose |
|---|---|
| Jira | Epic/Story management, sprint tracking, defect (bug) tracking |
| Testworthy | Test case design, test run execution, pass/fail tracking |

## Project Structure
```
orangehrm-qa-project/
├── README.md
├── docs/
│   ├── test-plan.md
│   ├── traceability-matrix.xlsx
│   └── sprint-1-test-summary-report.md
├── exports/
│   ├── testworthy-test-cases.csv
│   └── jira-defects.csv
└── screenshots/
    ├── jira-backlog-sprint1.png
    ├── jira-backlog-defects.png
    ├── testworthy-test-run-detail.png
    ├── testworthy-runs-overview.png
    ├── testworthy-test-overview-dashboard.png
    └── jira-defect-ohrm43-detail.png
```

## How This Project Was Run
1. Explored the OrangeHRM demo manually before writing any test cases.
2. Created 3 Epics in Jira (Authentication, PIM, Leave Management), each broken into user stories.
3. Wrote 52 test cases in Testworthy, linked back to their corresponding Jira stories.
4. Executed all test cases across 3 test runs, recording results in Testworthy.
5. Logged every genuine defect in Jira with full reproduction steps, severity, and priority — linked to its source test case.
6. Consolidated duplicate defect reports once identified, rather than leaving redundant tickets open.
7. Produced a final test summary report and traceability matrix (see `/docs`).

## Notable Defect Example
**OHRM-43 — System fails to reject invalid special characters (@, $, numbers) in employee name fields**
Employee records were successfully created and edited using clearly invalid characters (e.g., `@`, `$`) in the first/last name fields, with no validation error shown. Legitimate special characters in real names (apostrophes, hyphens — e.g., O'Brien, Smith-Jones) were correctly accepted, confirming this is specifically a validation gap for non-name characters, not an overly strict filter. See `/docs/sprint-1-test-summary-report.md` for full defect details and severity reasoning.

## Full Documentation
- [Test Plan](./docs/test-plan.md)
- [Test Summary Report](./docs/sprint-1-test-summary-report.md)
- [Traceability Matrix](./docs/traceability-matrix.xlsx)
- Raw exports of all test cases and defects in `/exports`
