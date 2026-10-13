# Day 7: System Testing & Integration Testing

## System Test Plan — At a Glance

![System Test Plan overview](README-Diagrams/system-test-plan-overview.png)

**Purpose:** Validate the application as a whole against system requirements, then verify that integrated modules and APIs work together correctly.

## Learning Objectives
- Understand system testing.
- Perform integration testing.
- Test the system as a whole.
- Validate integrated components.

## 1. Project Overview
Day 7 focuses on system-level validation, integration between components, and API checks. System testing evaluates the complete application against functional and non-functional requirements. Integration testing focuses on interfaces, data flow, and interactions between connected modules and services.

**Execution integrity:** Plans and expected results are documentation, not proof of execution. Mark Pass or Fail only after running the test and comparing the observed result with the expected result.

## 2. System Testing Approach
System testing validates the complete application against system requirements in a production-like test environment. It can include functional and non-functional validation.

![System testing approach](README-Diagrams/system-approach.png)

For the system test plan, define:
- Scope and objectives.
- System requirements and features to validate.
- Functional and non-functional test coverage.
- Test environment and test data.
- Preconditions, test steps, expected results, and entry/exit criteria.
- Evidence and execution status.

## 3. Types of System Testing

![Circular diagram of system testing types](README-Diagrams/system-testing-types.png)

| Type | Purpose |
|---|---|
| Functional system testing | Verify system features against requirements. |
| Performance testing | Check response time, throughput, and stability. |
| Security testing | Check access control and common security risks within authorized scope. |
| Usability testing | Check clarity and ease of use. |
| Compatibility testing | Check behavior across supported browsers, devices, and operating systems. |
| Reliability testing | Check consistent operation during repeated or sustained use. |
| Recovery testing | Check recovery after an interruption or failure where supported. |
| Regression testing | Check that existing behavior still works after changes. |
| Database testing | Check data accuracy and integrity where observable. |
| Load testing | Check behavior under a defined expected or peak workload. |

## 4. Integration Testing Approach
Integration testing verifies that combined modules, components, services, and APIs work together correctly. It checks interfaces, data flow, API requests and responses, and error handling.

![Integration testing component flow](README-Diagrams/integration-flow.png)

### Integration approaches

![Integration approaches diagram](README-Diagrams/integration-approaches.png)

- **Big Bang:** Integrate all components at once.
- **Top-Down:** Start with the top-level module and add lower-level modules.
- **Bottom-Up:** Start with lower-level modules and add higher-level modules.
- **Sandwich/Hybrid:** Combine top-down and bottom-up integration.

## 5. API Testing Basics with Postman
Understand REST APIs and manually validate requests and responses using Postman.

- **HTTP methods:** GET, POST, PUT, DELETE (the collection also includes PATCH).
- **Status codes to understand:** 200, 404, 500, plus any endpoint-specific expected codes.
- **JSON:** Inspect request and response bodies.
- **Validation:** Check status code, response body, fields, data types, and error behavior.

The provided Postman collection contains 11 example requests against JSONPlaceholder. Import `API-Testing/Postman-Collection.json`, review the variables and assertions, run the collection, and record observed results in `API-Testing/API-Test-Results.xlsx`.

**Demo API limitation:** JSONPlaceholder simulates POST, PUT, PATCH, and DELETE responses; changes do not persist to its underlying data. Do not report those responses as proof of persistent create/update/delete operations.

## 6. Integration Scenarios to Practice
- Login module + Dashboard module.
- Search module + Results module.
- Cart module + Payment module.
- Form module + Database module.

Only execute scenarios that are supported by the selected application and environment. For each one, identify the interface, the exchanged data, the expected behavior, and how the result can be observed.

## 7. Identify Integration Points
- Module interfaces.
- Data exchange points.
- API endpoints.
- Database interactions.
- Authentication and authorization boundaries.
- Error responses and dependency failures.

## 8. Integration Test Case Design
Create test cases that cover:
- Module A + Module B interactions.
- Data flow validation.
- API request/response validation.
- Error handling between modules.
- Positive and negative input.
- Authorization and data consistency where applicable.

The integration workbook contains 56 planned test cases. Record the actual result, status, evidence, and defect ID where relevant.

## 9. Test Execution and Reporting

![Test execution workflow](README-Diagrams/execution-flow.png)

- **Pass:** Actual result matches the expected result.
- **Fail:** Actual result differs from the expected result; capture evidence and a defect reference.
- **Blocked:** Environment, access, test data, or dependency issues prevent execution.
- **Not Executed:** The test has not been run.
- **Not Applicable:** The scenario does not apply; explain why.

Pass rate = Passed ÷ (Passed + Failed) × 100, when at least one test has a Pass or Fail result. Do not count Blocked or Not Executed cases as Pass.

## 10. Test Environment and Data Setup
- Record the exact application/API URL and environment.
- Record execution date/time, browser/client version, Postman version, and build/version when available.
- Use authorized test accounts and synthetic data.
- Never commit passwords, access tokens, or sensitive personal data.
- Record unsupported scenarios and environment limitations.

## 11. GitHub Repository Folder Structure
```text
Day-7-System-and-Integration-Testing/
├── README.md
├── README-Google-Docs.docx
├── README-Diagrams/
│   ├── system-test-plan-overview.png
│   ├── system-approach.png
│   ├── system-testing-types.png
│   ├── integration-flow.png
│   ├── integration-approaches.png
│   └── execution-flow.png
├── System-Testing/
│   ├── System-Test-Plan.md
│   ├── System-Test-Plan-Google-Docs.docx
│   └── System-Test-Plan.xlsx
├── Integration-Testing/
│   ├── Integration-Test-Strategy.md
│   ├── Integration-Test-Strategy-Google-Docs.docx
│   └── Integration-Test-Cases.xlsx
├── API-Testing/
│   ├── API-Testing-Approach.md
│   ├── API-Testing-Approach-Google-Docs.docx
│   ├── Postman-Collection.json
│   └── API-Test-Results.xlsx
└── Test-Execution/
    ├── Test-Execution-Report.md
    ├── Test-Execution-Report-Google-Docs.docx
    └── Test-Execution-Report.xlsx
```
