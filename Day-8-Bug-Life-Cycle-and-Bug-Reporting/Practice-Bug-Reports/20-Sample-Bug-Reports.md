# 20 Illustrative Sample Bug Reports

**Training examples only:** these are not verified defects. Fill actual environment details and attach evidence only after personally reproducing an issue.

## BR-001 — Login: Valid login displays a generic error
- **Preconditions:** Active test account exists
- **Steps to Reproduce:**
  1. Open login page
  2. Enter valid credentials
  3. Select Sign in
- **Expected Result:** Dashboard opens
- **Actual Result (illustrative):** Generic error appears
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** Core account access is blocked.
- **Validation Status:** Illustrative — Not Reproduced

## BR-002 — Registration: Invalid email format is accepted
- **Preconditions:** Registration page available
- **Steps to Reproduce:**
  1. Open registration
  2. Enter user@
  3. Complete required fields
  4. Submit
- **Expected Result:** Email validation appears
- **Actual Result (illustrative):** Invalid address is accepted or generic error appears
- **Suggested Severity:** Major
- **Suggested Priority:** P2 / Medium
- **Rationale:** Invalid account data may be stored.
- **Validation Status:** Illustrative — Not Reproduced

## BR-003 — Password reset: No confirmation appears after reset request
- **Preconditions:** Registered test email available
- **Steps to Reproduce:**
  1. Open Forgot Password
  2. Enter test email
  3. Submit
- **Expected Result:** Neutral confirmation appears
- **Actual Result (illustrative):** No visible feedback
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** User cannot tell if request was accepted.
- **Validation Status:** Illustrative — Not Reproduced

## BR-004 — Search: Exact product search omits matching item
- **Preconditions:** Known item exists in test data
- **Steps to Reproduce:**
  1. Search exact product name
  2. Submit
- **Expected Result:** Matching product appears
- **Actual Result (illustrative):** Item is absent; unrelated results appear
- **Suggested Severity:** Major
- **Suggested Priority:** P2 / Medium
- **Rationale:** Core discovery feature is impaired.
- **Validation Status:** Illustrative — Not Reproduced

## BR-005 — Cart: Cart accepts quantity zero
- **Preconditions:** Product in cart
- **Steps to Reproduce:**
  1. Open cart
  2. Set quantity to 0
  3. Update cart
- **Expected Result:** Zero is rejected or item is removed clearly
- **Actual Result (illustrative):** Zero-quantity line remains
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** Cart state may become inconsistent.
- **Validation Status:** Illustrative — Not Reproduced

## BR-006 — Checkout: Total does not update after quantity change
- **Preconditions:** Cart contains an item
- **Steps to Reproduce:**
  1. Open cart
  2. Increase quantity
  3. Check total
- **Expected Result:** Total recalculates
- **Actual Result (illustrative):** Old total remains
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** Potentially incorrect purchase total.
- **Validation Status:** Illustrative — Not Reproduced

## BR-007 — Payment: Retry remains disabled after sandbox decline
- **Preconditions:** Approved payment sandbox
- **Steps to Reproduce:**
  1. Submit approved decline test case
  2. Wait for response
  3. Inspect retry action
- **Expected Result:** Failure is explained and safe retry is possible
- **Actual Result (illustrative):** Button remains disabled
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** Payment recovery is blocked.
- **Validation Status:** Illustrative — Not Reproduced

## BR-008 — Profile: Success message appears after save failure
- **Preconditions:** Controlled failure setup in test environment
- **Steps to Reproduce:**
  1. Edit profile
  2. Trigger controlled save failure
  3. Observe message
- **Expected Result:** Failure is clearly reported
- **Actual Result (illustrative):** Success message appears
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** User may believe unsaved data was saved.
- **Validation Status:** Illustrative — Not Reproduced

## BR-009 — Logout: Back button displays cached protected page
- **Preconditions:** Signed-in test account
- **Steps to Reproduce:**
  1. Sign in
  2. Log out
  3. Press browser Back
- **Expected Result:** Protected content remains inaccessible
- **Actual Result (illustrative):** Cached content appears
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** Potential exposure of protected content.
- **Validation Status:** Illustrative — Not Reproduced

## BR-010 — Session: Expired session does not guide user to sign in
- **Preconditions:** Test session expiry configured
- **Steps to Reproduce:**
  1. Sign in
  2. Expire session
  3. Open protected page
- **Expected Result:** User is asked to authenticate
- **Actual Result (illustrative):** Broken page or silent failure appears
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** Authorization flow is confusing.
- **Validation Status:** Illustrative — Not Reproduced

## BR-011 — Filters: Clearing filters leaves filtered results
- **Preconditions:** Multiple filters available
- **Steps to Reproduce:**
  1. Apply category filter
  2. Apply price filter
  3. Select Clear filters
- **Expected Result:** Default result set returns
- **Actual Result (illustrative):** Results remain filtered
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** Search reset is ineffective.
- **Validation Status:** Illustrative — Not Reproduced

## BR-012 — Pagination: Next page repeats previous results
- **Preconditions:** Dataset spans multiple pages
- **Steps to Reproduce:**
  1. Record first page item IDs
  2. Select Next
  3. Compare IDs
- **Expected Result:** Next page shows unique next items
- **Actual Result (illustrative):** One or more items repeat
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** Browsing experience is degraded.
- **Validation Status:** Illustrative — Not Reproduced

## BR-013 — Upload: Unsupported file receives no validation message
- **Preconditions:** Upload form available
- **Steps to Reproduce:**
  1. Select unsupported file type
  2. Submit upload
- **Expected Result:** Upload is blocked with supported formats listed
- **Actual Result (illustrative):** No clear validation is shown
- **Suggested Severity:** Major
- **Suggested Priority:** P2 / Medium
- **Rationale:** Invalid files may cause processing errors.
- **Validation Status:** Illustrative — Not Reproduced

## BR-014 — Export: CSV omits a required report column
- **Preconditions:** Report has documented columns
- **Steps to Reproduce:**
  1. Open report
  2. Export CSV
  3. Compare headers
- **Expected Result:** All required columns are exported
- **Actual Result (illustrative):** A required column is missing
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** Exported data is incomplete.
- **Validation Status:** Illustrative — Not Reproduced

## BR-015 — Responsive UI: Primary button is clipped on narrow viewport
- **Preconditions:** Responsive page available
- **Steps to Reproduce:**
  1. Set viewport to 320px
  2. Open page
  3. Inspect primary action
- **Expected Result:** Button is fully visible and usable
- **Actual Result (illustrative):** Button edge is clipped
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** Small-screen use is impaired.
- **Validation Status:** Illustrative — Not Reproduced

## BR-016 — Accessibility: Field error is not associated programmatically
- **Preconditions:** Validated form available
- **Steps to Reproduce:**
  1. Submit with a required field empty
  2. Inspect accessible relationships
- **Expected Result:** Assistive technology can identify the field and error
- **Actual Result (illustrative):** Error text is not associated with the field
- **Suggested Severity:** Major
- **Suggested Priority:** P2 / Medium
- **Rationale:** Screen-reader users may miss error context.
- **Validation Status:** Illustrative — Not Reproduced

## BR-017 — Sorting: Price sorting uses text order
- **Preconditions:** Products priced 9, 20, and 100 exist
- **Steps to Reproduce:**
  1. Sort price ascending
  2. Compare displayed values
- **Expected Result:** Prices are sorted numerically
- **Actual Result (illustrative):** Values appear in lexicographic order
- **Suggested Severity:** Minor
- **Suggested Priority:** P2 / Medium
- **Rationale:** Users receive a misleading order.
- **Validation Status:** Illustrative — Not Reproduced

## BR-018 — Notifications: One save displays duplicate success toasts
- **Preconditions:** Editable record available
- **Steps to Reproduce:**
  1. Change one field
  2. Select Save once
  3. Observe notifications
- **Expected Result:** One confirmation appears
- **Actual Result (illustrative):** Two identical toasts appear
- **Suggested Severity:** Trivial
- **Suggested Priority:** P3 / Low
- **Rationale:** Minor interface noise.
- **Validation Status:** Illustrative — Not Reproduced

## BR-019 — Date form: End date before start date is accepted
- **Preconditions:** Start/end date form available
- **Steps to Reproduce:**
  1. Enter later start date
  2. Enter earlier end date
  3. Submit
- **Expected Result:** Invalid range is rejected
- **Actual Result (illustrative):** Form accepts range without warning
- **Suggested Severity:** Major
- **Suggested Priority:** P2 / Medium
- **Rationale:** Invalid schedule or report data may result.
- **Validation Status:** Illustrative — Not Reproduced

## BR-020 — Error handling: Error page exposes stack trace
- **Preconditions:** Controlled non-production error scenario
- **Steps to Reproduce:**
  1. Trigger approved error scenario
  2. Inspect response
- **Expected Result:** Safe user-facing error appears
- **Actual Result (illustrative):** Internal details appear
- **Suggested Severity:** Major
- **Suggested Priority:** P1 / High
- **Rationale:** Potential information disclosure.
- **Validation Status:** Illustrative — Not Reproduced
