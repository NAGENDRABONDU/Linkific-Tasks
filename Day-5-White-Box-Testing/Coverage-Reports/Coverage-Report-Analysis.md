# Coverage Report Analysis

## 1. Objective

To understand how code coverage reports help testers identify untested code and improve test coverage.

## 2. What Is a Coverage Report?

A coverage report shows which parts of the source code were executed during automated test execution and which parts were not executed.

It helps testers identify gaps in their test cases.

## 3. Types of Code Coverage

**Statement Coverage**

Measures the percentage of executable statements executed by the test cases.

Formula:

Statement Coverage = (Executed Statements / Total Executable Statements) × 100

**Branch Coverage**

Measures whether every possible decision outcome, such as True and False, has been executed.

Formula:

Branch Coverage = (Executed Branches / Total Branches) × 100

**Path Coverage**

Measures the percentage of feasible execution paths executed during testing.

Formula:

Path Coverage = (Executed Paths / Total Feasible Paths) × 100

## 4. Sample Coverage Report

Consider a login validation function with four branch outcomes.

| Coverage Metric | Total | Covered | Coverage |
|---|---:|---:|---:|
| Statement Coverage | 5 | 5 | 100% |
| Branch Coverage | 4 | 2 | 50% |

Note: These are illustrative figures, not results from an actual coverage tool. The statement and branch figures are independent examples and should not be treated as a report from the same test run.

## 5. Coverage Report Analysis

If a report shows 100% statement coverage but only 50% branch coverage:

- All executable statements may have been executed.
- Some True or False decision outcomes remain untested.
- Additional test cases are required to execute the missing branches.
- The test suite should be rerun to verify the updated coverage.

## 6. Common Coverage Tools

**JaCoCo**

A code coverage tool for Java applications. It generates reports for metrics such as instruction, line, and branch coverage.

**Istanbul / NYC**

JavaScript code coverage tools used to measure which parts of JavaScript code are executed by tests.

**Coverage.py**

A Python tool that measures code coverage and generates reports showing executed and missing lines.

## 7. How Testers Use Coverage Reports

1. Run the automated test suite.
2. Generate the code coverage report.
3. Identify statements or branches that were not executed.
4. Design additional test cases for uncovered logic.
5. Rerun the tests and review the updated report.
6. Share coverage gaps with developers when necessary.

## 8. Important Limitations

- High code coverage does not guarantee defect-free software.
- Coverage indicates code execution, not whether every result was checked correctly.
- Requirements-based testing and negative testing are also necessary.
- Coverage targets depend on project risks and requirements.

## 9. Conclusion

Coverage reports help testers measure test completeness at the code level and identify missing test scenarios. They support better test design but must be combined with other testing techniques.