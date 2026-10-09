# Equivalence Partitioning (EP) Examples

## Definition

Equivalence Partitioning divides input data into valid and invalid groups. One representative value is selected from each group to reduce the number of test cases.

## Example 1: Password Length

**Requirement:** Password must contain 8–16 characters.

| Test Data | Partition | Expected Result |
|---|---|---|
| 10 characters | Valid | Accepted |
| 7 characters | Invalid: Below minimum | Rejected |
| 17 characters | Invalid: Above maximum | Rejected |

## Example 2: Age

**Requirement:** Age must be between 18 and 60.

| Test Data | Partition | Expected Result |
|---|---|---|
| 30 | Valid | Accepted |
| 17 | Invalid: Below minimum | Rejected |
| 61 | Invalid: Above maximum | Rejected |

## Example 3: Username Length

**Requirement:** Username must contain 5–12 characters.

| Test Data | Partition | Expected Result |
|---|---|---|
| 7 characters | Valid | Accepted |
| 4 characters | Invalid: Below minimum | Rejected |
| 13 characters | Invalid: Above maximum | Rejected |

## Example 4: Mobile Number

**Requirement:** Mobile number must contain exactly 10 digits and start with 6, 7, 8, or 9.

| Test Data | Partition | Expected Result |
|---|---|---|
| 9876543210 | Valid | Accepted |
| 987654321 | Invalid: 9 digits | Rejected |
| 98765432101 | Invalid: 11 digits | Rejected |

## Example 5: Product Quantity

**Requirement:** Quantity must be a whole number from 1 to 10.

| Test Data | Partition | Expected Result |
|---|---|---|
| 5 | Valid | Accepted |
| 0 | Invalid: Below minimum | Rejected |
| 11 | Invalid: Above maximum | Rejected |

## Example 6: Monthly Salary

**Requirement:** Salary must be between ₹15,000 and ₹100,000.

| Test Data | Partition | Expected Result |
|---|---|---|
| ₹50,000 | Valid | Accepted |
| ₹14,999 | Invalid: Below minimum | Rejected |
| ₹100,001 | Invalid: Above maximum | Rejected |

## Example 7: Exam Marks

**Requirement:** Marks must be a whole number from 0 to 100.

| Test Data | Partition | Expected Result |
|---|---|---|
| 67 | Valid | Accepted |
| -1 | Invalid: Below minimum | Rejected |
| 101 | Invalid: Above maximum | Rejected |

## Example 8: Discount Percentage

**Requirement:** Discount must be between 0% and 50%. Decimal values are allowed.

| Test Data | Partition | Expected Result |
|---|---|---|
| 25% | Valid | Accepted |
| -1% | Invalid: Below minimum | Rejected |
| 51% | Invalid: Above maximum | Rejected |

## Example 9: File Size

**Requirement:** File size must be between 1 MB and 20 MB.

| Test Data | Partition | Expected Result |
|---|---|---|
| 13 MB | Valid | Accepted |
| 0 MB | Invalid: Below minimum | Rejected |
| 21 MB | Invalid: Above maximum | Rejected |

## Example 10: Hotel Booking Duration

**Requirement:** Booking duration must be a whole number from 1 to 30 nights.

| Test Data | Partition | Expected Result |
|---|---|---|
| 15 nights | Valid | Accepted |
| 0 nights | Invalid: Below minimum | Rejected |
| 31 nights | Invalid: Above maximum | Rejected |

## Conclusion

Equivalence Partitioning helps reduce test cases by selecting representative values from valid and invalid input groups. Additional partitions should be tested when requirements specify other input types or formats.