# Testing Levels

Testing levels define the different stages at which software is tested, starting from a small piece of code and progressing to the complete application.

---

## 1. Unit Testing

### Definition

Unit Testing is the process of testing **one small and individual part of the software**, such as a method, function, or class.

It is usually performed by **developers**.

### Example

Consider an e-commerce application that calculates the total price.

```text
Product Price = ₹100
Quantity       = 2
Expected Total = ₹200
```
The developer tests the price calculation method to verify whether it correctly returns ₹200.
Key Points
- Tests a small and individual part of the software.
- Usually performed by developers.
- Helps identify defects at an early stage.
- Focuses on the internal logic of a component.
Remember
Unit Testing → Testing one small part of the software.
## 2. Integration Testing
### Definition
Integration Testing is the process of testing whether two or more modules work correctly together and exchange data correctly.
### Example
Consider an e-commerce application.
```text
Product
   ↓
Cart
   ↓
Payment
```
### We verify:
- The product is added to the cart correctly.
- The cart displays the correct product.
- The correct amount is passed from the cart to the payment module.
- The payment module receives the correct information.
### Key Points
- Tests the interaction between two or more modules.
- Checks data flow between modules.
- Helps identify communication and integration problems.
- Focuses on how different modules work together.
## 3. System Testing
### Definition
System Testing is the process of testing the complete integrated application to verify that it works according to the specified requirements.
### Example
Consider an e-commerce application.
```text
Login
  ↓
Homepage
  ↓
Select Product
  ↓
Add to Cart
  ↓
Checkout
  ↓
Payment
  ↓
Order Confirmation
```

The tester verifies the complete application flow from start to end.
### We verify:
- User can log in.
- User can select a product.
- User can add the product to the cart.
- User can checkout.
- User can make payment.
- Order is placed successfully.
- Confirmation message is displayed.
### Key Points
- Tests the complete integrated application.
- Usually performed by testers.
- Checks the application against specified requirements.
- Covers complete business flows and functionality.
## 4. Acceptance Testing
### Definition
Acceptance Testing is the process of verifying whether the software meets customer requirements and business needs and is acceptable for use or release.
### Example
Suppose the business requirement is:
Customer should be able to:
```text
Login
   ↓
Select Product
   ↓
Purchase Product
   ↓
Make Payment
   ↓
Receive Order Confirmation
```
