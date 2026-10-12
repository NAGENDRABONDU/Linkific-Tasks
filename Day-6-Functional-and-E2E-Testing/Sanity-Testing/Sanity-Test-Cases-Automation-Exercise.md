# Day 6 – Sanity Testing

## Project Details
- **Project Name:** Automation Exercise
- **Module Name:** Sanity Testing
- **Application URL:** https://automationexercise.com/

## Objective
Perform focused checks on the main affected functions after a small change or bug fix to confirm they work as expected.

## Sanity Test Cases

| Test Case ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| SAN-001 | Verify Signup / Login page opens | Signup / Login page opens and displays the relevant fields. | Not Executed |
| SAN-002 | Verify login with valid credentials | Registered test user logs in successfully. | Not Executed |
| SAN-003 | Verify login with invalid credentials | Invalid login is rejected with an appropriate message. | Not Executed |
| SAN-004 | Verify Products page | Products page loads and product listings are displayed. | Not Executed |
| SAN-005 | Verify product search | Search for an existing product and check the results. | Not Executed |
| SAN-006 | Verify product details | Selected product details are displayed correctly. | Not Executed |
| SAN-007 | Verify adding a product to cart | Selected product is added to the cart. | Not Executed |
| SAN-008 | Verify cart quantity and total | Cart quantity and displayed total update correctly when changed, where supported. | Not Executed |
| SAN-009 | Verify cart item removal | Removed product no longer appears in the cart. | Not Executed |
| SAN-010 | Verify logout | Logged-in user can log out successfully. | Not Executed |

## Execution Notes
1. Open https://automationexercise.com/ in a browser.
2. Run each relevant check after the change or fix.
3. Record the actual result and update status only after execution.
4. Use safe test data and test accounts only.
5. Do not mark a test Pass without executing it.

## Status Definitions
- **Not Executed:** Test has not been run yet.
- **Pass:** Actual result matches the expected result.
- **Fail:** Actual result differs from the expected result.
- **Blocked:** Testing cannot continue due to an issue.
- **N/A:** The test does not apply.
