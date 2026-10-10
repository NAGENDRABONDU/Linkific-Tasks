# Day 5: White Box Testing & Code Coverage

## 1. Introduction to White Box Testing

White Box Testing is a software testing technique in which the tester examines the internal code, logic, conditions, loops, and execution paths of an application.

**Example:** Testing whether both True and False branches of an `if-else` condition execute correctly.

### White Box Testing Flow Diagram

```text
┌──────────────────────┐
│     Test Input       │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│   Internal Code      │
│ Conditions and Loops │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Execute Test Cases   │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Analyze Code Coverage│
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Identify Test Gaps   │
└──────────────────────┘
```

## 2. Basic Code Reading

### If-Else Statement

An `if-else` statement executes one of two blocks depending on a condition.

```python
age = 20

if age >= 18:
    print("Eligible")
else:
    print("Not Eligible")
```

### Code Flow Diagram

```text
       ┌────────────┐
       │ Start      │
       └─────┬──────┘
             ↓
       ┌────────────┐
       │ Age >= 18? │
       └─────┬──────┘
          Yes / \ No
             /   \
            ↓     ↓
    ┌──────────┐ ┌──────────────┐
    │ Eligible │ │ Not Eligible│
    └─────┬────┘ └──────┬───────┘
          └──────┬──────┘
                 ↓
           ┌─────────┐
           │ End     │
           └─────────┘
```

### Loops

Loops execute a block of code repeatedly.

```python
for i in range(3):
    print(i)
```

Output:

```text
0
1
2
```

### Functions

A function is a reusable block of code that performs a specific task.

```python
def add(a, b):
    return a + b

print(add(5, 3))
```

Output: `8`

## 3. Statement Coverage

Statement Coverage measures the percentage of executable statements executed by test cases.

**Formula:**

Statement Coverage = (Executed Statements / Total Executable Statements) × 100

### Example

```python
def check_age(age):
    if age >= 18:
        print("Eligible")
    print("Check completed")
```

Test input: `age = 20`

Executed statements:

- `if age >= 18`
- `print("Eligible")`
- `print("Check completed")`

Assume there are 3 executable statements and all 3 execute.

Statement Coverage = (3 / 3) × 100 = **100%**

### Statement Coverage Diagram

```text
┌──────────────────────┐
│ if age >= 18         │ ✓
├──────────────────────┤
│ print("Eligible")    │ ✓
├──────────────────────┤
│ print("Check completed")│ ✓
└──────────────────────┘

Executed: 3 statements
Total:    3 statements
Coverage: 100%
```

**Important:** Statement coverage does not guarantee that every decision outcome has been tested.

## 4. Branch Coverage (Decision Coverage)

Branch Coverage measures whether every possible outcome of a decision has been executed.

For an `if-else` statement, both the True and False branches must execute.

**Formula:**

Branch Coverage = (Executed Branches / Total Branches) × 100

### Example

```python
def check_age(age):
    if age >= 18:
        print("Eligible")
    else:
        print("Not Eligible")
```

Test cases:

- Test 1: `age = 20` → True branch
- Test 2: `age = 16` → False branch

Calculation:

Branch Coverage = (2 / 2) × 100 = **100%**

### Branch Coverage Diagram

```text
              ┌──────────────┐
              │ Age >= 18 ?  │
              └──────┬───────┘
                 Yes / \ No
                    /   \
                   ↓     ↓
            ┌──────────┐ ┌──────────────┐
            │ Eligible │ │ Not Eligible │
            └──────────┘ └──────────────┘
                 ✓              ✓

True branch:  Tested
False branch: Tested
Branch Coverage: 100%
```

### Test Cases for 100% Branch Coverage

| Test Case | Input | Expected Result | Branch |
|---|---:|---|---|
| TC01 | 20 | Eligible | True |
| TC02 | 16 | Not Eligible | False |

## 5. Path Coverage

Path Coverage measures which possible execution paths through the code have been tested.

### Example

```python
def login(username, password):
    if username == "admin":
        if password == "1234":
            return "Success"
        else:
            return "Invalid Password"
    else:
        return "Invalid Username"
```

### Login Code Flow Diagram

```text
             ┌──────────────┐
             │ Start Login  │
             └──────┬───────┘
                    ↓
             ┌──────────────┐
             │ Username     │
             │ correct?     │
             └──────┬───────┘
                 Yes / \ No
                    /   \
                   ↓     ↓
          ┌────────────┐ ┌─────────────────┐
          │ Password   │ │ Invalid Username│
          │ correct?   │ └─────────────────┘
          └──────┬─────┘
              Yes / \ No
                 /   \
                ↓     ↓
        ┌──────────┐ ┌──────────────────┐
        │ Success  │ │ Invalid Password │
        └──────────┘ └──────────────────┘
```

### Possible Paths

- Path 1: Correct username → Correct password → Success
- Path 2: Correct username → Incorrect password → Invalid Password
- Path 3: Incorrect username → Invalid Username

These three paths can be tested with three test cases.

**Limitation:** Loops and multiple conditions can create a very large number of possible paths. Therefore, testing every path may be impractical.

## 6. Statement vs Branch vs Path Coverage

| Coverage Type | What It Checks |
|---|---|
| Statement Coverage | Whether executable statements run |
| Branch Coverage | Whether decision outcomes run |
| Path Coverage | Which execution paths run |

Branch coverage is generally stronger than statement coverage for checking decision outcomes. Full path coverage can be significantly more difficult.

## 7. Identifying Test Gaps

A test gap exists when some executable statements, branches, or important paths have not been exercised by the tests.

### Example

For the age validation code:

```python
if age >= 18:
    print("Eligible")
else:
    print("Not Eligible")
```

If we test only `age = 20`, the True branch executes but the False branch remains untested.

**Missing test:** `age = 16`

Adding this test exercises the False branch and achieves 100% branch coverage for this decision.

## 8. Code Coverage Tools

### JaCoCo
Used for measuring code coverage in Java applications.

### Istanbul / NYC
Used for measuring code coverage in JavaScript applications.

### Coverage.py
Used for measuring code coverage in Python applications.

### How Testers Use Coverage Reports

1. Run the automated test suite.
2. Generate the code coverage report.
3. Review statement, branch, and other available coverage metrics.
4. Identify untested code and branches.
5. Add test cases for missing logic.
6. Run the tests again and review the updated report.

**Note:** High code coverage does not guarantee defect-free software. Assertions and meaningful expected-result checks are also necessary.

## 9. Tester's Role in White Box Testing

- Understand basic code structure and logic.
- Identify conditions, branches, loops, and functions.
- Review available code coverage reports.
- Identify untested statements and decision outcomes.
- Add tests to improve coverage.
- Collaborate with developers to investigate test gaps.

## 10. Deliverables

The following files are included in this project:

- `Statement-Coverage/Statement-Coverage-Examples.md`
- `Branch-Coverage/Branch-Coverage-Calculations.md`
- `Path-Coverage/Path-Coverage-Examples.md`
- `Code-Flow-Diagrams/Login-Code-Flow.md`
- `Test-Cases/Login-Test-Cases.md`
- `Coverage-Reports/Coverage-Report-Analysis.md`

## 11. Conclusion

White Box Testing focuses on internal code logic and execution. Statement Coverage checks executed statements, Branch Coverage checks decision outcomes, and Path Coverage examines execution paths.

Coverage metrics help testers identify untested logic and improve test suites, but they must be combined with meaningful assertions and appropriate test scenarios.