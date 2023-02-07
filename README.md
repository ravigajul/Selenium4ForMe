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

## Click on a SVG element 
```java
driver.get("https://petdiseasealerts.org/forecast-map/");
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(10,TimeUnit.SECONDS);
JavascriptExecutor js = (JavascriptExecutor) driver;
String state= (String) js.executeScript("return document.readyState");
if (state.equalsIgnoreCase("complete")){
	driver.switchTo().frame(driver.findElement(By.cssSelector("iframe[src*='iframe']")));
	WebElement eleCalifornia = driver.findElement(By.cssSelector("g#california"));
	js.executeScript("arguments[0].scrollIntoView(true);", eleCalifornia);
	eleCalifornia.click();
}else {
	System.out.println("The page is not fully loaded.");
	}
```
## Checking the ready state of a web page
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
String state= (String) js.executeScript("return document.readyState");
if (state.equalsIgnoreCase("complete")){
//do something
}
```
