
## 🔹 Maven Project Structure

```
src/main/java     → Application source code
src/test/java     → Test code
pom.xml           → Project configuration
target/           → Compiled output
```

---

## 🔹 Creating a Maven Project

```bash
mvn archetype:generate \
-DgroupId=com.mycompany.app \
-DartifactId=hello-world \
-DarchetypeArtifactId=maven-archetype-quickstart \
-DarchetypeVersion=1.4
```

---

## 🔹 pom.xml (Project Object Model)

```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.mycompany.app</groupId>
  <artifactId>hello-world</artifactId>
  <version>1.0-SNAPSHOT</version>
</project>
```

---

## 🔹 Adding Dependencies

```xml
<dependencies>
  <dependency>
    <groupId>org.seleniumhq.selenium</groupId>
    <artifactId>selenium-java</artifactId>
    <version>4.17.0</version>
  </dependency>
</dependencies>
```

---

## 🔹 Build Configuration (Compiler Plugin)

```xml
<build>
  <plugins>
    <plugin>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>3.8.1</version>
      <configuration>
        <source>1.8</source>
        <target>1.8</target>
      </configuration>
    </plugin>
  </plugins>
</build>
```

---

## 🔹 Common Maven Commands

```bash
mvn clean        # Remove target folder
mvn compile     # Compile source code
mvn test        # Run tests
mvn package     # Create JAR/WAR
mvn install     # Install to local repository
mvn clean install
```

---

## 🔹 Running Compiled JAR

```bash
java -cp target/hello-world-1.0-SNAPSHOT.jar com.mycompany.app.App
```

---

## 🔹 Reading Properties from pom.xml

### pom.xml

```xml
<properties>
  <app.name>HelloWorldApp</app.name>
  <app.version>1.0.0</app.version>
</properties>
```

### Java Code

```java
String appName = System.getProperty("app.name");
String appVersion = System.getProperty("app.version");
```

---

## 🔹 Executable JAR Configuration

```xml
<plugin>
  <artifactId>maven-jar-plugin</artifactId>
  <version>3.2.0</version>
  <configuration>
    <archive>
      <manifest>
        <mainClass>com.mycompany.app.App</mainClass>
      </manifest>
    </archive>
  </configuration>
</plugin>
```

### Run

```bash
java -jar hello-world-1.0-SNAPSHOT.jar
```

---

## ⭐ One-Line Summary (Exam Perfect)

**Maven is a build and dependency management tool that automates project creation, compilation, testing, and packaging using pom.xml.**

---

If you want next:

- 🔥 **Maven + Selenium + TestNG combined note**
    
- 🧠 **Last-night full lab revision sheet**
    
- ❓ **Maven viva / MCQs**
    
- ⚠️ **Common Maven errors & fixes**
    

Just tell me 👊