# Day 6 – End-to-End (E2E) Testing: Banking Scenarios

## Project Details
- **Project Name:** ParaBank Demo
- **Module Name:** Banking – End-to-End Scenarios
- **Created Date:** 12-10-2026
- **Application URL:** https://parabank.parasoft.com/parabank/index.htm

## Objective
Validate complete banking workflows in the ParaBank demo, including login, account overview, account details, transaction history, fund transfers, and logout.

## E2E Banking Scenarios

| Test Case ID | Scenario | Expected Result | Status |
|---|---|---|---|
| E2E-BA-001 | Log in with valid demo credentials | User logs in and account overview is displayed. | Not Executed |
| E2E-BA-002 | Log in with invalid credentials | Login is rejected and an error message is displayed. | Not Executed |
| E2E-BA-003 | View account overview | Available accounts and balances are displayed. | Not Executed |
| E2E-BA-004 | Open account details | Selected account details are displayed correctly. | Not Executed |
| E2E-BA-005 | View transaction history | Transactions for the selected account are displayed. | Not Executed |
| E2E-BA-006 | Transfer funds between eligible demo accounts | Transfer result is displayed and the transfer is processed. | Not Executed |
| E2E-BA-007 | Verify balances after transfer | Account balances reflect the completed transfer correctly. | Not Executed |
| E2E-BA-008 | Submit invalid transfer details | Invalid or incomplete transfer is rejected with validation feedback. | Not Executed |
| E2E-BA-009 | Open an available account service | Selected account service page opens successfully. | Not Executed |
| E2E-BA-010 | Log out after banking workflow | User session ends successfully. | Not Executed |

## Execution Notes
1. Open the ParaBank demo URL above.
2. Use only demo credentials and demo accounts. Do not enter real banking information.
3. Run each scenario and record the actual result.
4. Mark unsupported features **N/A** and record the reason.
5. Do not mark a scenario Pass without executing it.

## Status Definitions
- **Not Executed:** Not run yet.
- **Pass:** Actual result matches expected result.
- **Fail:** Actual result differs from expected result.
- **Blocked:** Testing cannot continue due to an issue.
- **N/A:** Feature or scenario does not apply.
