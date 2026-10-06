# 7 Principles of Software Testing

The 7 principles of software testing are general guidelines that help testers understand and perform testing effectively.

---

## 1. Testing Shows the Presence of Defects

Testing can find defects in software, but it cannot prove that the software has no defects.

**Example:**

A tester finds 5 defects in an application. This does not mean there are no other hidden defects.

**Remember:**

Testing can show the presence of defects, but cannot prove their absence.

---

## 2. Exhaustive Testing is Impossible

It is not possible to test every possible input, condition, and scenario.

Testers select important and high-risk test cases.

**Example:**

For an age field that accepts 18 to 60:

```text
17 → Invalid
18 → Valid
19 → Valid
59 → Valid
60 → Valid
61 → Invalid
```

 ## 3. Early Testing
Testing should start as early as possible in the software development process.
Finding defects early makes them easier and less expensive to fix.
**Example:**
If a requirement is unclear, the tester can identify it during requirement analysis before development starts.

## 4. Defect Clustering
Defect Clustering means that most defects are often found in a small number of modules or areas.
**Example:**
In an e-commerce application, most defects may be found in:
Cart
Payment
Order

These areas may need more testing.

## 5. Pesticide Paradox
Repeating the same test cases again and again may eventually stop finding new defects.
Test cases should be reviewed and updated regularly.
**Example:**
For a login page, instead of testing only valid and invalid credentials, we can also test:
Empty fields
Boundary values
Account lockout
Password reset
Session timeout

## 6. Testing is Context Dependent
The testing approach depends on the type, purpose, and risks of the software.
**Example:**
Banking application:
Security
Accuracy
Reliability
Performance

Gaming application:
Performance
Usability
Compatibility
User Experience

## 7. Absence-of-Errors Fallacy
Having few or no defects does not mean that the software is successful.
The software must also satisfy customer requirements and business needs.
**Example:**
An application has very few defects but does not provide an important feature required by customers.
The application may be technically stable but still not meet business needs.

