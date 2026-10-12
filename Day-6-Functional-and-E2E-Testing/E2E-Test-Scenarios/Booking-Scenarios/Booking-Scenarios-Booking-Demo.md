# Day 6 – End-to-End (E2E) Testing: Booking Scenarios

## Project Details
- **Project Name:** Booking Demo
- **Module Name:** Booking – End-to-End Scenarios
- **Created Date:** 12-10-2026
- **Application URL:** Use the booking demo assigned for this task.

## Objective
Validate a complete booking workflow, including searching, entering dates, selecting an available option, entering guest details, reviewing the booking, and checking the final result.

## E2E Booking Scenarios

| Test Case ID | Scenario | Expected Result | Status |
|---|---|---|---|
| E2E-BK-001 | Open the booking demo | Home or search page loads successfully. | Not Executed |
| E2E-BK-002 | Search using a destination and valid dates | Matching available options are displayed. | Not Executed |
| E2E-BK-003 | Enter an invalid date range | Invalid dates are rejected or validation is displayed. | Not Executed |
| E2E-BK-004 | Select an available property or room | Selected option details are displayed. | Not Executed |
| E2E-BK-005 | Enter valid guest details | Guest details are accepted. | Not Executed |
| E2E-BK-006 | Continue with required guest details missing | Required-field validation is displayed. | Not Executed |
| E2E-BK-007 | Review booking details | Destination, dates, guest count, and selected option are correct. | Not Executed |
| E2E-BK-008 | Submit a safe demo booking where supported | Booking is processed and a result is displayed. | Not Executed |
| E2E-BK-009 | Verify booking confirmation where supported | Confirmation details are displayed and match the booking. | Not Executed |
| E2E-BK-010 | Search for unavailable dates where supported | No-availability message or empty results are displayed. | Not Executed |

## Execution Notes
1. Use the booking demo approved for this task; confirm the URL before execution.
2. Use only test data. Never enter real payment-card details or sensitive personal information.
3. Mark unsupported scenarios **N/A** and record the reason.
4. Record actual results and update status only after executing each test.
5. Do not mark a scenario Pass without executing it.

## Status Definitions
- **Not Executed:** Not run yet.
- **Pass:** Actual result matches expected result.
- **Fail:** Actual result differs from expected result.
- **Blocked:** Testing cannot continue due to an issue.
- **N/A:** Feature or scenario does not apply.
