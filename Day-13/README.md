# Day 13 — Advanced Selenium with Java, TestNG, Maven, and POM

## 1. Goal

Build one maintainable automation framework for [SauceDemo](https://www.saucedemo.com/) using **Java + Selenium WebDriver + TestNG + Maven + Page Object Model (POM)**.

This guide is written as a learning path: create the project structure first, then understand each part, and run the tests from Eclipse.

## 2. Simple definitions

- **Selenium WebDriver:** controls a real browser to automate actions such as typing, clicking, and reading page content.
- **TestNG:** runs tests and provides annotations such as `@Test`, `@BeforeMethod`, and `@AfterMethod`.
- **Maven:** downloads project dependencies and provides standard commands to build and run tests.
- **Page Object Model (POM):** keeps page locators and page actions in page classes. Test classes describe what should be tested.
- **Explicit wait:** waits until a specific condition is true, such as a button becoming clickable.
- **BaseTest:** shared setup and cleanup code used by test classes.
- **DataProvider:** runs the same test with multiple sets of input data.
- **Parallel execution:** runs multiple tests at the same time. Start with sequential execution until the suite is stable.

## 3. Project structure

Create this structure in Eclipse. Keep the package names and file names consistent.

```text
Day13-SauceDemo-POM/
├── pom.xml
├── testng.xml
└── src/
    └── test/
        ├── java/
        │   ├── base/
        │   │   └── BaseTest.java
        │   ├── pages/
        │   │   ├── LoginPage.java
        │   │   ├── InventoryPage.java
        │   │   ├── CartPage.java
        │   │   └── CheckoutPage.java
        │   ├── tests/
        │   │   ├── LoginTest.java
        │   │   ├── InventoryTest.java
        │   │   ├── CheckoutTest.java
        │   │   └── TestNGFeaturesTest.java
        │   └── utilities/
        │       ├── WaitUtils.java
        │       └── ScreenshotUtils.java
        └── resources/
            └── config.properties
```

### What belongs where?

| File/folder | Responsibility |
|---|---|
| `pom.xml` | Selenium, TestNG, and Maven configuration |
| `testng.xml` | Chooses which TestNG tests to run |
| `BaseTest.java` | Starts Chrome, opens the website, and closes the browser |
| `pages/` | Locators and actions for each web page |
| `tests/` | Test scenarios and assertions |
| `WaitUtils.java` | Reusable explicit-wait methods |
| `ScreenshotUtils.java` | Reusable screenshot helper |
| `config.properties` | Website URL and other settings |

## 4. How POM works

```text
Test class
   |
   | calls page methods
   v
Page Object class  ---- uses ----> WaitUtils
   |
   | finds and interacts with elements
   v
SauceDemo website

BaseTest sets up and closes WebDriver for each test.
```

**Rule:** Put page locators and page actions in the relevant page class. Keep assertions and test intent in test classes as much as possible.

## 5. Setup in Eclipse

1. Select **File → New → Maven Project**.
2. Create a project with an example artifact ID such as `day13-saucedemo-pom`.
3. Replace the generated `pom.xml` with the Maven configuration from the project package.
4. Create the packages and Java files shown in the structure above.
5. Put `config.properties` inside `src/test/resources`.
6. Keep `testng.xml` at the project root.
7. Right-click the project → **Maven → Update Project**.
8. Confirm that Chrome is installed. The code uses `new ChromeDriver()` and Selenium Manager; no manually maintained `Drivers` folder is needed.

Example `config.properties`:

```properties
baseUrl=https://www.saucedemo.com/
username=standard_user
password=secret_sauce
```

Use the matching property names in `BaseTest.java`.

## 6. The 11 learning tasks — one POM framework

| No. | Task | Where to implement it | Simple explanation |
|---:|---|---|---|
| 1 | Explicit waits | `WaitUtils.java`, page classes | Wait for elements to become visible or clickable instead of using fixed delays. |
| 2 | Alerts | A separate practice site | SauceDemo's normal shopping flow does not provide a JavaScript alert scenario. |
| 3 | Frames | A separate practice site | The normal SauceDemo flow does not contain an iframe exercise. |
| 4 | Multiple windows | A separate practice site | The normal shopping flow does not require switching browser windows. |
| 5 | Actions class | A separate practice site or suitable UI | Practice hover, right-click, or drag-and-drop on a page that supports them. |
| 6 | Dynamic elements | `InventoryPage.java`, `CartPage.java` | Wait for product lists and cart counts to update, then verify the result. |
| 7 | Page Object Model | All classes in `pages/` | Keep page locators/actions separate from test scenarios. |
| 8 | Base test class | `BaseTest.java` | Reuse browser setup and teardown in every test class. |
| 9 | TestNG features | `TestNGFeaturesTest.java`, test classes | Use annotations, assertions, and `@DataProvider`. |
| 10 | Automation framework | Whole project | Connect configuration, page classes, utilities, tests, and Maven. |
| 11 | Parallel execution | `testng.xml` and `BaseTest.java` | Try only after sequential tests are stable and every test has its own WebDriver. |

**Important:** These 11 topics belong to one learning plan, but not every topic can be demonstrated honestly on SauceDemo. Do not write fake alert/frame/window tests for elements that do not exist there.

## 7. SauceDemo test scenarios

Use the standard demo credentials shown on the website:

- Username: `standard_user`
- Password: `secret_sauce`

Suggested scenarios:

1. Valid login opens the inventory page.
2. Invalid login shows an error.
3. Product names can be sorted alphabetically.
4. Adding the backpack updates the cart badge.
5. The cart contains the product that was added.
6. Checkout accepts valid first name, last name, and postal code.
7. Finishing checkout displays the order confirmation.
8. A `@DataProvider` supplies multiple login-data sets.

Use assertions in every test. For example, verify the URL after login or verify the confirmation message after checkout. A test that only clicks buttons without checking the result is incomplete.

## 8. Code pattern examples

### A. Page Object constructor

```java
public class LoginPage {
    private WebDriver driver;
    private WebDriverWait wait;

    public LoginPage(WebDriver driver) {
        this.driver = driver;
        this.wait = new WebDriverWait(driver, Duration.ofSeconds(10));
    }
}
```

**Meaning:** The test passes its current browser to the page object. The page object can then find elements in that browser.

### B. Explicit wait

```java
WebElement loginButton = wait.until(
    ExpectedConditions.elementToBeClickable(By.id("login-button"))
);
loginButton.click();
```

**Meaning:** Selenium waits up to 10 seconds for the login button to be clickable. It continues immediately if the condition becomes true.

### C. TestNG test

```java
@Test
public void validLoginOpensInventory() {
    LoginPage loginPage = new LoginPage(driver);
    loginPage.login("standard_user", "secret_sauce");

    Assert.assertTrue(driver.getCurrentUrl().contains("inventory.html"));
}
```

**Meaning:** Perform the login, then check the expected result with an assertion. In the full project, use the existing page methods and BaseTest setup rather than duplicating setup in each test.

### D. DataProvider idea

```java
@DataProvider(name = "loginData")
public Object[][] loginData() {
    return new Object[][] {
        {"standard_user", "secret_sauce"},
        {"wrong_user", "wrong_password"}
    };
}
```

**Meaning:** TestNG can pass each row to a test method, allowing one test structure to be run with different inputs. Make the expected result explicit for each row.

## 9. Run the project

### In Eclipse

1. Save all files.
2. Right-click the project → **Maven → Update Project**.
3. Right-click `testng.xml` → **Run As → TestNG Suite**.
4. Review the TestNG results and the Console output.

### From a terminal in the project folder

```bash
mvn clean test
```

This command asks Maven to clean previous build output and run the configured tests. It requires Maven to be installed and available on the system PATH.

Start with `parallel="false"` in `testng.xml`. Do not increase parallel execution until the tests pass reliably one at a time.

## 10. Common problems

- **ChromeDriver session error:** Update Chrome or allow Selenium Manager to resolve a compatible driver; avoid a manually pinned, outdated driver.
- **Element not found:** Check the locator, current page, and whether the page has loaded. Add a condition-based explicit wait where needed.
- **Test passes alone but fails in a suite:** Check shared browser state, test data, parallel settings, and timing. Give each test its own WebDriver.
- **Maven dependencies missing:** Right-click project → Maven → Update Project.
- **TestNG suite does not run:** Check that the class names in `testng.xml` exactly match the package and class names.

## 11. Completion checklist

- [ ] Maven project imports without dependency errors.
- [ ] `BaseTest` opens and closes Chrome.
- [ ] Page classes contain their own locators and actions.
- [ ] Tests contain meaningful assertions.
- [ ] Login, sorting, cart, and checkout scenarios are covered.
- [ ] Tests pass sequentially before parallel execution is attempted.
- [ ] Alerts, frames, windows, and advanced Actions are practiced on a site that actually supports those interactions.

## Reference

Sauce Labs' official Selenium demonstration documentation shows the basic SauceDemo login flow and emphasizes checking the expected result with assertions: [Selenium Demonstration Scripts](https://docs.saucelabs.com/web-apps/automated-testing/selenium/sample-scripts/).

The framework files are a learning template. They have not been run in your local Eclipse environment, so run the suite and resolve any environment-specific issues before treating the results as verified.
