# Testing Levels

Testing levels define **what we are testing**, from a small piece of code to the complete application.

---

## 1. Unit Testing

### Definition

Unit Testing means testing **one small part of the code**, such as a method or function.

Usually performed by **developers**.

### Example

In an e-commerce application:

```text
Price = ₹100
Quantity = 2
Total = ₹200
```
The developer tests the price calculation method to check whether it gives ₹200.
Remember
Unit Testing → One small part

2. Integration Testing
Definition
Integration Testing means testing whether two or more modules work correctly together.
Example
```text
In an e-commerce application:
Product
   ↓
Cart
   ↓
Payment
````
We check:
- Product is added to Cart.
- Cart shows the correct product.
- Correct amount is sent to Payment.
Remember
Integration Testing → Modules working together

3. System Testing
Definition
System Testing means testing the complete application.
Example
```text
For an e-commerce application:
Login
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
We test the complete application flow.
Remember
System Testing → Complete application

4. Acceptance Testing
Definition
Acceptance Testing means checking whether the software meets customer and business requirements.
Example
Business requirement:
Customer should be able to purchase a product and receive an order confirmation.

We verify whether the application satisfies this requirement.
UAT
UAT means User Acceptance Testing.
Business users or customers may perform UAT before the product is released.
Remember
Acceptance Testing → Customer/Business requirements

Testing Levels - Easy Difference
Level	Simple Meaning
Unit Testing	Test one small part
Integration Testing	Test modules together
System Testing	Test the complete application
Acceptance Testing	Check customer/business requirements

```text
Easy Flow
Unit
 ↓
One Part

Integration
 ↓
Parts Together

System
 ↓
Complete Application

Acceptance
 ↓
Customer/Business Acceptance
```
