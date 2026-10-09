Replace your current `README.md` content with this. It includes simple definitions and practical examples for all four Black Box Testing techniques.

# Day 4: Black Box Testing Techniques

## 1. Black Box Testing

**Definition:** Black Box Testing verifies whether an application works according to requirements without examining its internal source code.

**Example:** Enter valid login credentials and verify that the user can log in successfully.

**When to use:** Functional Testing, System Testing, Acceptance Testing, UI Testing, and API Testing.

## 2. Equivalence Partitioning (EP)

**Definition:** Divides input data into valid and invalid groups. One representative value is selected from each group.

**Example: Age Validation**

Requirement: Age must be between 18 and 60, inclusive.

- Invalid partition: Below 18
- Valid partition: 18–60
- Invalid partition: Above 60

| Test Data | Expected Result |
| --------- | --------------- |
| 17        | Rejected        |
| 30        | Accepted        |
| 61        | Rejected        |

## 3. Boundary Value Analysis (BVA)

**Definition:** Tests values at and immediately around the minimum and maximum boundaries.

**Example: Age Validation**

Requirement: Age must be between 18 and 60, inclusive.

| Test Data | Expected Result |
| --------- | --------------- |
| 17        | Rejected        |
| 18        | Accepted        |
| 19        | Accepted        |
| 59        | Accepted        |
| 60        | Accepted        |
| 61        | Rejected        |

## 4. Decision Table Testing

**Definition:** Tests different combinations of conditions and verifies the expected result for each combination.

**Example: E-commerce Discount**

Requirements:

- Premium members receive a 10% discount.
- Orders of ₹5,000 or more receive an additional 5% discount.

| Premium Member? | Order ≥ ₹5,000? | Expected Discount |
| --------------- | --------------- | ----------------- |
| Yes             | Yes             | 15%               |
| Yes             | No              | 10%               |
| No              | Yes             | 5%                |
| No              | No              | 0%                |

*Assumption: Both discounts are added together.*

## 5. State Transition Testing

**Definition:** Tests how an application moves from one state to another after an action or event.

**Example: E-commerce Order**

```
Pending
   |
   v
Confirmed
   |
   v
Shipped
   |
   v
Delivered
```

- Valid transition: Confirmed → Shipped
- Invalid transition: Delivered → Shipped

## 6. Practice Applications

- User Registration
- E-commerce Checkout
- Banking Transactions
- Hotel Booking

## 7. Deliverables

- 10 Equivalence Partitioning examples
- 10 Boundary Value Analysis scenarios
- 5 Decision Tables
- 3 State Transition Diagrams
- 100+ Black Box Test Cases

## Conclusion

Black Box Testing techniques help testers validate requirements, identify defects, improve test coverage, and reduce unnecessary test cases.
