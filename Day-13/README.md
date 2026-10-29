# Day 13: Advanced Selenium & Automation Frameworks

## Learning Objectives

- Handle complex Selenium scenarios.
- Understand implicit, explicit, and fluent waits.
- Implement the Page Object Model (POM).
- Use TestNG annotations, assertions, data providers, suites, priorities, and parallel-execution settings.
- Organize reusable automation code into a maintainable framework.

## Project Folder Structure

```text
Day13-Selenium-Framework/
├── pom.xml
├── testng.xml
├── README.md
└── src/
    └── test/
        ├── java/
        │   ├── base/
        │   │   └── BaseTest.java
        │   ├── pages/
        │   │   ├── LoginPage.java
        │   │   ├── HomePage.java
        │   │   ├── InventoryPage.java
        │   │   ├── CartPage.java
        │   │   ├── CheckoutPage.java
        │   │   └── PracticePage.java
        │   ├── tests/
        │   │   ├── LoginTest.java
        │   │   ├── InventoryTest.java
        │   │   ├── CheckoutTest.java
        │   │   ├── AdvancedInteractionsTest.java
        │   │   └── DynamicElementsTest.java
        │   └── utilities/
        │       ├── WaitUtils.java
        │       └── ScreenshotUtils.java
        └── resources/
            └── config.properties
```

## 1. Selenium Waits

### Implicit Wait
A global wait applied when Selenium searches for elements. Avoid mixing implicit and explicit waits because timing can become unpredictable.

```java
driver.manage().timeouts().implicitlyWait(Duration.ZERO);
```

### Explicit Wait
Waits for a specific condition, such as an element becoming visible or clickable.

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
WebElement button = wait.until(
    ExpectedConditions.elementToBeClickable(By.id("login-button"))
);
button.click();
```

### Fluent Wait
Allows a custom timeout, polling interval, and ignored exceptions.

```java
Wait<WebDriver> wait = new FluentWait<>(driver)
    .withTimeout(Duration.ofSeconds(10))
    .pollingEvery(Duration.ofMillis(300))
    .ignoring(NoSuchElementException.class);
```

**Preferred approach:** use explicit waits for most UI interactions. Avoid `Thread.sleep()` because it waits for a fixed time even when the page is ready sooner.

## 2. Complex Scenarios

The project uses two practice websites because the SauceDemo shopping flow does not contain every advanced interaction.

- SauceDemo: https://www.saucedemo.com/
- The Internet: https://the-internet.herokuapp.com/

| Scenario | Practice |
|---|---|
| JavaScript alerts | Read alert text, accept, and dismiss |
| Frames/iframes | Switch into a frame and return to default content |
| Multiple windows | Store window handle, switch to the new window, then return |
| Mouse hover | Use `Actions.moveToElement()` |
| Drag and drop | Use `Actions.dragAndDrop()` |
| Right-click | Use `Actions.contextClick()` |
| Double-click | Use `Actions.doubleClick()` on a suitable element |
| Keyboard actions | Use `Actions.sendKeys()` |
| Dynamic elements | Wait for elements to appear or disappear |
| Loading/AJAX | Wait for the required page condition instead of fixed delays |

## 3. Page Object Model (POM)

POM separates page locators and actions from test scenarios.

```text
Test class
   |
   | calls page methods
   v
Page Object class ---- uses ----> WaitUtils
   |
   | locates/interacts with elements
   v
Web application

BaseTest manages WebDriver setup and cleanup.
```

### Page class responsibilities

- Store locators for one page.
- Provide methods for page actions, such as `login()` or `addBackpackToCart()`.
- Use explicit waits where needed.
- Avoid putting unrelated test assertions inside page classes.

### Test class responsibilities

- Call page methods.
- Verify expected outcomes with TestNG assertions.
- Keep each test focused on one scenario.

## 4. TestNG Framework

| Feature | Purpose |
|---|---|
| `@BeforeMethod` | Prepare a fresh browser before a test |
| `@Test` | Mark a test method |
| `@AfterMethod` | Clean up after a test |
| `Assert` | Compare actual and expected results |
| `@DataProvider` | Run a test with multiple input sets |
| `testng.xml` | Select test classes and configure suite execution |
| `priority` | Set a test ordering preference; tests should still be independent |
| Parallel execution | Run tests concurrently after sequential execution is stable |

Start with `parallel="false"`. Enable parallel execution only when each test has its own WebDriver and independent data.

## 5. Framework Components

- **`BaseTest.java`** — shared WebDriver setup and teardown.
- **`pages/`** — page locators and reusable page actions.
- **`tests/`** — test scenarios and assertions.
- **`WaitUtils.java`** — reusable explicit-wait helpers.
- **`ScreenshotUtils.java`** — screenshot helper.
- **`config.properties`** — base URLs and test configuration.
- **`pom.xml`** — Selenium and TestNG dependencies.
- **`testng.xml`** — TestNG suite configuration.

## 6. SauceDemo Test Scenarios

Practice credentials: `standard_user` / `secret_sauce`.

1. Verify valid login opens the inventory page.
2. Verify invalid login displays an error.
3. Sort product names alphabetically.
4. Add a product to the cart and verify the cart badge.
5. Verify the expected product is in the cart.
6. Complete checkout with valid customer details.
7. Verify the order confirmation.
8. Use a TestNG `@DataProvider` for multiple login-data sets.

## 7. Run in Eclipse

1. Import the project using **File → Import → Existing Maven Projects**.
2. Select the project directory.
3. Right-click the project and select **Maven → Update Project**.
4. Ensure Chrome is installed. `new ChromeDriver()` uses Selenium Manager; no manually maintained `Drivers` folder is required.
5. Right-click `testng.xml` and choose **Run As → TestNG Suite**.

Terminal alternative, from the project directory:

```bash
mvn clean test
```

## Deliverables Checklist

- [ ] Advanced Selenium scripts for waits and complex interactions.
- [ ] POM implementation with separate page classes.
- [ ] TestNG suite with annotations and assertions.
- [ ] Data provider and suite configuration.
- [ ] Reusable framework with BaseTest and utilities.
- [ ] Configuration properties file.
- [ ] `README.md` framework documentation.
- [ ] `README.docx` framework documentation.

## Notes

The test code is a learning template and must be run in the local environment before results are considered verified. Check locators and page behavior if the practice website changes.
