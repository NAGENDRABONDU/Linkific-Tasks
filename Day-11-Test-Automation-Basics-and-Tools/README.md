# Test Automation Basics & Tools


## Learning Objectives
- Understand what test automation means.
- Know the benefits and problems of automation.
- Choose which tests are worth automating.
- Recognize common testing tools.
- Understand basic automation frameworks.
- Learn the parts of a first Java + Selenium test.
- Understand the test automation pyramid.

## 1. What Is Test Automation?

**Test automation means using a program to run test steps and check the results.** It helps testers repeat the same checks without doing every step by hand. Manual testing is still important.

### Manual Testing vs Automation Testing

| Manual testing | Automation testing |
|---|---|
| A person follows the steps and checks the result. | A script follows steps and checks the result. |
| Good for exploring a new feature and checking usability. | Good for repeated tests and regression checks. |
| Repeating many tests takes time. | Writing and updating scripts takes time. |

![How test automation works](automation-workflow.png)

### Benefits
- Run the same test many times.
- Get results faster for repeated checks.
- Check important features after a change.
- Run tests with different input data.
- Reduce repeated manual work once scripts are working well.

### Challenges
- Scripts take time to create.
- Scripts need updates when the application changes.
- A test may fail because of timing or test data, not because of a product bug.
- The team needs skills to read and fix scripts.
- Automated tests cannot judge every user experience.

### What Is Automation ROI?

![Automation ROI decision diagram](automation-roi-decision.png)
**ROI means checking whether automation saves more time or cost than it takes to build and maintain.**

Simple estimate:

`ROI (%) = (Benefit − Cost) / Cost × 100`

The benefit and cost should include how often a test runs, time saved, script creation, and maintenance.

## 2. When Should a Test Be Automated?

![Choosing tests to automate](when-to-automate.png)

### Good choices for automation
- Regression tests that run again after code changes.
- Smoke tests that check the main features after a build.
- Stable features with clear expected results.
- The same test run with many sets of data.
- Important workflows that need frequent checking.

### Tests often better done manually
- **Exploratory testing:** the tester investigates the application to find unexpected problems.
- **Usability testing:** a person judges whether the application is easy to use.
- One-time checks that will not be repeated.
- Features changing so often that scripts need constant repair.
- Tests where the expected result is not clear yet.

These are guidelines. A team decides based on risk, time, and maintenance cost.

### Quick Automation Checklist

| Question | What it tells us |
|---|---|
| Will this test be repeated often? | Repeated tests may be worth automating. |
| Is the expected result clear? | The script needs a clear result to check. |
| Is the feature stable? | Stable features usually need less script repair. |
| Is the test data ready? | Good test data makes results more reliable. |
| Is the benefit worth the effort? | Automate when the value is worth the cost. |

## 3. Automation Tools Comparison

| Tool | What it is used for | Simple example |
|---|---|---|
| Selenium | Automating websites in a browser | Check a login page in Chrome. |
| Appium | Automating mobile apps | Test an Android or iOS app. |
| Cypress | Testing web applications | Check actions and results in a website. |
| Playwright | Automating browsers | Test a website in different browsers. |
| JUnit | Running Java tests | Organize Java tests and check results. |
| TestNG | Running and organizing Java tests | Group tests and run selected test cases. |
| Postman | Testing APIs | Send a request and check the response. |
| REST Assured | Testing APIs using Java | Write API checks in Java tests. |

**How to choose:** use the tool that fits the application, programming language, browser or device, team skills, and project needs.

## 4. Common Automation Frameworks

A **framework** is an organized way to build and manage automation tests. It helps keep tests easier to reuse and update.

- **Data-Driven Framework:** the same test runs with different input data, such as several usernames and passwords.
- **Keyword-Driven Framework:** test steps use action names such as `Open Browser` or `Click Login`.
- **Hybrid Framework:** combines more than one framework approach.
- **Page Object Model (POM):** keeps page details, such as locators and page actions, in separate classes. This makes website tests easier to update.

POM is a design pattern. It is not a test runner by itself.

## 5. Java + Selenium Environment Setup

The basic tools for this demo are:
- Java JDK
- IntelliJ IDEA
- Maven
- Selenium Java
- JUnit or TestNG
- Chrome browser

### Setup flow
1. Check Java with `java -version`.
2. Create a Maven Java project in IntelliJ IDEA.
3. Add Selenium and JUnit or TestNG dependencies to `pom.xml`.
4. Create a test class under `src/test/java`.
5. Run the test from IntelliJ IDEA or Maven.
6. `new ChromeDriver()` can use Selenium Manager to manage the browser driver in supported setups. A manually maintained driver folder is not needed for this basic example.
7. If the test does not start, check the dependency versions, browser version, error message, and network access.

### Example Maven dependencies

Replace the placeholder versions with compatible versions selected for the project.

```xml
<dependencies>
    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>YOUR_SELENIUM_VERSION</version>
    </dependency>
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter</artifactId>
        <version>YOUR_JUNIT_VERSION</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

## 6. First Selenium Script

![Automation workflow diagram](automation-workflow-cycle.png)

This example opens a public demo page, checks its title, and closes the browser.

```java
import org.junit.jupiter.api.Test;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import static org.junit.jupiter.api.Assertions.assertEquals;

class FirstSeleniumTest {
    @Test
    void verifyPageTitle() {
        WebDriver driver = new ChromeDriver();

        try {
            driver.get("https://example.com");
            assertEquals("Example Domain", driver.getTitle());
        } finally {
            driver.quit();
        }
    }
}
```

### What each part does
1. `new ChromeDriver()` starts Chrome.
2. `driver.get(...)` opens the website.
3. `driver.getTitle()` reads the page title.
4. `assertEquals(...)` checks whether the actual title matches the expected title.
5. `driver.quit()` closes the browser, even if the check fails.

This is a demo script. Its result should only be recorded as passed after it has actually been run.

## 7. Test Automation Pyramid

![Test automation pyramid](automation-pyramid.png)

- **Unit tests:** check one small part of the code. They are usually fast, so teams can have many of them.
- **Integration tests:** check whether parts of the application work together.
- **End-to-end tests:** check a full user journey, such as logging in and completing a purchase. They are usually slower and fewer in number.

A good test suite uses all suitable levels. Not every check needs to be done through the browser.

## 8. Basic Automation Strategy

1. Choose important tests: start with repeated and high-risk workflows.
2. Set clear expected results: every test should know what success looks like.
3. Select tools: choose tools based on whether the application is web, mobile, API, or another type.
4. Keep tests readable: use clear names and reusable methods.
5. Prepare test data: use known data and avoid tests interfering with each other.
6. Run and record results: record passed, failed, and blocked tests and keep useful error details.
7. Maintain scripts: update scripts when the application changes and investigate flaky failures.
8. Review value: check time saved, test reliability, maintenance effort, and important features covered.
