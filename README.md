# Selenium4ForMe

## Relative Locators Syntax
```java
By emailLocator = RelativeLocator.with(By.tagName("input")).above(By.id("password"));
or
By emailLocator = driver.findElement(with(By.tagName("input"))).above(By.id("password"));
```
