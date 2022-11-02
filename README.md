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



**Capabilities for Android**

```java 

DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.setCapability("deviceName", "8d75c47d");
capabilities.setCapability("platformName", "Android");
capabilities.setCapability("appPackage", "com.android.calculator2");
capabilities.setCapability("appActivity", "com.android.calculator2.Calculator");
capabilities.setCapability("udid", "emulator-5554");
capabilities.setCapability("platformVersion", "11.0");

```
		
**Capabilities for iOS**

```java 

DesiredCapabilities capabilities = new DesiredCapabilities();
capabilities.setCapability("deviceName", "8d75c47d");
capabilities.setCapability("platformName", "iOS");
capabilities.setCapability("appPackage", "com.android.calculator2");
capabilities.setCapability("appActivity", "com.android.calculator2.Calculator");
capabilities.setCapability("udid", "emulator-5554");
capabilities.setCapability("platformVersion", "11.0");

```

**Tap By Element**

```java

MobileElement element= driver.findElementByAccessibilityId("Login Screen");
TouchAction action = new TouchAction(driver);
action
	.tap(tapOptions()
	.withElement(element(element)))
	.waitAction(waitOptions(ofMillis(250)))
	.perform();
	
```  
  
**Tap by coordinates**

```java

TouchAction action = new TouchAction(driver);
action
	.tap(point(100,200))
	.waitAction(waitOptions(ofMillis(250)))
	.perform();
	
```  
  
**Perform Single Tap**

```java

MobileElement element= driver.findElementByAccessibilityId("Login Screen");
TouchActions action = new TouchActions(driver);
action
	.singleTap(element)
	.perform();

```

**Perform Double Tap**

```java

MobileElement element= driver.findElementByAccessibilityId("Login Screen");
TouchActions action = new TouchActions(driver);
action
	.doubleTap(element)
	.perform();

```

**Perform touch sequence from one element to another element**

```java

MobileElement element1= driver.findElementByAccessibilityId("Login Screen");
MobileElement element2= driver.findElementByAccessibilityId("Home Screen");
TouchAction action = new TouchAction(driver);
	action.press(element1);
	action.moveTo(element2);
	action.release();
	action.perform();

```

**Perform multi touch sequence containing different elements**

```java

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

```

**hide the keyboard in Appium**

```java

driver.hideKeyboard();

```



**AppiumWebDriverEventListener interface**

```java 

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

```


**Press by element**

```java 

TouchAction action = new TouchAction(driver);
action.
	.press(element(element))
	.waitAction(waitOptions(ofSeconds(seconds)))
	.release()
	.perform();

```


**Press by coordinates**

```java 

TouchAction action = new TouchAction(driver);
action. 
	.press(point(x,y))
	.waitAction(waitOptions(ofSeconds(seconds)))
	.release()
	.perform();

```


**Multitouch action by using an android element**

```java 

TouchAction action = new TouchAction(driver)
action. 
	.press(element(androidElement))
	.waitAction(waitOptions(ofSeconds(1)))
	.release();

MultiTouchAction multiAction=new MultiTouchAction(driver);
multiAction.
	.add(press)
	.perform();

```

**TouchActions using Screen Coordinates**

```java 

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

```

**Swipe By Co-ordinates**

```java 

int starty = (int) (size.width * 0.90);
int endx = (int) (size.width * 0.20);
int startx = size.width / 2;
driver.swipe(endx, starty, startx, starty, 1000);  // Swipe from Left to Right.
Thread.sleep(2000);
	
```

**Swipe From Element:**

```java 

MobileElement element = (MobileElement)driver.findElement(By.xpath("//xpath"));
element.swipe(SwipeElementDirection.DOWN, 1000);	
		
MobileElement element = (MobileElement)driver.findElement(By.xpath("//xpath"));
element.swipe(SwipeElementDirection.UP, 1000);	

```

**Horizontal Swipe by percentages**

```java 

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

```


**Vertical Swipe by percentages**

```java 

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

```

**Swipe by elements**

```java 
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
    
```		


**Status**

```java 

Retrieve the server’s current status
driver.getStatus();
	
Reference: https://appium.io/docs/en/commands/status/index.html
	
```	
	
**Execute Mobile Command**

```java 

Execute a native mobile command
driver.executeScript("mobile: scroll", ImmutableMap.of("direction", "down"));
	
Reference: https://appium.io/docs/en/commands/mobile-command/index.html
	
```	


# Session related commands

**Create a new session**
	
```java 
	
DesiredCapabilities desiredCapabilities = new DesiredCapabilities();
desiredCapabilities.setCapability(MobileCapabilityType.PLATFORM_VERSION, "10.3");
desiredCapabilities.setCapability(MobileCapabilityType.DEVICE_NAME, "iPhone Simulator");
desiredCapabilities.setCapability(MobileCapabilityType.AUTOMATION_NAME, "XCUITest");
desiredCapabilities.setCapability(MobileCapabilityType.APP, "/path/to/ios/app.zip");

URL url = new URL("http://127.0.0.1:4723/wd/hub");

IOSDriver driver = new IOSDriver(url, desiredCapabilities);
String sessionId = driver.getSessionId().toString();
	
Reference:  https://appium.io/docs/en/commands/session/create/index.html
	
```

**End Session**

```java 

End the running session
driver.quit();
	
Reference: https://appium.io/docs/en/commands/session/delete/index.html
	
```
	

**Get Session Capabilities**

```java 
	Retrieve the capabilities of the specified session
	Map<String, Object> caps = driver.getSessionDetails();
	
	Reference: https://appium.io/docs/en/commands/session/get/index.html
		
```
	
**Go Back**

```java 
	Navigate backwards in the browser history, if possible (Web context only)
	driver.back();

	Reference: https://appium.io/docs/en/commands/session/back/index.html
		
```
	
**Take Screenshot**

```java 
	Take a screenshot of the current viewport/window/page
	File scrFile = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
	
	Reference: https://appium.io/docs/en/commands/session/screenshot/index.html
		
```
	
**Get Page Source**

```java 
	Get the current application hierarchy XML (app) or page source (web)
	String pageSource = driver.getPageSource();

	Reference: https://appium.io/docs/en/commands/session/source/index.html
		
```
	
**Set Timeouts**

```java 
	Configure the amount of time that a particular type of operation can execute for before they are aborted
	driver.manage().timeouts().pageLoadTimeout(30, TimeUnit.SECONDS);
	
	Reference: https://appium.io/docs/en/commands/session/timeouts/timeouts/index.html
		
```
	
**Set Implicit Wait Timeout**

```java 
	Set the amount of time the driver should wait when searching for elements	
	driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
	
	Reference: https://appium.io/docs/en/commands/session/timeouts/implicit-wait/index.html
		
```
	
**Set Script Timeout**

```java 
	Set the amount of time, in milliseconds, that asynchronous scripts executed by execute async are permitted to run before they are aborted (Web context only)
	driver.manage().timeouts().setScriptTimeout(30, TimeUnit.SECONDS);

	Reference: https://appium.io/docs/en/commands/session/timeouts/async-script/index.html
	
```

**Get Orientation**

```java 
	Get the current device/browser orientation
	ScreenOrientation orientation = driver.getOrientation();
	
	Reference: https://appium.io/docs/en/commands/session/orientation/get-orientation/index.html
		
```
	
**Set Orientation**

```java 
	Set the current device/browser orientation
	driver.rotate(ScreenOrientation.LANDSCAPE);
	
	Reference: https://appium.io/docs/en/commands/session/orientation/set-orientation/index.html
		
```
	
**Get Geolocation**

```java 
	Get the current geo location
	Location location = driver.location(); // Must be a driver that implements LocationContext
	
	Reference: https://appium.io/docs/en/commands/session/geolocation/get-geolocation/index.html
	
```

Set Geolocation

```java 

	Set the current geo location
	driver.setLocation(new Location(49, 123, 10)); // Must be a driver that implements LocationContext
	
	Reference: https://appium.io/docs/en/commands/session/geolocation/set-geolocation/index.html
	
```

	
Get available log types 

```java 
	
	Get available log types as a list of strings
	Set<String> logTypes = driver.manage().logs().getAvailableLogTypes();
	
	Reference: https://appium.io/docs/en/commands/session/logs/get-log-types/index.html

```


Get Logs

```java 
	
	Get the log for a given log type. Log buffer is reset after each request
	LogEntries logEntries = driver.manage().logs().get("driver");
	
	Reference: https://appium.io/docs/en/commands/session/logs/get-log/index.html

```


Log event

```java 
	
	Store a custom event
	
	CustomEvent evt = new CustomEvent();
	evt.setEventName("funEvent");
	evt.setVendor("appium");
	driver.logEvent(evt);

	Reference: https://appium.io/docs/en/commands/session/events/log-event/index.html

```


Get events

```java 
	
	Get events stored in appium server
	driver.getEvents();

	Reference: https://appium.io/docs/en/commands/session/events/get-events/index.html

```


Update Device Settings

```java 
	
	Update the current setting on the device
	driver.setSetting(Setting.WAIT_FOR_IDLE_TIMEOUT, 5000);
	
	Reference: https://appium.io/docs/en/commands/session/settings/update-settings/index.html

```


Retrieve Device Settings

```java 
	
	Retrieve the current settings on the device
	Map<String, Object> settings = driver.getSettings();
	
	Reference : https://appium.io/docs/en/commands/session/settings/get-settings/index.html

```


Execute Driver Script

```java 
	
	Run a WebdriverIO script against the current session, allowing execution of many commands in one Appium request.	
	String script = "const el = await driver.$('~foo');\n"
				  + "await el.click();"
	driver.executeDriverScript(script, new ScriptOptions().withTimeout(200));
	
	Reference : https://appium.io/docs/en/commands/session/execute-driver/index.html	

```


Start Activity

```java 
	
	Start an Android activity by providing package name and activity name
	driver.startActivity(new Activity("com.example", "ActivityName"));
	
	Reference: https://appium.io/docs/en/commands/device/activity/start-activity/index.html

```


Get Current Activity

```java 
	
	Get the name of the current Android activity
	String activity = driver.currentActivity();
	
	Reference: https://appium.io/docs/en/commands/device/activity/current-activity/index.html
	
```

	
Get Current Package

```java 
	
	Get the name of the current Android package
	String package = driver.getCurrentPackage();
	
	Reference: https://appium.io/docs/en/commands/device/activity/current-package/index.html

```


Install App

```java 
	
	Install the given app onto the device
	driver.installApp("/Users/johndoe/path/to/app.apk");
	
	Reference: https://appium.io/docs/en/commands/device/app/install-app/index.html

```

	
Is App Installed

```java 
	
	Check whether the specified app is installed on the device
	driver.isAppInstalled("com.example.AppName");
	
	Reference: https://appium.io/docs/en/commands/device/app/is-app-installed/index.html

```


Launch App

```java 
	
	Launch the app-under-test on the device
	driver.launchApp();
	
	Reference: https://appium.io/docs/en/commands/device/app/launch-app/index.html
	
```

	
Background App

```java 
	
	Send the currently running app for this session to the background
	driver.runAppInBackground(Duration.ofSeconds(10));
	
	Reference: https://appium.io/docs/en/commands/device/app/background-app/index.html
	
```


Close an App

```java 
	
	Close an app on device
	driver.closeApp();
	
	Reference: https://appium.io/docs/en/commands/device/app/close-app/index.html

```

	
Reset App

```java 
	
	Reset the currently running app for this session
	driver.resetApp();
	
	Reference: https://appium.io/docs/en/commands/device/app/reset-app/index.html

```

	
Remove App

```java 
	
	Remove an app from the device
	driver.removeApp("com.example.AppName");
	
	Reference: https://appium.io/docs/en/commands/device/app/remove-app/index.html

```

	
Activate App

```java 
	
	Activate the given app onto the device
	driver.activateApp('com.apple.PReferences');
	driver.activateApp('io.appium.android.apis');
	
	Reference: https://appium.io/docs/en/commands/device/app/activate-app/index.html

```

	
Terminate App

```java 
	
	Terminate the given app on the device
	driver.terminateApp('com.apple.PReferences');
	driver.terminateApp('io.appium.android.apis');
	
	Reference: https://appium.io/docs/en/commands/device/app/terminate-app/index.html
	
```

	
Get app state

```java 
	
	Get the given app status on the device
	driver.queryAppState('com.apple.PReferences');
	driver.queryAppState('io.appium.android.apis');
	
	Reference: https://appium.io/docs/en/commands/device/app/app-state/index.html

```

	
Get App Strings

```java 
	
	Get app strings
	Map<String, String> appStrings = driver.getAppStringMap("en", "/path/to/file");
	
	Reference: https://appium.io/docs/en/commands/device/app/get-app-strings/index.html

```

	
End Test Coverage

```java 
	
	Get test coverage data
	driver.endTestCoverage("Intent", "/path");
	
	https://appium.io/docs/en/commands/device/app/end-test-coverage/index.html
	
```

	
Get Clipboard

```java 
	
	Get the content of the system clipboard
	driver.getClipboard(ClipboardContentType.PLAINTEXT); // get plaintext
	driver.getClipboardText();
	
	Reference: https://appium.io/docs/en/commands/device/clipboard/get-clipboard/index.html

```

	
Set Clipboard

```java 
	
	Set the content of the system clipboard
	// base64Content is Base64-encoded content
	driver.setClipboard("label", ClipboardContentType.PLAINTEXT, base64Content);
	driver.setClipboardText("happy testing");
	
	Reference: https://appium.io/docs/en/commands/device/clipboard/set-clipboard/index.html

```

	
Emulate power state

```java 
	
	Emulate power state change on the connected emulator.
	driver.setPowerAC(PowerACState.OFF);
	
	Reference: https://appium.io/docs/en/commands/device/emulator/power_ac/index.html
	
```

	
Emulate power capacity

```java 
	
	Emulate power capacity change on the connected emulator.
	driver.setPowerCapacity(100);
	
	Reference: https://appium.io/docs/en/commands/device/emulator/power_capacity/index.html
	
```

	
Push File

```java 
	
	Place a file onto the device in a particular place
	driver.pushFile("/data/local/tmp/foo.bar", new File("/Users/johndoe/files/foo.bar"));
	
	Reference: https://appium.io/docs/en/commands/device/files/push-file/index.html
	
```

	
Pull File

```java 
	
	Retrieve a file from the device's file system
	byte[] fileBase64 = driver.pullFile("/path/to/device/foo.bar");
	
	Reference: https://appium.io/docs/en/commands/device/files/pull-file/index.html
	
```


Pull Folder

```java 
	
	Retrieve a folder from the device's file system
	byte[] folder = driver.pullFolder("/path/to/device/foo.bar");
	
	Reference: https://appium.io/docs/en/commands/device/files/pull-folder/index.html
	
```


Shake

```java 
	
	Perform a shake action on the device
	driver.shake();
	
	Reference: https://appium.io/docs/en/commands/device/interactions/shake/index.html

```

	
Lock

```java 
	
	Lock the device
	driver.lockDevice();
	
	Reference: https://appium.io/docs/en/commands/device/interactions/lock/index.html
	
```


Unlock

```java 
	
	Unlock the device	
	driver.lockDevice();
	driver.unlockDevice();
	
	Reference: https://appium.io/docs/en/commands/device/interactions/unlock/index.html

```



Is Device Locked

```java 
	
	Check whether the device is locked or not
	boolean isLocked = driver.isDeviceLocked();
	
	Reference: https://appium.io/docs/en/commands/device/interactions/is-locked/index.html
	
```


Rotate

```java 
	
	Rotate the device in three dimensions
	driver.rotate(new DeviceRotation(10, 10, 10));
	
	Reference: https://appium.io/docs/en/commands/device/interactions/rotate/index.html

```

	
Press Key Code

```java 
	
	Press a particular key on an Android Device
	driver.pressKeyCode(AndroidKeyCode.SPACE, AndroidKeyMetastate.META_SHIFT_ON);
	
	Reference: https://appium.io/docs/en/commands/device/keys/press-keycode/index.html

```


Long Press Key Code

```java 
	
	Press and hold a particular key code on an Android device
	driver.longPressKeyCode(AndroidKeyCode.HOME);
	
	Reference: https://appium.io/docs/en/commands/device/keys/long-press-keycode/index.html

```


Hide Keyboard

```java 
	
	Hide soft keyboard
	driver.hideKeyboard();
	
	Reference: https://appium.io/docs/en/commands/device/keys/hide-keyboard/index.html

```


Is Keyboard Shown

```java 
	
	Whether or not the soft keyboard is shown
	boolean isKeyboardShown = driver.isKeyboardShown();
	
	Reference: https://appium.io/docs/en/commands/device/keys/is-keyboard-shown/index.html

```



Toggle Airplane Mode

```java 
	
	Toggle airplane mode on device
	driver.toggleAirplaneMode();
	
	Reference: https://appium.io/docs/en/commands/device/network/toggle-airplane-mode/index.html

```


Toggle Data

```java 
	
	Switch the state of data service
	driver.toggleData();
	
	Reference: https://appium.io/docs/en/commands/device/network/toggle-data/index.html

```


Toggle WiFi

```java 
	
	Switch the state of the WiFi service
	driver.toggleWifi();
	
	Reference: https://appium.io/docs/en/commands/device/network/toggle-wifi/index.html

```

Toggle Location Services

```java 
	
	Switch the state of the location service
	driver.toggleLocationServices();
	
	Reference: https://appium.io/docs/en/commands/device/network/toggle-location-services/index.html

```


Send SMS

```java 
	
	Simulate an SMS message (Emulator only)
	driver.sendSMS("555-123-4567", "Hey lol");
	
	Reference: https://appium.io/docs/en/commands/device/network/send-sms/index.html

```


GSM Call

```java 
	
	Make GSM call (Emulator only)
	driver.makeGsmCall("5551234567", GsmCallActions.CALL);
	
	Reference: https://appium.io/docs/en/commands/device/network/gsm-call/index.html

```



GSM Signal

```java 
	
	Set GSM signal strength (Emulator only)
	driver.setGsmSignalStrength(GsmSignalStrength.GOOD);
	
	Reference: https://appium.io/docs/en/commands/device/network/gsm-signal/index.html

```


GSM Voice

```java 
	
	Set GSM voice state (Emulator only)
	driver.setGsmVoice(GsmVoiceState.HOME);
	
	Reference: https://appium.io/docs/en/commands/device/network/gsm-voice/index.html

```


Network speed

```java 
	
	Set network speed (Emulator only)
	driver.setNetworkSpeed(NetworkSpeed.LTE);
	
	Reference: https://appium.io/docs/en/commands/device/network/network-speed/index.html

```


Get Performance Data

```java 
	
	Returns the information of the system state which is supported to read as like cpu, memory, network traffic, and battery
	List<List<Object>> performanceData = driver.getPerformanceData("my.app.package", "cpuinfo", 5);
	
	Reference: https://appium.io/docs/en/commands/device/performance-data/get-performance-data/index.html

```


Get Performance Data Types

```java 
	
	Returns the information types of the system state which is supported to read as like cpu, memory, network traffic, and battery
	List<String> performanceTypes = driver.getSupportedPerformanceDataTypes();
	
	Reference: https://appium.io/docs/en/commands/device/performance-data/performance-data-types/index.html

```


Start Recording Screen

```java 
	
	Start recording screen
	driver.startRecordingScreen();
	driver.startRecordingScreen(new BaseStartScreenRecordingOptions(....));
	
	Reference: https://appium.io/docs/en/commands/device/recording-screen/start-recording-screen/index.html

```


Stop Recording Screen

```java 
	
	Stop recording screen
	driver.stopRecordingScreen();
	driver.stopRecordingScreen(new BaseStopScreenRecordingOptions(....));
	
	Reference: https://appium.io/docs/en/commands/device/recording-screen/stop-recording-screen/index.html

```


Perform Touch ID

```java 
	
	Simulate a touch id event (iOS Simulator only)
	driver.performTouchID(false); // Simulates a failed touch
	driver.performTouchID(true); // Simulates a passing touch
	
	Reference: https://appium.io/docs/en/commands/device/simulator/touch-id/index.html

```


Toggle Touch ID Enrollment

```java 
	
	Toggle the simulator being enrolled to accept touchId (iOS Simulator only)
	driver.toggleTouchIDEnrollment(true);
	
	Reference: https://appium.io/docs/en/commands/device/simulator/toggle-touch-id-enrollment/index.html

```


Open Notifications

```java 
	
	Open Android notifications (Emulator only)
	driver.openNotifications();
	
	Reference: https://appium.io/docs/en/commands/device/system/open-notifications/index.html

```


Get System Bars

```java 
	
	Retrieve visibility and bounds information of the status and navigation bars
	Map<String, String> systemBars = driver.getSystemBars();
	
	Reference: https://appium.io/docs/en/commands/device/system/system-bars/index.html

```


Get System Time

```java 
	
	Get the time on the device
	String time = driver.getDeviceTime();
	
	Reference: https://appium.io/docs/en/commands/device/system/system-time/index.html

```


Get Display Density

```java 
	
	Retrieve display density(dpi) of the Android device
	driver.getDeviceDensity();
	
	Reference: https://appium.io/docs/en/commands/device/system/display-density/index.html

```


Finger print

```java 
	
	Authenticate users by using their finger print scans on supported emulators.
	driver.fingerPrint(1);
	
	Reference: https://appium.io/docs/en/commands/device/authentication/finger-print/index.html
 
```


4) Element related Commands

Find Element

```java 
	Search for an element on the page
	MobileElement elementOne = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	MobileElement elementTwo = (MobileElement) driver.findElementByClassName("SomeClassName");
	
	Reference: https://appium.io/docs/en/commands/element/find-element/index.html

```


Find Elements

```java 
	Search for multiple elements
	List<MobileElement> elementsOne = (List<MobileElement>) driver.findElementsByAccessibilityId("SomeAccessibilityID");
	List<MobileElement> elementsTwo = (List<MobileElement>) driver.findElementsByClassName("SomeClassName");
	
	Reference: https://appium.io/docs/en/commands/element/find-elements/index.html

```


Click

```java 
	Click element at its center point.
	MobileElement el = driver.findElementByAccessibilityId("SomeId");
	el.click();
	
	Reference: https://appium.io/docs/en/commands/element/actions/click/index.html

```


Send Keys

```java 
	Send a sequence of key strokes to an element
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	element.sendKeys("Hello world!");
	
	Reference: https://appium.io/docs/en/commands/element/actions/send-keys/index.html

```


Clear Element

```java 
	Clear an element's value
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	element.clear();
	
	https://appium.io/docs/en/commands/element/actions/clear/index.html

```


Get Element Text

```java 
	Returns visible text for element
	MobileElement element = (MobileElement) driver.findElementByClassName("SomeClassName");
	String elText = element.getText();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/text/index.html

```


Get Tag Name

```java 
	Get an element's tag name
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	String tagName = element.getTagName();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/name/index.html

```


Get Element Attribute

```java 
	Get the value of an element's attribute
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	String tagName = element.getAttribute("content-desc");
	
	Reference: https://appium.io/docs/en/commands/element/attributes/attribute/index.html

```


Is Element Selected

```java 
	Determine if a form or form-like element (checkbox, select, etc...) is selected
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	boolean isSelected = element.isSelected();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/selected/index.html

```


Is Element Enabled

```java 
	Determine if an element is currently enabled
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	boolean isEnabled = element.isEnabled();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/enabled/index.html

```


Is Element Displayed

```java 
	Determine if an element is currently displayed
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	boolean isDisplayed = element.isDisplayed();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/displayed/index.html

```


Get Element Location

```java 
	Determine an element's location on the page or screen
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	Point location = element.getLocation();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/location/index.html

```

Get Element Size

```java 
	Determine an element's size in pixels
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	Dimension elementSize = element.getSize();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/size/index.html

```


Get Element Rect

```java 
	Gets dimensions and coordinates of an element
	MobileElement element = (MobileElement) driver.findElementByAccessibilityId("SomeAccessibilityID");
	Rectangle rect = element.getRect();
	
	Reference: https://appium.io/docs/en/commands/element/attributes/rect/index.html

```


Get Element CSS Value

```java 
	Query the value of a web element's computed CSS property
	MobileElement element = (MobileElement) driver.findElementById("SomeId");
	String cssProperty = element.getCssValue("style");
	
	Reference: https://appium.io/docs/en/commands/element/attributes/css-property/index.html

```


Submit Form

```java 
	Submit a FORM element
	MobileElement element = (MobileElement) driver.findElementByClassName("SomeClassName");
	element.submit();
	
	Reference: https://appium.io/docs/en/commands/element/other/submit/index.html

```


Get Active Element

```java 
	Gets the active element of the current session
	WebElement currentElement = driver.switchTo().activeElement();
	
	Reference: https://appium.io/docs/en/commands/element/other/active/index.html

```



Are Elements Equal

```java 
	Test if two element IDs refer to the same element
	// Overrides the Java Object .equals method
	MobileElement elementOne = (MobileElement) driver.findElementByClassName("SomeClassName");
	MobileElement elementTwo = (MobileElement) driver.findElementByClassName("SomeOtherClassName");
	boolean isEqual = elementOne.equals(elementTwo);
	
	Reference: https://appium.io/docs/en/commands/element/other/equals-element/index.html
 
```


6) Context related commands

Get Current Context

```java 
	Get the current context in which Appium is running
	String context = driver.getContext();
	
	Reference: https://appium.io/docs/en/commands/context/get-context/index.html

```

Get All Contexts

```java 
	Get all the contexts available to automate
	Set<String> contextNames = driver.getContextHandles();
	
	Reference: https://appium.io/docs/en/commands/context/get-contexts/index.html

```


Set Current Context

```java 
	Set the context being automated
	Set<String> contextNames = driver.getContextHandles();
	driver.context(contextNames.toArray()[1]);
	// ...
	driver.context("NATIVE_APP");

	Reference: https://appium.io/docs/en/commands/context/set-context/index.html

```


Move Mouse To

```java 
	Move the mouse by an offset of the specificed element
	Actions action = new Actions(driver);
	action.moveTo(element, 10, 10);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/mouse/moveto/index.html
	
```

	
Click

```java 
	Click any mouse button at the current mouse coordinates
	Actions action = new Actions(driver);
	action.moveTo(element);
	action.click();
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/mouse/click/index.html

```


Double Click

```java 
	Double-clicks at the current mouse coordinates (set by moveto).
	Actions action = new Actions(driver);
	action.moveTo(element);
	action.doubleClick();
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/mouse/doubleclick/index.html

```


Button Down

```java 
	Click and hold the left mouse button at the current mouse coordinates
	Actions action = new Actions(driver);
	action.moveTo(element);
	action.clickAndHold();
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/mouse/button-down/index.html

```


Button Up

```java 
	Releases the mouse button previously held
	Actions action = new Actions(driver);
	action.moveTo(element);
	action.clickAndHold();
	action.moveTo(element, 10, 10);
	action.release();
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/mouse/button-up/index.html

```



Tap

```java 
	Single tap on the touch enabled device
	TouchActions action = new TouchActions(driver);
	action.singleTap(element);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/tap/index.html

```

Double Tap

```java 
	Double tap on the touch screen using finger motion events
	TouchActions action = new TouchActions(driver);
	action.doubleTap(element);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/double-tap/index.html

```


Move To

```java 
	Finger move on the screen
	TouchActions action = new TouchActions(driver);
	action.down(10, 10);
	action.moveTo(50, 50);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/move/index.html

```


Touch Down

```java 
	Finger down on the screen
	TouchActions action = new TouchActions(driver);
	action.down(10, 10);
	action.move(50, 50);
	action.perform();

	Reference: https://appium.io/docs/en/commands/interactions/touch/touch-down/index.html

```


Touch Up

```java 
	Finger up on the screen
	TouchActions action = new TouchActions(driver);
	action.down(10, 10);
	action.up(20, 20);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/touch-up/index.html

```


Long Tap

```java 
	Long press on the touch screen using finger motion events
	TouchActions action = new TouchActions(driver);
	action.longPress(element);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/long-press/index.html

```


Scroll

```java 
	Scroll on the touch screen using finger based motion events
	TouchActions action = new TouchActions(driver);
	action.scroll(element, 10, 100);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/scroll/index.html

```

Flick

```java 
	Flick on the touch screen using finger motion events
	TouchActions action = new TouchActions(driver);
	action.flick(element, 1, 10, 10);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/flick/index.html

```


Multi Touch Perform

```java 
	Perform a multi touch action sequence
	TouchActions actionOne = new TouchAction();
	actionOne.press(10, 10);
	actionOne.moveTo(10, 100);
	actionOne.release();
	TouchActions actionTwo = new TouchAction();
	actionTwo.press(20, 20);
	actionTwo.moveTo(20, 200);
	actionTwo.release();
	MultiTouchAction action = new MultiTouchAction();
	action.add(actionOne);
	action.add(actionTwo);
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/multi-touch-perform/index.html

```


Touch Perform

```java 
	Perform a touch action sequence
	TouchAction action = new TouchAction(driver);
	action.press(10, 10);
	action.moveTo(10, 100);
	action.release();
	action.perform();
	
	Reference: https://appium.io/docs/en/commands/interactions/touch/touch-perform/index.html

```


Actions

```java 
	Perform a chain or multiple chains of keyboard and pointer (touch, mouse, stylus) actions
	WebElement source = (MobileElement) driver.findElementsByAccessibilityId("SomeAccessibilityID");
	WebElement target = (MobileElement) driver.findElementsByAccessibilityId("SomeOtherAccessibilityID");

	Point source = dragMe.getCenter();
	Point target = driver.findElementByAccessibilityId("dropzone").getCenter();
	PointerInput finger = new PointerInput(PointerInput.Kind.TOUCH, "finger");
	Sequence dragNDrop = new Sequence(finger, 1);
	dragNDrop.addAction(finger.createPointerMove(Duration.ofMillis(0),
						PointerInput.Origin.viewport(), source.x, source.y));
	dragNDrop.addAction(finger.createPointerDown(PointerInput.MouseButton.LEFT.asArg()));
	dragNDrop.addAction(finger.createPointerMove(Duration.ofMillis(700),
						PointerInput.Origin.viewport(),target.x, target.y));
	dragNDrop.addAction(finger.createPointerUp(PointerInput.MouseButton.LEFT.asArg()));
	driver.perform(Arrays.asList(dragNDrop));
	
	Reference: https://appium.io/docs/en/commands/interactions/actions/index.html

```

--------------------------------------------------------------------------------------------------------------------------------

8) Web related commands

Switch to Window

```java
	Change focus to another window (Web context only)
	driver.switchTo().window("handle");
	
	Reference: https://appium.io/docs/en/commands/web/window/set-window/index.html

```


Close Window

```java
	Close the current window (Web context only)
	driver.close();
	
	Reference: https://appium.io/docs/en/commands/web/window/close-window/index.html

```


Get Window Handle

```java
	Retrieve the current window handle (Web context only)
	String windowHandle = driver.getWindowHandle();
	
	Reference: https://appium.io/docs/en/commands/web/window/get-handle/index.html

```


Get Window Handles

```java
	Retrieve the list of all window handles available to the session (Web context only)
	Set<String> windowHandles = driver.getWindowHandles();

```


Get Title

```java
	Get the current page title (Web context only)
	String title = driver.getTitle();
	
	Reference: https://appium.io/docs/en/commands/web/window/title/index.html

```


Get Window Size

```java
	Get the size of the specified window (Web context only)
	Dimension windowSize = driver.manage().window().getSize();
	
	Reference: https://appium.io/docs/en/commands/web/window/get-window-size/index.html

```



Set Window Size

```java
	Change the size of the specified window (Web context only)
	driver.manage().window().setSize(new Dimension(10, 10));
	
	Reference: https://appium.io/docs/en/commands/web/window/set-window-size/index.html

```


Get Window Position

```java
	Get the position of the specified window (Web context only)
	Point windowPosition = driver.manage().window().getPosition();
	
	Reference: https://appium.io/docs/en/commands/web/window/get-window-position/index.html

```


Set Window Position

```java
	Change the position of the specified window (Web context only)
	driver.manage().window().setPosition(new Dimension(10, 10));
	
	Reference: https://appium.io/docs/en/commands/web/window/set-window-position/index.html

```


Maximize Window

```java
	Maximize the specified window (Web context only)
	driver.manage().window().maximize();
	
	Reference: https://appium.io/docs/en/commands/web/window/maximize-window/index.html

```


Go to URL

```java
	Navigate to a new URL (Web context) or open an Appium deep link (Native)
	driver.get("http://appium.io/");
	
	Reference: https://appium.io/docs/en/commands/web/navigation/go-to-url/index.html

```


Get URL

```java
	Retrieve the URL of the current page (Web context only)
	String url = driver.getCurrentUrl();
	
	Reference: https://appium.io/docs/en/commands/web/navigation/url/index.html

```


Go Back

```java
	Navigate backwards in the browser history, if possible (Web context only)
	driver.back();
	
	Reference: https://appium.io/docs/en/commands/web/navigation/back/index.html

```


Go Forward

```java
	Navigate forwards in the browser history, if possible (Web context only)
	driver.forward();
	
	Reference: https://appium.io/docs/en/commands/web/navigation/forward/index.html

```


Refresh

```java
	Refresh the current page. (Web context only)
	driver.refresh();
	
	Reference: https://appium.io/docs/en/commands/web/navigation/refresh/index.html

```


Get All Cookies

```java
	Retrieve all cookies visible to the current page (Web context only)
	Set<Cookie> allcookies = driver.manage().getCookies();
	
	Reference: https://appium.io/docs/en/commands/web/storage/get-all-cookies/index.html

```


Set Cookie

```java
	Set a cookie (Web context only)
	driver.manage().addCookie(new Cookie("foo", "bar"));
	
	Reference: https://appium.io/docs/en/commands/web/storage/set-cookie/index.html

```


Delete Cookie

```java
	Delete the cookie with the given name (Web context only)
	driver.manage().deleteCookieNamed("cookie_name");
	
	Reference: https://appium.io/docs/en/commands/web/storage/delete-cookie/index.html

```




Delete All Cookies

```java
	Delete all cookies visible to current page (Web context only)
	driver.manage().deleteAllCookies();
	
	Reference: https://appium.io/docs/en/commands/web/storage/delete-all-cookies/index.html

```


Switch to Frame

```java
	Change focus to another frame on the page (Web context only)
	driver.switchTo().frame(3);
	
	Reference: https://appium.io/docs/en/commands/web/frame/switch/index.html

```


Switch to Parent Frame

```java
	Change focus to the parent context (Web context only)
	driver.switchTo().parentFrame();

```


Execute Async Script

```java
	((JavascriptExecutor) driver).executeAsyncScript("window.setTimeout(arguments[arguments.length - 1], 500);");
	
	Reference: https://appium.io/docs/en/commands/web/execute-async/index.html

```


Execute Script

```java
	Inject a snippet of JavaScript into the page for execution in the context of the currently selected frame (Web context). Run a native mobile command (Native Context).
	((JavascriptExecutor) driver).executeScript("window.setTimeout(arguments[arguments.length - 1], 500);");
	
	Reference: https://appium.io/docs/en/commands/web/execute/index.html

```


Simple Swipe
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/simple-screen/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/simple-element/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/simple-partial-screen/


Android Swipe
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/android-simple/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/android-multiple/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/android-layout-direction/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/android-tricks/

iOS Swipe
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/ios-mobile-screen/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/ios-mobile-element/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/ios-mobile-element-search/


iOS Picker wheel
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/ios-picker-wheels-set-value/
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/ios-picker-wheels-mobile/

Troubleshoot
https://appium.io/docs/en/writing-running-appium/tutorial/swipe/swipe-troubleshoot-guide/



