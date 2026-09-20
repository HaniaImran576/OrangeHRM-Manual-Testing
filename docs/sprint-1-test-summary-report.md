# Test Summary Report — OrangeHRM QA Project

**Project:** OrangeHRM QA Testing (Authentication, PIM, Leave Management)
**Test Management:** Testworthy | **Defect Tracking:** Jira
**Report Date:** September 2026

## 1. Overview
This report summarizes the results of manual functional testing performed across the Authentication, PIM (Personnel Information Management), and Leave Management modules of the OrangeHRM open-source demo application.

**Note on tooling:** Testworthy's dashboard summary view displayed a total of 52 test cases and 4 pending, which does not reconcile with the actual module-level breakdown (51 total, 3 blocked). This report uses the verified module-level counts below, which are internally consistent and confirmed against individual test run results.

## 2. Overall Results

| Metric | Count |
|---|---|
| Total Test Cases | 51 |
| Executed (Passed + Failed) | 48 |
| Passed | 42 |
| Failed | 6 |
| Blocked (not executable) | 3 |
| **Pass Rate (of executed cases)** | **87.5%** |

## 3. Results by Module

| Module | Total | Passed | Failed | Blocked |
|---|---|---|---|---|
| Authentication | 12 | 10 | 2 | 0 |
| PIM | 21 | 20 | 1 | 0 |
| Leave Management | 18 | 12 | 3 | 3 |

## 4. Defects Logged

| Jira ID | Title | Module | Status |
|---|---|---|---|
| OHRM-31 | Login with invalid password does not display an error message. | Authentication | Open |
| OHRM-39 | System fails to enforce rate-limiting or account lockout after multiple rapid failed login attempts | Authentication | Open |
| OHRM-43 | System fails to reject invalid special characters (@, $, numbers) in employee name fields during creation/editing | PIM | Open |
| OHRM-35 | Leave request status displays as "Scheduled" instead of "Pending" immediately after submission | Leave Management | Open |
| OHRM-38 | Unable to execute overlapping leave validation test due to upstream leave request persistence and approval blockers | Leave Management | Open |
| OHRM-41 | System fails to allow or process leave applications with the same start and end date (Single-day leave) | Leave Management | Open |
| OHRM-34 | Leave request data persistence failure ("No records found" in Admin Leave List) | Leave Management | Open — linked to blocked test cases (root cause) |
| OHRM-36 | Submitted leave requests fail to sync/populate in Admin Leave List, blocking approval workflow | Leave Management | Duplicate of OHRM-34 — consolidated |
| OHRM-37 | Unable to execute leave rejection workflow due to missing request records in Admin queue | Leave Management | Duplicate of OHRM-34 — consolidated |

**Note on OHRM-34/36/37:** These three defects were initially logged separately, one per blocked test case. On review, all three were found to share the same underlying root cause. OHRM-36 and OHRM-37 were consolidated into OHRM-34 as duplicates, and all three affected test cases were re-linked to the single master defect (OHRM-34) rather than being tracked against three redundant reports.

## 5. Notable Finding
**OHRM-43 — Employee name field accepts invalid special characters.** During PIM testing, the employee first/last name fields were found to accept characters such as `@` and `$` without any validation error, while correctly accepting legitimate name punctuation (apostrophes, hyphens) in separate test cases. This confirms the gap is specific to genuinely invalid input, not an overly strict filter rejecting valid names. Classified as **Minor severity / Low–Medium priority**, since no downstream functional breakage was observed in this test session; would warrant re-evaluation if employee names feed into document generation, search indexing, or reporting elsewhere in the system.

## 6. Coverage Notes
Admin, Time/Attendance, Recruitment, Performance, Buzz, and Claims modules were explicitly out of scope for this project and were not tested — see Test Plan, Section 2, for the reasoning behind this scoping decision.

## 7. Overall Assessment
Authentication and PIM show strong reliability, with the majority of failures being validation-related rather than functional breakage. Leave Management surfaced the most significant issues, including a data-persistence-related defect currently blocking 3 test cases from execution. **Recommendation: Leave Management's blocking defect (OHRM-34) should be prioritized for resolution before further testing of dependent leave workflows can proceed.**
