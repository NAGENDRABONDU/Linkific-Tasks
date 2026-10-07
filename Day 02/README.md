# ShoppersStack – Day 2 Test Case Writing

## 1. Objective

The purpose of this Day 2 activity is to practice writing clear, effective, and reusable software test cases for the ShoppersStack application.

## 2. Test Case Components

Each test case contains:

- Test Scenario ID
- Test Scenario Description
- Test Case ID
- Test Case Description
- Test Steps
- Preconditions
- Test Data
- Post Conditions
- Expected Result
- Actual Result
- Status
- Priority
- Severity

## 3. Test Scenario vs Test Case

**Test Scenario:** Describes what needs to be tested at a high level.

**Test Case:** Describes how to test a scenario using detailed steps, test data, and expected results.

**Relationship:** One test scenario can contain multiple test cases.

## 4. Test Case Design Techniques

### Equivalence Partitioning
Divide input data into valid and invalid groups and test representative values.

### Boundary Value Analysis
Test values at, just below, and just above the boundaries.

### Decision Table Testing
Test different combinations of conditions and their expected results.

### State Transition Testing
Verify system behavior when it moves from one state to another.

### Use Case Testing
Create test cases based on real user interactions and business flows.

## 5. Effective Test Case Writing Guidelines

- Write clear and concise test cases.
- Give every test case a unique ID.
- Keep test cases independent where possible.
- Use specific and understandable test steps.
- Provide realistic test data.
- Write measurable expected results.
- Avoid ambiguous language.
- Make test cases reusable.
- Keep test cases traceable to requirements or scenarios.
- Review test cases before execution.

## 6. Naming Convention

### Test Scenario ID
Use:

`TS_<MODULE>_<NUMBER>`

Example:

`TS_LOGIN_001`

### Test Case ID
Use:

`TC_<MODULE>_<NUMBER>`

Example:

`TC_LOGIN_001`

## 7. Status

- **Not Executed:** Test case has not been executed.
- **Pass:** Actual result matches the expected result.
- **Fail:** Actual result does not match the expected result.
- **Blocked:** Test execution cannot continue because of a dependency or blocker.

## 8. Priority

- **High:** Important functionality that should be tested first.
- **Medium:** Normal business functionality.
- **Low:** Less important functionality.

## 9. Severity

- **Critical:** The defect prevents the application or major functionality from working.
- **Major:** Important functionality is significantly affected.
- **Minor:** Small issue with limited impact.

## 10. Test Suite Organization

Related test cases should be grouped into test suites.

Example:

```text
ShoppersStack
├── Login Testing
│   ├── Login Scenarios
│   └── Login Test Cases
├── Signup Testing
│   ├── Signup Scenarios
│   └── Signup Test Cases
└── Traceability Matrix
```

## 11. Traceability

The Traceability Matrix connects requirements or scenarios with their corresponding test cases.

It helps to verify:

- Test coverage
- Missing test cases
- Requirement-to-test mapping
- Overall testing completeness

## 12. Test Execution

Before execution:

1. Review the test case.
2. Verify the preconditions.
3. Prepare the required test data.
4. Execute each test step.
5. Record the actual result.
6. Update the status.
7. Report defects for failed test cases.

## 13. Day 2 Deliverables

- Test Case Template
- Login Test Scenarios
- Login Test Cases
- Signup Test Scenarios
- Signup Test Cases
- Traceability Matrix
- README with Test Case Writing Guidelines

## 14. Project

**Application:** ShoppersStack

**Modules Covered:**
- Login
- Signup / Registration

**Created By:** Nagendra

**Created Date:** 07-10-2026
