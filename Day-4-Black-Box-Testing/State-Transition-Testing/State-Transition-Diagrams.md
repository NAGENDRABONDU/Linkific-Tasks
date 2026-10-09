# State Transition Testing

## Definition

State Transition Testing verifies how an application moves from one state to another when an action or event occurs.

## Diagram 1: E-commerce Order

**States:** Pending, Confirmed, Shipped, Delivered, Cancelled.

```text
Pending
   |
   | Payment successful
   v
Confirmed
   |
   | Order dispatched
   v
Shipped
   |
   | Delivery completed
   v
Delivered
```

**Additional transition:**

```text
Pending → Cancelled
```

**Test cases:**
- Pending → Confirmed: Valid transition.
- Confirmed → Shipped: Valid transition.
- Shipped → Delivered: Valid transition.
- Delivered → Shipped: Invalid transition.

## Diagram 2: User Account Lock

**States:** Unlocked, Locked, Authenticated.

```text
Unlocked
   |
   | Three consecutive incorrect passwords
   v
Locked
   |
   | Successful password reset
   v
Unlocked
```

**Additional transition:**

```text
Unlocked → Authenticated
Correct password
```

**Test cases:**
- Unlocked → Authenticated: Valid transition.
- Unlocked → Locked: Valid transition after three consecutive incorrect attempts.
- Locked → Unlocked: Valid transition after successful password reset.
- Locked → Authenticated using the correct password without unlocking: Invalid transition.

## Diagram 3: Banking Transaction

**States:** Initiated, Processing, Successful, Failed, Reversed.

```text
Initiated
    |
    v
Processing
   / \
  v   v
Successful  Failed
                |
                | Reversal supported
                v
             Reversed
```

**Test cases:**
- Initiated → Processing: Valid transition.
- Processing → Successful: Valid transition.
- Processing → Failed: Valid transition.
- Failed → Reversed: Valid when reversal is supported.
- Failed → Successful without a retry or new transaction: Invalid transition.

## Conclusion

State Transition Testing verifies valid state changes, invalid transitions, and the behavior of an application in each state.