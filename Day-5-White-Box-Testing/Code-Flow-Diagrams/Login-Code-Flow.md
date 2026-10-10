# Login Code Flow Diagrams

## 1. Objective

To understand the execution flow of a login validation function using a flowchart and identify the True and False branches.

## 2. Login Validation Code

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

## 3. Login Flow Diagram

```text
                START
                  |
                  v
       Enter Username and Password
                  |
                  v
       Is username == "admin"?
             /            \
           Yes             No
            |               |
            v               v
 Is password == "1234"?   Invalid Username
        /       \                |
      Yes        No              |
       |          |              |
       v          v              |
    Login      Invalid           |
   Successful  Password          |
       |          |              |
       v          v              v
      END        END            END
```

## 4. Explanation of the Flow

1. The user enters a username and password.
2. The program checks whether the username is `admin`.
3. If the username is incorrect, the program returns `Invalid username`.
4. If the username is correct, the program checks the password.
5. If the password is `1234`, the program returns `Login successful`.
6. If the password is incorrect, the program returns `Invalid password`.

## 5. Test Scenarios

**Scenario 1: Valid Login**

Input: `admin`, `1234`

Expected result: `Login successful`

**Scenario 2: Invalid Password**

Input: `admin`, `wrong`

Expected result: `Invalid password`

**Scenario 3: Invalid Username**

Input: `user`, `1234`

Expected result: `Invalid username`

## 6. Conclusion

A code flow diagram represents the sequence of program execution and its decision branches. It helps testers identify possible execution paths and design test cases for different outcomes.