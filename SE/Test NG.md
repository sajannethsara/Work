
## 📌 TestNG – Short Note (Usage + Example)

**TestNG** is a Java testing framework used to **write, organize, and execute test cases** efficiently.  
It provides annotations, assertions, grouping, priorities, dependencies, and data-driven testing.

### 🔹 Key Features

- Uses `@Test` annotation (no `main()` method)
    
- Supports **Assertions**
    
- Allows **Grouping** of tests
    
- Controls execution using **priority** and **dependencies**
    
- Supports **Data Providers**
    
- Uses `testng.xml` for centralized control
    

---

## 🔹 Basic TestNG Example

```java
import org.testng.Assert;
import org.testng.annotations.Test;

public class CalculatorTest {

    Calculator calculator = new Calculator();

    @Test
    public void testAdd() {
        Assert.assertEquals(calculator.add(2, 3), 5);
    }
}
```

---

## 🔹 Grouping Tests

```java
@Test(groups = "BasicOperations")
public void testAdd() {
    Assert.assertEquals(calculator.add(2, 3), 5);
}
```

---

## 🔹 Priority & Dependency

```java
@Test(priority = 1)
public void testAdd() { }

@Test(priority = 2, dependsOnMethods = {"testAdd"})
public void testMultiply() { }
```

---

## 🔹 Data Provider Example

```java
@DataProvider(name = "addData")
public Object[][] data() {
    return new Object[][] {
        {1, 2, 3},
        {2, 3, 5}
    };
}

@Test(dataProvider = "addData")
public void testAdd(int a, int b, int result) {
    Assert.assertEquals(calculator.add(a, b), result);
}
```

---

## 🔹 Exception Testing

```java
@Test(expectedExceptions = IllegalArgumentException.class)
public void testDivideByZero() {
    calculator.divide(5, 0);
}
```

---

## 🔹 Before & After Annotations

```java
@BeforeMethod
public void beforeTest() {
    System.out.println("Before test");
}

@AfterMethod
public void afterTest() {
    System.out.println("After test");
}
```

---

## 🔹 testng.xml Example

```xml
<suite name="Calculator Suite">
  <test name="Calculator Tests">
    <groups>
      <run>
        <include name="BasicOperations"/> // targeting group
      </run>
    </groups>
    <classes>
      <class name="CalculatorTest"/> // Targeting class
    </classes>
  </test>
</suite>
```

---

## ⭐ One-Line Summary (Exam Perfect)

**TestNG is a Java testing framework that uses annotations to manage test execution, validation, grouping, and data-driven testing efficiently.**

---

If you want, I can also:

- Compress this into a **half-page handwritten note**
    
- Create **MCQs from this**
    
- Give a **Selenium + TestNG combo note** (very exam-likely)
    

Just tell me 👍