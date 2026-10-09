# Decision Table Testing

## Definition

Decision Table Testing verifies different combinations of conditions and their expected results.

## Decision Table 1: E-commerce Discount

**Requirements:**
- Premium members receive a 10% discount.
- Orders of ₹5,000 or more receive an additional 5% discount.

| Rule | Premium Member? | Order ≥ ₹5,000? | Expected Discount |
|---|---|---|---|
| R1 | Yes | Yes | 15% |
| R2 | Yes | No | 10% |
| R3 | No | Yes | 5% |
| R4 | No | No | 0% |

## Decision Table 2: Login Validation

**Requirements:**
- Login succeeds when the username and password are valid and the account is not locked.

| Rule | Username Valid? | Password Valid? | Account Locked? | Expected Result |
|---|---|---|---|---|
| R1 | Yes | Yes | No | Login succeeds |
| R2 | No | Any | No | Login rejected |
| R3 | Yes | No | No | Login rejected |
| R4 | Yes | Yes | Yes | Login rejected |

## Decision Table 3: Free Shipping

**Requirements:**
- Orders of ₹2,000 or more qualify for free shipping.

| Rule | Order ≥ ₹2,000? | Expected Shipping |
|---|---|---|
| R1 | Yes | Free |
| R2 | No | Paid |

## Decision Table 4: Loan Eligibility

**Requirements:**
- The applicant must meet the minimum age, income, and credit requirements.

| Rule | Meets Age Requirement? | Meets Income Requirement? | Credit Check Passed? | Expected Result |
|---|---|---|---|---|
| R1 | Yes | Yes | Yes | Eligible for next stage |
| R2 | No | Any | Any | Rejected |
| R3 | Yes | No | Any | Rejected |
| R4 | Yes | Yes | No | Rejected |

## Decision Table 5: Booking Confirmation

**Requirements:**
- A booking is confirmed only when payment succeeds and the room or slot is available.

| Rule | Payment Successful? | Room/Slot Available? | Expected Result |
|---|---|---|---|
| R1 | Yes | Yes | Booking confirmed |
| R2 | Yes | No | Booking not confirmed; handle refund |
| R3 | No | Yes | Booking remains unconfirmed |
| R4 | No | No | Booking not confirmed |

## Conclusion

Decision Table Testing helps verify combinations of business conditions and ensures the correct action is taken for each combination.