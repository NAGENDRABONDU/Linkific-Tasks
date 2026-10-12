# Full Test Execution Report — Practice Data (Simulated)

**Report date:** 12-10-2026  
**Primary application:** Automation Exercise  
**Primary URL:** https://automationexercise.com/  
**Important:** This is a fictional practice report. These results were not produced by running the websites. All actual-result entries, statuses, and defect IDs below are simulated for learning documentation only.

## Overall Summary

| Metric | Count |
|---|---:|
| Total test cases | 60 |
| Passed | 55 |
| Failed | 5 |
| Blocked | 0 |
| Not Executed | 0 |

## Suite Summary

| Suite | Total | Passed | Failed |
|---|---:|---:|---:|
| Smoke Testing | 10 | 10 | 0 |
| Sanity Testing | 10 | 8 | 2 |
| E-commerce E2E Testing | 10 | 9 | 1 |
| Regression Testing | 10 | 9 | 1 |
| Banking E2E - ParaBank | 10 | 10 | 0 |
| Booking E2E - Demo | 10 | 9 | 1 |

## Smoke Testing

| Test Case ID | Scenario | Steps | Expected Result | Simulated Actual Result | Status | Defect / Remarks |
|---|---|---|---|---|---|---|
| SM-001 | Verify home page loads | Open the home page. | Home page loads and displays Automation Exercise content. | Home page opened; header and main content were visible. | Pass | — |
| SM-002 | Verify Products navigation | Click Products from the home page. | Products page opens and products are listed. | Products page opened and product cards were visible. | Pass | — |
| SM-003 | Verify Signup/Login page | Click Signup / Login. | Login and signup forms are displayed. | Login and signup sections displayed correctly. | Pass | — |
| SM-004 | Verify product search | Open Products, enter a product name, and click Search. | Matching products are displayed. | Search for 'Blue Top' returned a matching product. | Pass | — |
| SM-005 | Verify product details | Open Products and click View Product. | Selected product details page is displayed. | Product details displayed name, price, and description. | Pass | — |
| SM-006 | Verify cart page opens | Click Cart. | Cart page opens without an application error. | Cart page opened; empty-cart message was displayed. | Pass | — |
| SM-007 | Verify contact us page opens | Click Contact us. | Contact Us page and form are displayed. | Contact Us form displayed with name, email, subject, and message fields. | Pass | — |
| SM-008 | Verify test cases page opens | Click Test Cases. | Test Cases page opens and content is visible. | Test Cases page opened and test-case content was visible. | Pass | — |
| SM-009 | Verify subscription section | Locate subscription section and submit a valid test email if appropriate. | Subscription section is available and responds as expected. | Subscription field was visible; success message appeared after test submission. | Pass | — |
| SM-010 | Verify footer is displayed | Scroll to the bottom of the home page. | Footer content is displayed. | Footer section was visible at the bottom of the page. | Pass | — |

## Sanity Testing

| Test Case ID | Scenario | Steps | Expected Result | Simulated Actual Result | Status | Defect / Remarks |
|---|---|---|---|---|---|---|
| SAN-001 | Verify login with valid account | Open Signup/Login and enter approved valid test credentials. | User logs in successfully. | Test user logged in and account name was displayed. | Pass | — |
| SAN-002 | Verify login with invalid password | Enter test email with an incorrect password. | An appropriate error message is displayed. | Error message was not displayed after invalid password submission. | Fail | BUG-SAN-002: Invalid login feedback missing (simulated defect). |
| SAN-003 | Verify signup form validation | Submit signup with required fields missing. | Required-field validation is shown. | Required-field validation appeared and form submission was prevented. | Pass | — |
| SAN-004 | Verify product search results | Search for a known product name. | Relevant matching products are shown. | Relevant product cards were displayed for the search term. | Pass | — |
| SAN-005 | Verify product details content | Open a product details page. | Product name, price, availability and details are shown. | Product name, price, and availability were visible. | Pass | — |
| SAN-006 | Verify add to cart | Add an available product to cart. | Product is added to cart. | Selected product was shown in cart. | Pass | — |
| SAN-007 | Verify cart quantity update | Change product quantity in cart. | Cart quantity and totals update correctly. | Quantity changed to 2, but displayed total did not update. | Fail | BUG-SAN-007: Cart total not recalculated (simulated defect). |
| SAN-008 | Verify remove item from cart | Remove a product from cart. | Removed product no longer appears in cart. | Removed product disappeared from cart. | Pass | — |
| SAN-009 | Verify contact form validation | Submit Contact Us with required fields missing. | Validation prevents incomplete submission or shows an appropriate message. | Validation message appeared for missing required fields. | Pass | — |
| SAN-010 | Verify navigation links | Open key navigation links one by one. | Each selected page opens without a visible error. | All checked navigation links opened the expected pages. | Pass | — |

## E-commerce E2E Testing

| Test Case ID | Scenario | Steps | Expected Result | Simulated Actual Result | Status | Defect / Remarks |
|---|---|---|---|---|---|---|
| E2E-001 | Browse product and view details | Open Products, select a product, and view details. | Product details match the selected item. | Selected product details matched the product listing. | Pass | — |
| E2E-002 | Search and add product to cart | Search for a product and add it to cart. | Correct product is added to cart. | Searched product was added to cart successfully. | Pass | — |
| E2E-003 | Update cart quantity | Add a product and change its quantity. | Cart reflects the selected quantity and updated total. | Quantity updated, but total remained unchanged. | Fail | BUG-E2E-003: Cart total stale after quantity update (simulated defect). |
| E2E-004 | Remove product from cart | Add product and remove it from cart. | Cart no longer contains the removed product. | Removed product no longer appeared in cart. | Pass | — |
| E2E-005 | Signup new test user | Complete signup using unique approved test data. | Test account is created or duplicate-account validation is shown. | New synthetic test account was created and confirmation displayed. | Pass | — |
| E2E-006 | Login and logout | Log in with an approved test account and log out. | User session starts and ends successfully. | Login succeeded; logout returned user to logged-out state. | Pass | — |
| E2E-007 | Checkout as logged-in user | Add item, log in, proceed through checkout using demo-safe data. | Checkout flow advances as designed. | Checkout page opened and delivery details were displayed. | Pass | — |
| E2E-008 | Place demo order | Complete supported demo order flow with test data only. | Order confirmation is displayed if demo supports it. | Order confirmation page displayed for the simulated test order. | Pass | — |
| E2E-009 | Submit contact form | Fill Contact Us with test data and submit only if safe. | Confirmation or expected validation appears. | Submission confirmation was displayed. | Pass | — |
| E2E-010 | Subscribe using test email | Enter approved test email in subscription field. | Expected subscription response appears. | Subscription confirmation message appeared. | Pass | — |

## Regression Testing

| Test Case ID | Scenario | Steps | Expected Result | Simulated Actual Result | Status | Defect / Remarks |
|---|---|---|---|---|---|---|
| REG-001 | Home page rendering | Open home page after a change. | Home page loads and core sections are visible. | Home page and core sections displayed. | Pass | — |
| REG-002 | Primary navigation | Open Products, Cart, Signup/Login, Contact Us. | Each page opens correctly. | All selected pages opened correctly. | Pass | — |
| REG-003 | Product listing | Open Products and inspect listing. | Product cards and key information display. | Product cards, names, and prices displayed. | Pass | — |
| REG-004 | Product search | Search using valid and unmatched terms. | Relevant results and no-results behaviour are correct. | Valid search returned matches; unmatched search showed no products. | Pass | — |
| REG-005 | Product details | Open details for an available product. | Name, price and product information display. | Product details displayed correctly. | Pass | — |
| REG-006 | Add item to cart | Add a product from listing/details. | Cart reflects the added product. | Product appeared in cart. | Pass | — |
| REG-007 | Cart update and removal | Update quantity and remove product. | Cart contents and totals remain consistent. | Cart item removal worked; quantity update left total unchanged. | Fail | BUG-REG-007: Cart total not recalculated (simulated defect). |
| REG-008 | Login/logout | Log in and log out with approved test credentials. | Authentication and session termination work. | Login and logout worked as expected. | Pass | — |
| REG-009 | Form validation | Check signup and contact form validation. | Required fields and validation messages behave correctly. | Required-field validation appeared on both forms. | Pass | — |
| REG-010 | Footer and subscription | Inspect footer and subscription area. | Footer and subscription section remain available. | Footer and subscription section displayed. | Pass | — |

## Banking E2E - ParaBank

| Test Case ID | Scenario | Steps | Expected Result | Simulated Actual Result | Status | Defect / Remarks |
|---|---|---|---|---|---|---|
| BANK-001 | Open banking demo | Open ParaBank demo home page. | ParaBank demo home page loads. | Demo home page opened successfully. | Pass | — |
| BANK-002 | Register demo customer | Register using synthetic test data. | Demo customer registration succeeds or validates duplicate data. | Synthetic test customer registration succeeded. | Pass | — |
| BANK-003 | Login to demo | Log in using the created demo account. | Account overview is displayed. | Account overview displayed after login. | Pass | — |
| BANK-004 | View account overview | Open account overview. | Account list and balances display. | Two demo accounts and balances were visible. | Pass | — |
| BANK-005 | Open new account | Use the demo's Open New Account function. | New account is created and confirmation appears. | New demo account opened and confirmation appeared. | Pass | — |
| BANK-006 | View account activity | Select an account and open activity. | Transactions/activity are displayed. | Account activity page displayed transaction rows. | Pass | — |
| BANK-007 | Transfer funds | Transfer a small demo amount between demo accounts. | Transfer confirmation and updated balances are displayed. | Transfer confirmation displayed; balances appeared updated. | Pass | — |
| BANK-008 | Pay demo bill | Use synthetic payee details in the demo bill-pay flow. | Expected confirmation is displayed. | Bill payment confirmation displayed. | Pass | — |
| BANK-009 | Update profile | Change a non-sensitive demo profile field. | Profile update is saved. | Profile update confirmation displayed. | Pass | — |
| BANK-010 | Logout | Click Log Out. | User is returned to logged-out state. | Logout returned the user to the login page. | Pass | — |

## Booking E2E - Demo

| Test Case ID | Scenario | Steps | Expected Result | Simulated Actual Result | Status | Defect / Remarks |
|---|---|---|---|---|---|---|
| BOOK-001 | Open booking demo | Open the assigned booking demo URL. | Booking home/search page loads. | Demo booking search page loaded. | Pass | — |
| BOOK-002 | Search destination | Enter a test destination and dates. | Available demo results are displayed. | Search returned three sample properties. | Pass | — |
| BOOK-003 | Apply filters | Apply one available filter. | Results reflect selected filter. | Price filter reduced results from 3 to 2 properties. | Pass | — |
| BOOK-004 | View property details | Open a result. | Property details and price information display. | Property detail page displayed dates, room, and price. | Pass | — |
| BOOK-005 | Select room/option | Select a demo room or booking option. | Selection is retained in booking flow. | Selected room was retained in booking summary. | Pass | — |
| BOOK-006 | Enter guest details | Enter synthetic guest details. | Form accepts valid data and validates required fields. | Synthetic guest data accepted by the form. | Pass | — |
| BOOK-007 | Validate missing fields | Submit booking form with required fields omitted. | Required-field validation is displayed. | Form submitted without showing the expected missing-field message. | Fail | BUG-BOOK-007: Missing-field validation not displayed (simulated defect). |
| BOOK-008 | Review booking summary | Open booking review/summary page. | Destination, dates, guests and price are consistent. | Booking summary values matched selected search details. | Pass | — |
| BOOK-009 | Cancel/reset test flow | Cancel or reset an unconfirmed demo flow if supported. | Unconfirmed flow is cleared or cancellation confirmation appears. | Unconfirmed test flow was cleared. | Pass | — |
| BOOK-010 | Check confirmation page | Complete only a supported demo confirmation flow. | Demo confirmation details display. | Confirmation page displayed a reference number. | Pass | — |

## Practice Defect Log

| Defect ID | Summary | Severity (practice assumption) |
|---|---|---|
| BUG-SAN-002 | Invalid login feedback missing | Medium |
| BUG-SAN-007 | Cart total not recalculated after quantity update | High |
| BUG-E2E-003 | Cart total stale after quantity update | High |
| BUG-REG-007 | Cart total not recalculated | High |
| BUG-BOOK-007 | Missing-field validation not displayed | Medium |

## Notes

- These outcomes are invented solely for practice; do not present them as evidence of real execution.
- The Booking E2E suite uses an illustrative demo flow because no specific booking demo URL was supplied.
- For real execution, replace simulated actual results with observed behaviour and attach screenshots or evidence references.