# Selenium WebDriver Basics

## Learning Objectives
- Understand Selenium WebDriver fundamentals.
- Locate web elements using all eight common locator types.
- Perform basic actions on web elements.
- Work with text boxes, buttons, checkboxes, radio buttons, dropdowns, links, and images.

## 1. What Is Selenium WebDriver?
Selenium WebDriver is a tool used to automate web browsers. A test script can open a website, locate elements, interact with them, and verify the results.

## 2. WebDriver Basics
- `new ChromeDriver()` starts a Chrome browser session.
- `driver.get("URL")` opens a website.
- `driver.close()` closes the current browser window.
- `driver.quit()` closes all browser windows and ends the WebDriver session.

Use `driver.quit()` in the cleanup section of most tests so the entire browser session is closed.

## 3. The Eight Locator Types

| Locator | Java example | Purpose |
|---|---|---|
| ID | `By.id("username")` | Finds an element by its ID. Prefer it when it is unique and stable. |
| Name | `By.name("username")` | Finds an element by its `name` attribute. |
| Class Name | `By.className("login-button")` | Finds an element by one class name. |
| Tag Name | `By.tagName("input")` | Finds elements by HTML tag; it may return multiple matches. |
| Link Text | `By.linkText("Forgot Password?")` | Finds a link by its exact visible text. |
| Partial Link Text | `By.partialLinkText("Forgot")` | Finds a link using part of its visible text. |
| CSS Selector | `By.cssSelector("input#username")` | Finds elements using CSS selector syntax. |
| XPath | `By.xpath("//input[@id='username']")` | Finds elements using attributes, text, and DOM relationships. |

### Choosing Reliable Locators
1. Prefer a unique, stable ID when one is available.
2. Use stable attributes such as `name` when suitable.
3. Use CSS selectors or XPath when simpler locators are not enough.
4. Prefer readable relative XPath expressions over long absolute XPath paths.
5. Check that the locator identifies the intended element and not several unintended elements.

CSS selectors are not always faster than XPath, or vice versa. Reliability, stability, and readability should guide the choice.

## 4. Common Web Element Actions

| Method | Purpose |
|---|---|
| `sendKeys("text")` | Enters text into a field. |
| `click()` | Clicks a button, link, checkbox, or other clickable element. |
| `clear()` | Clears text from an editable field. |
| `getText()` | Reads visible text from an element. |
| `getAttribute("value")` | Reads an attribute or input value. |
| `isDisplayed()` | Checks whether an element is displayed. |
| `isEnabled()` | Checks whether an element is enabled. |
| `isSelected()` | Checks whether a checkbox, radio button, or option is selected. |

## 5. Working with Different Element Types
- **Text boxes:** use `sendKeys()`, `clear()`, and `getAttribute("value")`.
- **Buttons:** use `click()` and verify the result.
- **Checkboxes:** use `isSelected()` before clicking when the test needs a specific state.
- **Radio buttons:** select the required option and verify its selected state.
- **Dropdowns:** for a native HTML `<select>`, use Selenium's `Select` class and methods such as `selectByVisibleText()`.
- **Links:** click the link and verify the destination URL or page content.
- **Images:** inspect attributes such as `alt` or `src`, and check visibility when appropriate.

## 6. Practice Scenarios
The following scenarios can be used to build and review 10 or more separate Java + Selenium scripts.

1. **All eight locators:** locate suitable elements using ID, Name, Class Name, Tag Name, Link Text, Partial Link Text, CSS Selector, and XPath.
2. **Valid login:** enter valid practice credentials, submit the form, and verify the success message.
3. **Invalid login:** enter invalid credentials and verify the error message.
4. **Text field actions:** enter text, read the value, clear the field, and enter new text.
5. **Button interaction:** click a button and verify the resulting page state.
6. **Checkbox interaction:** select and deselect a checkbox and verify each state.
7. **Radio button interaction:** select an option and verify that it is selected.
8. **Dropdown interaction:** choose an option from a native HTML dropdown and verify the selected value.
9. **Link navigation:** click a link and verify the destination.
10. **Element state checks:** verify `isDisplayed()`, `isEnabled()`, and `isSelected()` where appropriate.
11. **Form filling:** fill multiple fields and verify their values.
12. **Search or add-to-cart flow:** enter a search term or add an item, then verify the visible result. The exact steps depend on the practice website.

A registration scenario requires a website that actually has a registration form. Choose a suitable practice site before writing that test.

## 7. Suggested Test Script Structure
A typical Selenium test follows this sequence:

1. Create a WebDriver instance.
2. Open the target URL using `driver.get()`.
3. Locate the required elements.
4. Perform actions such as typing or clicking.
5. Assert the expected result.
6. Close the browser session in a `finally` block using `driver.quit()`.

## 8. Practice Websites and Setup Notes
Use a public testing website intended for automation practice. Check its current page structure before relying on example locators or credentials, because public sites can change.

For a Java project, use a JDK, IntelliJ IDEA, Maven, Selenium WebDriver, and a compatible browser. Selenium Manager can manage the browser driver when using `new ChromeDriver()` with a supported Selenium version; a manually maintained `Drivers` folder is not required.

## 9. Completion Checklist
- [ ] Reviewed Selenium WebDriver basics.
- [ ] Demonstrated all eight locator types.
- [ ] Practiced common element actions.
- [ ] Covered text boxes, buttons, checkboxes, radio buttons, dropdowns, links, and images.
- [ ] Created 10 or more separate practice scripts.
- [ ] Reviewed the scripts and verified expected results.
