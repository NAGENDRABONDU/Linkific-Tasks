# Branch Coverage Calculations

## 1. Definition

Branch Coverage is a white box testing technique that checks whether every possible outcome of each decision in the code has been executed.

For an `if-else` condition, the two branches are:
- True branch
- False branch

## 2. Formula

Branch Coverage (%) = (Executed Branches / Total Branches) × 100

## 3. Login Validation Code

```python
def login(username, password):
    if username == "admin":
        if password == "1234":
            return "Login successful"
        else:
            return "Invalid password"
    else:
        return "Invalid username"
```

## 4. Code Flow Diagram

```text
              Start
                |
       Check username == admin
           /           \
        True            False
         |                |
 Check password       Invalid username
     == 1234                |
     /    \                End
  True    False
   |        |
Login     Invalid
success   password
   |        |
  End      End
```

## 5. Test Cases

### Test Case 1: Valid Username and Password

**Input:**
- Username: admin
- Password: 1234

**Expected Result:** Login successful

**Branches Covered:**
- Username condition: True
- Password condition: True

### Test Case 2: Valid Username and Invalid Password

**Input:**
- Username: admin
- Password: wrong

**Expected Result:** Invalid password

**Branches Covered:**
- Username condition: True
- Password condition: False

### Test Case 3: Invalid Username

**Input:**
- Username: user
- Password: 1234

**Expected Result:** Invalid username

**Branches Covered:**
- Username condition: False
- Password condition: Not executed

## 6. Branch Coverage Calculation

There are **4 total branch outcomes** in this code:

1. Username condition: True
2. Username condition: False
3. Password condition: True
4. Password condition: False

| Test Case | Branches Covered |
|---|---|
| TC01 | Username True, Password True |
| TC02 | Username True, Password False |
| TC03 | Username False |

All four branch outcomes are covered by these three test cases.

**Branch Coverage = (4 / 4) × 100 = 100%**

## 7. Identify Test Gaps

If we execute only TC01:
- Username True branch is covered.
- Password True branch is covered.
- Username False branch is not covered.
- Password False branch is not covered.

Branch Coverage = (2 / 4) × 100 = 50%

Therefore, additional test cases are required to cover the missing branches.

## 8. Conclusion

Branch coverage helps testers verify that every decision outcome in the code has been tested. For this login function, three test cases achieve 100% branch coverage.

However, 100% branch coverage does not guarantee that the application is completely defect-free. Other test techniques are also necessary.