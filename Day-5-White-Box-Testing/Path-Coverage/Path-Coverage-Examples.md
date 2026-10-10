# Path Coverage Examples

## 1. Definition

Path Coverage is a white box testing technique that checks whether all possible execution paths in a program have been executed.

An execution path is the sequence of statements and decisions followed from the start to the end of a program.

## 2. Example Code

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

## 3. Code Flow Diagram

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

## 4. Identify Execution Paths

### Path 1: Valid Login

**Input:**
- Username: admin
- Password: 1234

**Execution Path:**

Start → Username True → Password True → Login successful → End

### Path 2: Invalid Password

**Input:**
- Username: admin
- Password: wrong

**Execution Path:**

Start → Username True → Password False → Invalid password → End

### Path 3: Invalid Username

**Input:**
- Username: user
- Password: 1234

**Execution Path:**

Start → Username False → Invalid username → End

## 5. Path Coverage Calculation

For this example, there are three feasible execution paths.

Path Coverage (%) = (Executed Paths / Total Feasible Paths) × 100

If all three paths are executed:

Path Coverage = (3 / 3) × 100 = 100%

## 6. Difference Between Branch Coverage and Path Coverage

**Branch Coverage:** Checks whether every decision outcome (True and False) has been executed.

**Path Coverage:** Checks whether every feasible execution path has been executed.

Path coverage is generally more demanding because one path can combine multiple branch outcomes.

## 7. Limitations of Path Coverage

- Programs with multiple decisions can have many execution paths.
- Loops can create a very large or potentially unbounded number of paths.
- Some paths may be infeasible because of program logic.
- Testing every possible path may be impractical for large applications.

## 8. Conclusion

Path coverage helps testers understand how different combinations of decisions affect program execution. It is useful for identifying untested logic, but achieving 100% path coverage can be difficult in complex applications.