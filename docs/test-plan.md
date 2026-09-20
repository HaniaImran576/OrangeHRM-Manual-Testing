# Test Plan: OrangeHRM QA Practice Project

**Project:** OrangeHRM QA Testing
**Prepared by:** Hania Imran
**Version:** 1.0
**Date:** September 2026

## 1. Objective
Verify core Authentication, PIM (Personnel Information Management), and Leave Management functionality on the OrangeHRM open-source demo application through structured manual testing.

## 2. Scope

**In Scope:**
- Login/Authentication (valid/invalid login, session handling, access control)
- PIM — adding, viewing, editing, and searching employee records
- Leave Management — applying for leave, viewing balance/history, approval workflow

**Out of Scope:**
- Admin module
- Time/Attendance
- Recruitment
- Performance
- Buzz
- Claims

These modules were deliberately excluded to keep the project focused, thoroughly tested, and completable within a realistic timeframe, rather than superficially covering the entire application.

## 3. Test Approach
Manual, black-box functional testing using positive, negative, and boundary-value test design techniques. No test automation was used in this phase (noted as a possible future extension).

Testing was structured around 3 Jira Epics (one per module), broken into user stories, with detailed test cases written and executed in Testworthy and linked back to their originating stories.

## 4. Test Environment
- **Application:** OrangeHRM open-source demo (`opensource-demo.orangehrmlive.com`)
- **Browser:** [your browser/version]
- **OS:** [your OS]
- **Test Management:** Testworthy (test cases, test runs)
- **Defect Tracking:** Jira (Scrum project, "OrangeHRM" space)

## 5. Entry Criteria
- Demo environment accessible
- Test cases written, reviewed, and linked to their Jira stories

## 6. Exit Criteria
- All planned test cases executed at least once
- All genuine findings logged as Jira defects with full reproduction steps, severity, and priority
- Duplicate defects identified and consolidated
- Test summary report completed

## 7. Roles & Responsibilities
All test design, execution, and defect management performed by a single tester (Hania) as an independent learning project.

## 8. Risks & Assumptions
- This is a shared public demo instance — data may be reset or modified by other users at any time, which can affect result repeatability. This is treated as a known environmental limitation, not a product defect, when encountered.
- Some previously-reported issues on this demo (sourced from other public QA practice projects) were used to inform specific test case design; any confirmed here are noted as independently verified, not assumed.

## 9. Deliverables
- Test Plan (this document)
- Test cases (Testworthy, exported to `/exports`)
- Traceability Matrix
- Defect reports (Jira, exported to `/exports`)
- Test Summary Report
