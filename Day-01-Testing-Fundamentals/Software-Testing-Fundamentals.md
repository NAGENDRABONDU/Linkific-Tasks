# Software Testing Fundamentals

## 1. What is Software Testing?

### Definition

Software testing is the process of evaluating software to identify
defects and verify that it meets specified requirements.

### Purpose of Software Testing

Software testing is performed to:

- Verify that the software meets its requirements
- Identify defects
- Check that the software behaves as expected
- Reduce business and technical risks
- Improve software quality
- Ensure changes do not break existing functionality

### Example

Consider an application with a login page.

Requirement:

> A registered user should be able to log in successfully using valid
> username and password.

A tester should not check only the valid login scenario.

The tester should also check:

- Valid username and valid password
- Invalid username
- Invalid password
- Empty username
- Empty password
- Boundary conditions
- Validation messages
- Login button behavior

### Basic Testing Flow

┌─────────────────┐
│   Requirement   │
└────────┬────────┘
         ↓
┌─────────────────┐
│ Test Conditions │
└────────┬────────┘
         ↓
┌─────────────────┐
│ Test Execution  │
└────────┬────────┘
         ↓
┌──────────────────────────┐
│ Compare Expected & Actual│
└────────────┬─────────────┘
             ↓
       ┌───────────┐
       │ Pass / Fail│
       └─────┬─────┘
             ↓
      ┌──────────────┐
      │ Defect Found?│
      └──────┬───────┘
             ↓
        Defect Report

### Important Point

Testing can show the presence of defects, but it cannot prove that
software is completely free of defects.


---

## 2. QA vs Testing

### Quality Assurance (QA)

Quality Assurance is a process-oriented approach that focuses on
preventing defects by improving the processes used to develop software.

### Software Testing

Software testing is a product-oriented activity that focuses on
finding defects by evaluating the software.

### Difference

| QA | Testing |
|---|---|
| Process-oriented | Product-oriented |
| Focuses on preventing defects | Focuses on finding defects |
| Improves processes | Evaluates the software |
| Proactive approach | Mainly reactive approach |

### Example

**QA:** Establishing standards and processes to prevent defects.

**Testing:** Testing a login page to identify defects.

### Easy Way to Remember

**QA → Prevent defects**

**Testing → Find defects**


---

## 3. Verification vs Validation

### Verification

Verification checks:

> **Are we building the product right?**

It involves reviewing work products such as:

- Requirements
- Design
- Code
- Test plans
- Test cases

Examples:

- Requirement review
- Design review
- Code review
- Test plan review
- Test case review

### Validation

Validation checks:

> **Are we building the right product?**

It involves evaluating the actual software through testing.

Examples:

- Functional testing
- Integration testing
- System testing
- Compatibility testing
- Smoke testing
- Ad-hoc testing

### Easy Way to Remember

**Verification → Building the product right**

**Validation → Building the right product**


---

## 4. Error, Defect and Failure

### Error

An error is a human mistake made during software development.

### Defect

A defect is a flaw or mistake introduced into the software or code.

### Failure

A failure occurs when the software behaves incorrectly during
execution and does not produce the expected result.

### Relationship

┌──────────────┐
│ Human Error  │
│   (Mistake)  │
└──────┬───────┘
       ↓
┌──────────────┐
│   Defect     │
│ In Software  │
└──────┬───────┘
       ↓
┌──────────────┐
│   Failure    │
│Wrong Behavior│
└──────────────┘

### Example

Requirement:

> The discount should be 10%.

A developer accidentally writes 20% in the code.

**Error:** Developer makes the mistake.

**Defect:** Incorrect 20% value exists in the code.

**Failure:** The application gives the customer a 20% discount.

### Key Point

A defect may exist in software without producing a failure until the
specific condition that triggers it is executed.


---

## 5. Test Scenario vs Test Case

### Test Scenario

A test scenario is a high-level description of **what needs to be tested**.
Diagram:

             Test Scenario
                  │
            Verify Login
                  │
       ┌──────────┼──────────┐
       ↓          ↓          ↓
   Valid Login  Invalid    Empty Fields
                Login
       │          │          │
       ↓          ↓          ↓
   Test Case   Test Case   Test Case

Example:

> Verify login functionality.

### Test Case

A test case is a detailed documented set of steps used to verify
a specific functionality.

Example:

**Test Case: Valid Login**

1. Open the login page.
2. Enter a valid username.
3. Enter a valid password.
4. Click the Login button.
5. Verify that the home page is displayed.

### Difference

| Test Scenario | Test Case |
|---|---|
| High-level | Detailed |
| Describes what to test | Describes how to test |
| Less detailed | Contains steps and expected results |
| Can lead to multiple test cases | Tests a specific condition |

### Example

**Scenario:** Verify login functionality.

Possible test cases:

- Valid username + valid password
- Invalid username + valid password
- Valid username + invalid password
- Empty username
- Empty password


---

## 6. Expected Result vs Actual Result

### Expected Result

The expected result describes what **should happen** according to
the specified requirement.

### Actual Result

The actual result describes what **actually happens** when the test
is executed.

### Example

Requirement:

> A user with valid credentials should successfully log in.

**Expected Result:**

The home page should be displayed.

**Actual Result:**

An error message is displayed instead of the home page.

Since the expected and actual results are different, the test fails
and the issue should be investigated as a potential defect.

### Key Rule

**Expected Result = Actual Result → Test Passes**

**Expected Result ≠ Actual Result → Test Fails → Investigate Defect**
