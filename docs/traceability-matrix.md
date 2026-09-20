# Traceability Matrix — OrangeHRM QA Project

## Epic: Authentication (Login Module)

| Story ID | User Story | Test Cases (count) | Status Summary |
|---|---|---|---|
| OHRM-11 | As a user, I want to log in with valid credentials | 3 | Passed |
| OHRM-12 | As a user, I want to see a clear error with invalid credentials | 4 | 1 Failed (OHRM-31), 3 Passed |
| OHRM-13 | As a user, I want my session to end properly on logout | 3 | Passed |
| OHRM-14 | As a user, I want to be redirected to login if accessing a protected page while logged out | 2 | 1 Failed (OHRM-39 — rate-limiting), 1 Passed |
| **Total** | | **12** | **10 Passed / 2 Failed** |

## Epic: PIM — Employee Management

| Story | User Story | Test Cases (count) | Status Summary |
|---|---|---|---|
| PIM-Add | As an admin, I want to add a new employee record | 8 | Passed |
| PIM-Search | As an admin, I want to search for an employee by name/ID | 3 | Passed |
| PIM-Edit | As an admin, I want to edit an existing employee's details | 5 | Passed |
| PIM-Validation | As an admin, I want validation errors on incomplete/invalid data | 5 | 1 Failed (OHRM-43 — special characters), 4 Passed |
| **Total** | | **21** | **20 Passed / 1 Failed** |

## Epic: Leave Management

| Story | User Story | Test Cases (count) | Status Summary |
|---|---|---|---|
| Leave-Apply | As an employee, I want to apply for leave | 6 | 3 Blocked (OHRM-34, root cause — data persistence), 3 Passed |
| Leave-Balance | As an employee, I want to view my leave balance | 4 | 1 Failed (OHRM-38 — overlapping leave), 3 Passed |
| Leave-Status | As an employee, I want to see my leave request's approval status | 4 | 1 Failed (OHRM-35 — status display), 3 Passed |
| Leave-Approval | As an admin, I want to approve or reject leave requests | 4 | 1 Failed (OHRM-41), 3 Passed |
| **Total** | | **18** | **12 Passed / 3 Failed / 3 Blocked** |

## Grand Total

| Module | Test Cases | Passed | Failed | Blocked |
|---|---|---|---|---|
| Authentication | 12 | 10 | 2 | 0 |
| PIM | 21 | 20 | 1 | 0 |
| Leave Management | 18 | 12 | 3 | 3 |
| **Overall** | **51** | **42** | **6** | **3** |

**Coverage confirmation:** Every user story across all 3 epics has at least one linked test case, and every logged defect traces back to a specific failed or blocked test case — no untested requirements, no orphaned defects.
