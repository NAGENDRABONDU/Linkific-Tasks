# Login Test Cases – White Box Testing

## 1. Objective

To test the login validation function and achieve 100% branch coverage by executing every True and False branch.

## 2. Test Data

Valid username: `admin`

Valid password: `1234`

## 3. Test Cases

### TC01 – Valid Username and Password

**Input:**
- Username: admin
- Password: 1234

**Expected Result:** Login successful

**Branches Covered:**
- Username condition: True
- Password condition: True

### TC02 – Valid Username and Invalid Password

**Input:**
- Username: admin
- Password: wrong

**Expected Result:** Invalid password

**Branches Covered:**
- Username condition: True
- Password condition: False

### TC03 – Invalid Username

**Input:**
- Username: user
- Password: 1234

**Expected Result:** Invalid username

**Branches Covered:**
- Username condition: False
- Password condition: Not executed

## 4. Branch Coverage Calculation

Total branch outcomes: 4

- Username condition: True
- Username condition: False
- Password condition: True
- Password condition: False

All four outcomes are covered by TC01, TC02, and TC03.

Branch Coverage = (Executed Branches / Total Branches) × 100

Branch Coverage = (4 / 4) × 100 = **100%**

## 5. Additional Test Cases

| Test Case | Username | Password | Expected Result |
|---|---|---|---|
| TC04 | Empty | Empty | Invalid username |
| TC05 | admin | Empty | Invalid password |
| TC06 | Admin | 1234 | Invalid username |

Note: TC04–TC06 are additional functional test cases. The expected results follow the sample code's exact, case-sensitive comparisons.

## 6. Conclusion

These test cases cover every branch in the sample login function. They demonstrate how white box testing helps identify untested decision outcomes and measure branch coverage.