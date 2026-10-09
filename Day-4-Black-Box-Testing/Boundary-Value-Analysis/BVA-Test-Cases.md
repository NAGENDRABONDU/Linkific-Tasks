# Boundary Value Analysis (BVA) Test Cases

## Definition

Boundary Value Analysis tests values at the minimum and maximum limits, including values immediately below and above those limits.

## Scenario 1: Password Length

**Requirement:** Password must contain 8–16 characters.

| Test Data | Expected Result |
|---|---|
| 7 characters | Rejected |
| 8 characters | Accepted |
| 9 characters | Accepted |
| 15 characters | Accepted |
| 16 characters | Accepted |
| 17 characters | Rejected |

## Scenario 2: Age

**Requirement:** Age must be between 18 and 60.

| Test Data | Expected Result |
|---|---|
| 17 | Rejected |
| 18 | Accepted |
| 19 | Accepted |
| 59 | Accepted |
| 60 | Accepted |
| 61 | Rejected |

## Scenario 3: Username Length

**Requirement:** Username must contain 5–12 characters.

| Test Data | Expected Result |
|---|---|
| 4 characters | Rejected |
| 5 characters | Accepted |
| 6 characters | Accepted |
| 11 characters | Accepted |
| 12 characters | Accepted |
| 13 characters | Rejected |

## Scenario 4: Monthly Salary

**Requirement:** Salary must be between ₹15,000 and ₹100,000, inclusive. Whole rupees only.

| Test Data | Expected Result |
|---|---|
| ₹14,999 | Rejected |
| ₹15,000 | Accepted |
| ₹15,001 | Accepted |
| ₹99,999 | Accepted |
| ₹100,000 | Accepted |
| ₹100,001 | Rejected |

## Scenario 5: Exam Marks

**Requirement:** Marks must be a whole number from 0 to 100.

| Test Data | Expected Result |
|---|---|
| -1 | Rejected |
| 0 | Accepted |
| 1 | Accepted |
| 99 | Accepted |
| 100 | Accepted |
| 101 | Rejected |

## Scenario 6: Product Quantity

**Requirement:** Quantity must be a whole number from 1 to 10.

| Test Data | Expected Result |
|---|---|
| 0 | Rejected |
| 1 | Accepted |
| 2 | Accepted |
| 9 | Accepted |
| 10 | Accepted |
| 11 | Rejected |

## Scenario 7: Discount Percentage

**Requirement:** Discount must be between 0% and 50%, inclusive.

| Test Data | Expected Result |
|---|---|
| -1% | Rejected |
| 0% | Accepted |
| 1% | Accepted |
| 49% | Accepted |
| 50% | Accepted |
| 51% | Rejected |

## Scenario 8: File Size

**Requirement:** File size must be between 1 MB and 20 MB, inclusive.

| Test Data | Expected Result |
|---|---|
| 0 MB | Rejected |
| 1 MB | Accepted |
| 2 MB | Accepted |
| 19 MB | Accepted |
| 20 MB | Accepted |
| 21 MB | Rejected |

## Scenario 9: Hotel Booking Duration

**Requirement:** Booking duration must be a whole number from 1 to 30 nights.

| Test Data | Expected Result |
|---|---|
| 0 nights | Rejected |
| 1 night | Accepted |
| 2 nights | Accepted |
| 29 nights | Accepted |
| 30 nights | Accepted |
| 31 nights | Rejected |

## Scenario 10: Cart Item Limit

**Requirement:** A shopping cart allows between 1 and 99 items, inclusive.

| Test Data | Expected Result |
|---|---|
| 0 items | Rejected |
| 1 item | Accepted |
| 2 items | Accepted |
| 98 items | Accepted |
| 99 items | Accepted |
| 100 items | Rejected |

## Conclusion

Boundary Value Analysis helps identify defects near input limits by testing values just below, at, and just above the minimum and maximum boundaries.