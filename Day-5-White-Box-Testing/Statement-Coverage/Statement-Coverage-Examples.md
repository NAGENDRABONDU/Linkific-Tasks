# Statement Coverage Examples

## 1. Definition

Statement Coverage is a white box testing technique that measures the percentage of executable statements executed during testing.

## 2. Formula

Statement Coverage (%) = (Executed Statements / Total Executable Statements) × 100

## 3. Example Code

```python
def check_age(age):
    if age >= 18:
        print("Eligible")
    print("Verification completed")

check_age(20)
```

## 4. Code Flow Diagram

```text
        START
          |
          v
     Input Age
          |
          v
      Age >= 18?
       /      \
     True      False
      |          |
      v          |
 Print Eligible  |
       \        /
          v
 Print Verification Completed
          |
          v
         END
```

## 5. Test Case 1: Age = 20

**Expected Result:**
- Eligible
- Verification completed

**Executed Statements:**
1. Check age condition.
2. Print Eligible.
3. Print Verification completed.

Statement Coverage = (3 / 3) × 100 = **100%**

## 6. Test Case 2: Age = 16

**Expected Result:**
- Verification completed

**Executed Statements:**
1. Check age condition.
2. Print Verification completed.

The `print("Eligible")` statement is not executed.

Statement Coverage = (2 / 3) × 100 = **66.67%**

## 7. Identify Test Gaps

When only age 16 is tested, the `print("Eligible")` statement remains unexecuted.

Adding a test case with age 20 executes the missing statement.

Both test cases together achieve:
- Statement Coverage: 100%
- Branch Coverage: 100%

## 8. Conclusion

Statement coverage helps testers identify executable statements that have not been tested. However, 100% statement coverage does not always guarantee that every decision outcome has been tested.