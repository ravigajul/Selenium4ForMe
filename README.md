# Selenium4ForMe

## Relative Locators Syntax
Above, below, toLeftOf, toRightOf
```java
    By emailLocator = RelativeLocator.with(By.tagName("input")).above(By.id("password"));
    or
    By emailLocator = driver.findElement(with(By.tagName("input"))).above(By.id("password"));
```

## Invoke multiple windows
```java
driver.get("https://www.google.com");
//Switch to new windows
driver.switchTo().newWindow(WindowType.WINDOW);
//swtich to new tab
driver.switchTo().newWindow(WindowType.TAB);
Set<String> windowHandles= driver.getWindowHandles();
Iterator it = windowHandles.iterator();
String parentWindowId=(String) it.next();
String childWindowId=(String) it.next();
driver.switchTo().window(childWindowId);
```

## Screenshot of WebElement
```java
//Getscreenshot of element
File screenshotFile=driver.findElement(By.cssSelector("img.lnXdpd")).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(screenshotFile, new File("logo.png"));
```
## Capturing Height & Width of element
```java
//get Height & Width
int height=driver.findElement(By.cssSelector("img.lnXdpd")).getRect().getHeight();
int width=driver.findElement(By.cssSelector("img.lnXdpd")).getRect().getWidth();
System.out.println(height + "-->" + width);
```
