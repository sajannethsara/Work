## 🔹 Key Features

- Open source
    
- Supports multiple **browsers** (Chrome, Firefox, Edge)
    
- Supports multiple **languages** (Java, Python, etc.)
    
- Works on multiple **operating systems**
    
- Supports **parallel testing**
    
- ❌ Does **not** support desktop (Windows) applications
    

---

## 🔹 Core Component

**WebDriver** – main interface used to control the browser

---

## 🔹 Basic Selenium Example (Selenium 4)

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class FirstTest {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.google.com/");
    }
}
```

---

## 🔹 Selenium with TestNG

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class GoogleTest {

    @Test
    public void openGoogle() {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.google.com/");
    }
}
```

---

## 🔹 Locators (Element Identification)

Selenium locates web elements using **locators**:

- `id`
    
- `name`
    
- `className`
    
- `xpath`
    
- `tagName`
    
- `cssSelector`
    

---

## 🔹 Locator Example

```java
driver.findElement(By.name("q"))
      .sendKeys("Colombo" + Keys.ENTER);
```

---

## 🔹 Common WebDriver Methods

```java
driver.get(url);
driver.getTitle();
driver.getCurrentUrl();
driver.close();
driver.quit();
```

---

## 🔹 Selenium Setup Methods

### Selenium 4 (Recommended)

```java
WebDriver driver = new ChromeDriver();
```

### Selenium 3 (Old)

```java
System.setProperty("webdriver.chrome.driver", "path");
WebDriver driver = new ChromeDriver();
```

---

## ⭐ One-Line Summary (Exam Perfect)

**Selenium is a web automation tool that uses WebDriver to control browsers and perform automated testing of web applications.**

---

If you want next:

- ⚡ **Selenium + TestNG combined short note**
    
- 🧠 **Last-night exam memory sheet**
    
- ❓ **Viva questions from Selenium**
    
- 🔁 **Common Selenium errors & fixes**
    

Just say it 👊