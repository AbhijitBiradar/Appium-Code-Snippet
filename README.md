# Appium Code Snippet

**Sample Appium Code for Android**

```java 

public class AndroidCalcAppExample {
	WebDriver driver;
	String appiumServiceUrl= “https://127.0.0.1:4723/wd/hub”;
	
	@BeforeTest
	public void setUp() throws MalformedURLException {		
		DesiredCapabilities capabilities = new DesiredCapabilities();
		capabilities.setCapability("deviceName", "8d75c47d");
capabilities.setCapability("udid", "emulator-5554");
		capabilities.setCapability("platformName", "Android");
		capabilities.setCapability("platformVersion", "11.0");
		capabilities.setCapability("appPackage", "com.android.calculator2");
		capabilities.setCapability("appActivity", "com.android.calculator2.Calculator");		
		capabilities.setCapability("automationName" ,"UiAutomator2");
		
		driver = new AndroidDriver<MobileElement>(new URL(appiumServiceUrl), capabilities);
		driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);
	}
}

```

**Sample Appium Code for iOS**

```java 

public class iOSCalcAppExample {
	WebDriver driver;
	String appiumServiceUrl= “https://127.0.0.1:4723/wd/hub”;
	
	@BeforeTest
	public void setUp() throws MalformedURLException {		
		DesiredCapabilities capabilities = new DesiredCapabilities();
		capabilities.setCapability("deviceName", "8d75c47d");
		capabilities.setCapability("udid", "emulator-5554");
		capabilities.setCapability("platformName", "iOS");
		capabilities.setCapability("platformVersion", "11.0");
		capabilities.setCapability("appPackage", "com.ios.calculator2");
		capabilities.setCapability("appActivity", "com.ios.calculator2.Calculator");
		capabilities.setCapability("automationName" ,"XCUITest");
		
		driver = new IOSDriver<MobileElement>(new URL(appiumServiceUrl), capabilities);
		driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);
	}
}

```



Q: Capabilities for Android

DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.setCapability("deviceName", "8d75c47d");
capabilities.setCapability("platformName", "Android");
capabilities.setCapability("appPackage", "com.android.calculator2");
capabilities.setCapability("appActivity", "com.android.calculator2.Calculator");
capabilities.setCapability("udid", "emulator-5554");
capabilities.setCapability("platformVersion", "11.0");

		
Q: Capabilities for iOS

DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.setCapability("deviceName", "8d75c47d");
capabilities.setCapability("platformName", "iOS");
capabilities.setCapability("appPackage", "com.android.calculator2");
capabilities.setCapability("appActivity", "com.android.calculator2.Calculator");
capabilities.setCapability("udid", "emulator-5554");
capabilities.setCapability("platformVersion", "11.0");



Q: Tap By Element

MobileElement element= driver.findElementByAccessibilityId("Login Screen");
TouchAction action = new TouchAction(driver);
action
	.tap(tapOptions()
	.withElement(element(element)))
	.waitAction(waitOptions(ofMillis(250)))
	.perform();
	
  
  
Q: Tap by coordinates
    
TouchAction action = new TouchAction(driver);
action
	.tap(point(100,200))
	.waitAction(waitOptions(ofMillis(250)))
	.perform();
	
  
  
Q: Perform Single Tap

MobileElement element= driver.findElementByAccessibilityId("Login Screen");
TouchActions action = new TouchActions(driver);
action
	.singleTap(element)
	.perform();



Q: Perform Double Tap

MobileElement element= driver.findElementByAccessibilityId("Login Screen");
TouchActions action = new TouchActions(driver);
action
	.doubleTap(element)
	.perform();



Q: Perform touch sequence from one element to another element	

MobileElement element1= driver.findElementByAccessibilityId("Login Screen");
MobileElement element2= driver.findElementByAccessibilityId("Home Screen");
TouchAction action = new TouchAction(driver);
	action.press(element1);
	action.moveTo(element2);
	action.release();
	action.perform();



Q: Perform multi touch sequence containing different elements

MobileElement element1= driver.findElementByAccessibilityId("Login Screen");
MobileElement element2= driver.findElementByAccessibilityId("Home Screen");
MobileElement element3= driver.findElementByAccessibilityId("Invest Screen");
MobileElement element4= driver.findElementByAccessibilityId("Logout Screen");

TouchAction actionOne = new TouchAction(driver);
actionOne.press(element1);
actionOne.moveTo(element2);
actionOne.release();
	
TouchAction actionTwo = new TouchAction(driver);
actionTwo.press(element3);
actionTwo.moveTo(element4);
actionTwo.release();
	
MultiTouchAction action = new MultiTouchAction(driver);
action.add(actionOne);
action.add(actionTwo);
action.perform();



Q: How to hide the keyboard in Appium?
driver.hideKeyboard();



Q: Is there any EventListeners in Appium?
Ans: yes, you can use AppiumWebDriverEventListener . You need to implement this interface.

Example:

public class AppiumListener implements AppiumWebDriverEventListener {
	public void beforeChangeValueOf(WebElement webElement, WebDriver webDriver) {

	}
	public void afterChangeValueOf(WebElement webElement, WebDriver webDriver) {

	}
	public void beforeAlertAccept(WebDriver webDriver) {

	}
	public void afterAlertAccept(WebDriver webDriver) {

	}
	public void afterAlertDismiss(WebDriver webDriver) {

	}
	public void beforeAlertDismiss(WebDriver webDriver) {

	}
	public void beforeNavigateTo(String s, WebDriver webDriver) {

	}
	public void afterNavigateTo(String s, WebDriver webDriver) {

	}

	public void beforeNavigateBack(WebDriver webDriver) {

	}

	public void afterNavigateBack(WebDriver webDriver) {

	}
	public void beforeNavigateForward(WebDriver webDriver) {

	}
	public void afterNavigateForward(WebDriver webDriver) {

	}
	public void beforeNavigateRefresh(WebDriver webDriver) {

	}
	public void afterNavigateRefresh(WebDriver webDriver) {

	}
	public void beforeFindBy(By by, WebElement webElement, WebDriver webDriver) {

	}
	public void afterFindBy(By by, WebElement webElement, WebDriver webDriver) {

	}
	public void beforeClickOn(WebElement webElement, WebDriver webDriver) {

	}
	public void afterClickOn(WebElement webElement, WebDriver webDriver) {

	}
	public void beforeChangeValueOf(WebElement webElement, WebDriver webDriver, CharSequence[] charSequences) {

	}
	public void afterChangeValueOf(WebElement webElement, WebDriver webDriver, CharSequence[] charSequences) {

	}
	public void beforeScript(String s, WebDriver webDriver) {

	}
	public void afterScript(String s, WebDriver webDriver) {

	}
	public void beforeSwitchToWindow(String s, WebDriver webDriver) {

	}
	public void afterSwitchToWindow(String s, WebDriver webDriver) {

	}
	/**
	* will work if there is any exception found in the scripts
	* @param throwable
	* @param webDriver
	*/
	public void onException(Throwable throwable, WebDriver webDriver) {
	   System.out.println("Execute Exception");
	}
	public <X> void beforeGetScreenshotAs(OutputType<X> outputType) {

	}
	public <X> void afterGetScreenshotAs(OutputType<X> outputType, X x) {

	}
	public void beforeGetText(WebElement webElement, WebDriver webDriver) {

	}
	public void afterGetText(WebElement webElement, WebDriver webDriver, String s) {

	}
}



Q: Press by element
TouchAction action = new TouchAction(driver);
action.
	.press(element(element))
	.waitAction(waitOptions(ofSeconds(seconds)))
	.release()
	.perform();




Q: Press by coordinates
TouchAction action = new TouchAction(driver);
action. 
	.press(point(x,y))
	.waitAction(waitOptions(ofSeconds(seconds)))
	.release()
	.perform();




Q: Multitouch action by using an android element
TouchAction action = new TouchAction(driver)
action. 
	.press(element(androidElement))
	.waitAction(waitOptions(ofSeconds(1)))
	.release();

MultiTouchAction multiAction=new MultiTouchAction(driver);
multiAction.
	.add(press)
	.perform();



Q: TouchActions using Screen Coordinates

MobileElement topCharts = driver.findElement(MobileBy.xpath("//android.widget.TextView[@text = 'Top Charts']"));
Point point = topCharts.getLocation();
int startY = point.y;
int endY = point.y;

int startX = (int) ((driver.manage().window().getSize().getWidth()) * 0.80);
int endX = (int) ((driver.manage().window().getSize().getWidth()) * 0.20);

TouchAction actions = new TouchAction(driver);
Actions
.press(startX, startY)
.waitAction(Duration.ofSeconds(2))
.moveTo(endX, endY)
.release()
.perform();

For More Info Refer this:
https://www.automationtestinghub.com/appium-scroll-examples/


Swipe By Co-ordinates
int starty = (int) (size.width * 0.90);
int endx = (int) (size.width * 0.20);
int startx = size.width / 2;
driver.swipe(endx, starty, startx, starty, 1000);  // Swipe from Left to Right.
Thread.sleep(2000);
	
		
Swipe From Element:
MobileElement element = (MobileElement)driver.findElement(By.xpath("//xpath"));
element.swipe(SwipeElementDirection.DOWN, 1000);	
		
MobileElement element = (MobileElement)driver.findElement(By.xpath("//xpath"));
element.swipe(SwipeElementDirection.UP, 1000);	

//Horizontal Swipe by percentages
public void horizontalSwipeByPercentage (double startPercentage, double endPercentage, double anchorPercentage) {
	Dimension size = driver.manage().window().getSize();
	int anchor = (int) (size.height * anchorPercentage);
	int startPoint = (int) (size.width * startPercentage);
	int endPoint = (int) (size.width * endPercentage);
	new TouchAction(driver)
		.press(point(startPoint, anchor))
		.waitAction(waitOptions(ofMillis(1000)))
		.moveTo(point(endPoint, anchor))
		.release().perform();
}



Q: Vertical Swipe by percentages
public void verticalSwipeByPercentages(double startPercentage, double endPercentage, double anchorPercentage) {
	Dimension size = driver.manage().window().getSize();
	int anchor = (int) (size.width * anchorPercentage);
	int startPoint = (int) (size.height * startPercentage);
	int endPoint = (int) (size.height * endPercentage);
	new TouchAction(driver)
		.press(point(anchor, startPoint))
		.waitAction(waitOptions(ofMillis(1000)))
		.moveTo(point(anchor, endPoint))
		.release().perform();
}


Q: Swipe by elements
public void swipeByElements (AndroidElement startElement, AndroidElement endElement) {
	int startX = startElement.getLocation().getX() + (startElement.getSize().getWidth() / 2);
	int startY = startElement.getLocation().getY() + (startElement.getSize().getHeight() / 2);
	int endX = endElement.getLocation().getX() + (endElement.getSize().getWidth() / 2);
	int endY = endElement.getLocation().getY() + (endElement.getSize().getHeight() / 2);
	new TouchAction(driver)
		.press(point(startX,startY))
		.waitAction(waitOptions(ofMillis(1000)))
		.moveTo(point(endX, endY))
		.release().perform();
}
    
		
