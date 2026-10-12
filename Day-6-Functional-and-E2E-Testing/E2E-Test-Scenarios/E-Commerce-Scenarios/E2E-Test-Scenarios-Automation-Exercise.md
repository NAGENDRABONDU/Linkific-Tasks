# Day 6 – End-to-End (E2E) Testing

## Project Details
- **Project Name:** Automation Exercise
- **Module Name:** End-to-End Testing
- **Created Date:** 12-10-2026
- **Application URL:** https://automationexercise.com/

## Objective
Verify complete user workflows across connected features, from starting an action through to its final result.

## Scope
Scenarios cover browsing products, account registration and login, searching, product details, cart actions, checkout where supported, and logout. Use only test accounts and safe test data. Do not enter real payment details.

## E2E Test Scenarios

| Test Case ID | Scenario | Expected Result | Status |
|---|---|---|---|
| E2E-001 | Open the website and browse products | Home page and product listing load successfully. | Not Executed |
| E2E-002 | Register a new test account | Registration completes and the account is created. | Not Executed |
| E2E-003 | Log in with a registered test account | User logs in and the logged-in state is displayed. | Not Executed |
| E2E-004 | Search for an existing product | Relevant matching products are displayed. | Not Executed |
| E2E-005 | View product details | The selected product details are displayed. | Not Executed |
| E2E-006 | Add a product to the cart | The selected product appears in the cart. | Not Executed |
| E2E-007 | Update cart quantity where supported | Quantity and total update correctly. | Not Executed |
| E2E-008 | Remove a product from the cart | The selected product is removed from the cart. | Not Executed |
| E2E-009 | Proceed through checkout using safe test data, where supported | Checkout proceeds and a confirmation/result is displayed. | Not Executed |
| E2E-010 | Log out after completing the workflow | User session ends successfully. | Not Executed |

## Execution Notes
1. Execute each scenario on https://automationexercise.com/.
2. Record actual results and update status only after execution.
3. Mark a scenario N/A if the feature is unavailable in the current demo, and record the reason.
4. Use only test accounts and safe demo data. Do not use real payment details.
5. Do not mark a scenario Pass without executing it.

## Status Definitions
- **Not Executed:** Not run yet.
- **Pass:** Actual result matches expected result.
- **Fail:** Actual result differs from expected result.
- **Blocked:** Testing cannot continue due to an issue.
- **N/A:** Feature or scenario does not apply.
