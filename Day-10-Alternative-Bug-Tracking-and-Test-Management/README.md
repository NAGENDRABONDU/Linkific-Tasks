# Day 10 — Alternative Bug Tracking Tools & Test Management

## Learning Objectives
- Compare common bug-tracking and test-management tools.
- Document the TestRail project and test-management structure used in practice.
- Understand execution results, defect references, testing metrics, and reports.
- Record the failed-test-to-Jira-defect workflow.

## 1. Tools Comparison Matrix

| Tool | Main use | Strengths | Considerations |
|---|---|---|---|
| Bugzilla | Defect tracking | Mature issue fields, search, configurable workflows | Interface and administration may feel less modern |
| MantisBT | Defect tracking | Lightweight, open-source option, simple issue workflow | Dedicated test-management features are limited by default |
| Azure DevOps | Work items and delivery lifecycle | Boards, queries, repositories, pipelines, test-related workflows | Broad platform; setup can be more involved |
| GitHub Issues | Issue tracking near source code | Labels, milestones, collaboration, pull-request links | Dedicated test-case management may need another tool |
| Redmine | Project and issue tracking | Projects, trackers, workflows, plugins | Capabilities depend on configuration and plugins |
| TestRail | Test case and execution management | Reusable cases, sections, runs, results, reporting, defect references | Dedicated defect tracking is usually handled in a linked tracker |
| Zephyr | Test management | Test cases and execution connected to Jira workflows | Features depend on the product/edition |
| qTest | Test management | Test planning, execution, traceability, reporting | Commercial platform with organization-specific setup |
| Spreadsheet | Basic test tracking | Accessible and flexible for a small exercise | Manual maintenance and weaker traceability at scale |

*This is a high-level learning comparison, not a live pricing quotation. Features and pricing can vary by edition and vendor plan.*

## 2. TestRail Project Setup

The project was named **Shopper Stack Release Q1**. The workspace included Project Overview, Test Cases, Test Runs & Results, Milestones, and Reports. Login scenarios were organized under **Login and Authentication**.

A test case describes the scenario and expected behavior. A test run groups cases for an execution cycle. A result records what happened when a case was executed.

## 3. Test Management Structure

| Level | Recorded item | Purpose |
|---|---|---|
| Project | Shopper Stack Release Q1 | Main workspace for the exercise |
| Section | Login and Authentication | Groups related login scenarios |
| Test case T1 | Verify login with valid credentials | Checks successful authentication |
| Test case T2 | Verify login fails with an invalid password | Checks rejection of incorrect credentials |
| Test run R1 | Login Regression - Run 1 | Groups T1 and T2 for one execution cycle |
| Results | T1 Passed; T2 Failed | Records the saved outcome of each case |
| Jira defect | SHOP-35 | Tracks the login behavior issue associated with T2 |

### T1 — Valid credentials
Precondition: a registered active test account exists and the application is accessible. The steps covered opening the login page, entering the registered username, entering the correct password, and clicking Login.

### T2 — Invalid password
The case followed the login sequence with an incorrect password. The expected final behavior was rejection of the login, display of an appropriate error message, and no authenticated session.

## 4. Testing Metrics Dashboard

The saved TestRail run showed two test cases: one Passed and one Failed.

| Metric | Calculation | Value | Meaning |
|---|---|---:|---|
| Total tests | All selected cases | 2 | Two cases were included |
| Executed tests | Total tests − Untested | 2 | Both cases had a recorded result |
| Execution rate | Executed ÷ Total × 100 | 100% | Every selected case had a result |
| Pass rate | Passed ÷ Executed × 100 | 50% | One of two recorded results passed |
| Fail rate | Failed ÷ Executed × 100 | 50% | One of two recorded results failed |

Execution rate does not mean every test passed. The report's **Completed** field showed **No**, so the run's completion/closure state was separate from the fact that both cases had recorded results.

## 5. Test Execution Reports

A TestRail report named **Day 10 - Login Test Execution Summary** was generated for **Login Regression - Run 1**. It summarized the run and included activity, progress, and a results table showing T1 as Passed and T2 as Failed.

The TestRail Add Result form supported an overall status, comments, step-level outcomes, assignment, version, elapsed time, and a **Defects** field.

### Failed Test Follow-up: Logging the Defect in Jira

After T2, **Verify login fails with an invalid password**, was marked Failed in TestRail, the issue was logged in Jira in the **Shopper Stack V2** project. Jira issue **SHOP-35** was created with the summary **“Login behavior is incorrect when an invalid password is entered.”** The issue description recorded the precondition, reproduction steps, expected behavior, and actual-result details.

The Jira issue key **SHOP-35** was then entered in the **Defects** field for the failed TestRail result. This connects the failed execution record to the defect record and supports traceability between the test outcome and its investigation.

The report showed one Passed test and one Failed test. The saved status and defect reference do not independently prove that automatic integration synchronization is configured.

## Conclusion

Day 10 covered tool comparison, TestRail project setup, test-management structure, execution metrics, defect traceability, and report generation. The saved run showed one Passed result and one Failed result. After the failed test was recorded, Jira issue **SHOP-35** was created and referenced from the failed TestRail result. This connects the test outcome with the defect investigation and makes the QA record easier to trace and explain.
