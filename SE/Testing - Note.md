
# 1️⃣ What is Software Testing? (VERY IMPORTANT)

### **Definition (memorize this)**

**Software Testing** is the process of **evaluating and examining software** to ensure it **works correctly**, meets **requirements**, and is **free from defects**.

### In simple words

👉 We run the software  
👉 Give inputs  
👉 Compare **actual result vs expected result**  
👉 Find bugs before users do

### **Main Goal**

- Find defects
    
- Improve quality
    
- Increase reliability
    
- Ensure user satisfaction
    

✍️ **Exam Tip**: Always mention

> _“Actual results are compared with expected results”_

---

# 2️⃣ Importance of Software Testing (Write Any 4–5)

### 1. **Quality Assurance**

Ensures the software meets required standards and works as expected.

### 2. **Risk Mitigation**

Reduces chances of failures, crashes, or security issues.

### 3. **User Satisfaction**

Bug-free software = happy users.

### 4. **Cost Efficiency**

Fixing bugs early is **cheaper** than fixing them after release.

### 5. **Compliance & Standards**

Ensures legal, security, and industry standards are met.

---

# 3️⃣ Types of Software Testing (High-level)

### 🔹 Manual Testing

Testing done **by humans**, without automation tools.

### 🔹 Automated Testing

Testing done using **tools & scripts**.

### 🔹 Non-Functional Testing

Tests **performance, security, usability**, etc.

---

# 4️⃣ Manual Testing (Exam Favorite)

### **Definition**

Manual testing is performed by **human testers** who execute test cases **without automation tools**.

### Key Types inside Manual Testing:

#### 🔸 Exploratory Testing

- No predefined test cases
    
- Tester uses **experience & intuition**
    
- Goal: find hidden bugs
    

#### 🔸 Usability Testing

- Focus on **UI & UX**
    
- Checks if app is easy to use
    

#### 🔸 Ad-hoc Testing

- Unplanned testing
    
- No documentation
    
- “Break the system” style 😄
    

✍️ **Exam line**:

> Manual testing is flexible and good for UI/UX validation.

---

# 5️⃣ Automated Testing

### **Definition**

Automated testing uses **tools and scripts** to execute test cases automatically.

### Why Automation?

- Faster execution
    
- Reusable test scripts
    
- Best for **regression testing**
    

### Example Tool:

✔ **Selenium**

---

## 🧮 How to Test a Calculator? (Exam Scenario)

### Manual Test Cases:

- 2 + 3 = 5
    
- 5 − 2 = 3
    
- Divide by zero → error
    
- Large numbers
    
- Invalid inputs (letters)
    

---

# 6️⃣ Test Levels (MEMORIZE ORDER)

👉 **U → I → S → A**

### 1. **Unit Testing**

- Tests individual functions/methods
    
- Done by developers
    
- Uses mocks/stubs
    

### 2. **Integration Testing**

- Tests interaction between modules
    
- Finds data flow issues
    

### 3. **System Testing**

- Tests the **entire system**
    
- End-to-end testing
    

### 4. **Acceptance Testing**

- Done by users or clients
    
- Checks business requirements
    
- Includes **UAT, Alpha, Beta**
    

---

# 7️⃣ Regression Testing

### **Definition**

Regression testing ensures that **new changes do not break existing features**.

### Example:

- New feature added
    
- Old login stops working ❌
    
- Regression testing catches this
    

---

# 8️⃣ Software Testing Life Cycle (STLC) 🔁

### Phases (MEMORIZE IN ORDER):

1️⃣ Requirement Analysis  
2️⃣ Test Planning  
3️⃣ Test Design  
4️⃣ Test Execution  
5️⃣ Defect Reporting & Tracking  
6️⃣ Test Closure

---

## 🔹 Requirement Analysis

- Understand what to test
    
- Clarify ambiguities
    
- Identify testable requirements
    

**Output**: Clear testing scope

---

## 🔹 Test Planning

- Decide **how** to test
    
- Resources, tools, schedule
    

**Output**: Test Plan document

---

## 🔹 Test Design

- Create test cases
    
- Cover positive, negative & boundary cases
    

**Output**: Test cases & test data

---

## 🔹 Test Execution

- Run test cases
    
- Compare expected vs actual
    
- Log defects
    

---

## 🔹 Defect Reporting & Tracking

- Report bugs with:
    
    - Severity
        
    - Priority
        
    - Steps to reproduce
        

---

## 🔹 Test Closure

- Prepare test summary report
    
- Lessons learned
    
- Sign-off
    

---

# 9️⃣ Test Case (MUST KNOW)

### **Definition**

A test case is a **set of steps** used to verify a specific functionality.

### Components:

- Test Case ID
    
- Title
    
- Preconditions
    
- Test Steps
    
- Test Data
    
- Expected Result
    
- Actual Result
    
- Status
    

💡 **You already have a perfect example** — just reproduce it in exams 👍

---

# 🔟 Testing Techniques

## 🔹 Black Box Testing

- No code knowledge
    
- Focus on input & output
    
- User perspective
    

### Example: Login

✔ Valid login  
❌ Invalid username  
❌ Invalid password

---

## 🔹 White Box Testing

- Code knowledge required
    
- Tests logic, branches, paths
    
- Used by developers
    

---

## 🔹 Grey Box Testing

- Partial code knowledge
    
- Combination of black & white box
    

---

# 1️⃣1️⃣ Code Coverage Metrics (VERY EXAM-IMPORTANT)

## ✔ Statement Coverage

Checks whether **every line** of code is executed.

**Formula**:

```
(No. of statements executed / Total statements) × 100
```

---

## ✔ Branch Coverage

Checks whether **each decision (true & false)** is tested.

Example:

```
if (x > 10)
```

Need:

- x = 12 (true)
    
- x = 5 (false)
    

---

## ✔ Path / Flow Coverage

Checks **all possible execution paths**

More paths → more test cases

---

### 🔑 One-line Summary (WRITE THIS!)

- **Statement** → every line
    
- **Branch** → every true & false
    
- **Path** → every possible path
    

---

# 1️⃣2️⃣ Equivalence Partitioning

### Idea:

Instead of testing all values, divide inputs into **groups (partitions)**.

### Example: Discount System

- ≤100 → No discount
    
- 101–500 → 10%
    
- > 500 → 20%
    

✔ Pick **one value from each partition**

---

# 1️⃣3️⃣ Boundary Value Analysis (BVA)

### Focus:

Test **edges of ranges**

### Example: Age 18–100

Test:

- 17 ❌
    
- 18 ✅
    
- 100 ✅
    
- 101 ❌
    

✍️ **Golden Rule**:

> Bugs often occur at boundaries

---

# 1️⃣4️⃣ OTP Boundary Value Analysis (Activity Answer)

OTP length = **6 digits**

### Test Cases:

1. 6 digits → Accept
    
2. 5 digits → Reject
    
3. 7 digits → Reject
    
4. Empty OTP → Reject
    
5. Alphabet characters → Reject
    

---

# 1️⃣5️⃣ Test Automation

### Benefits:

- Faster
    
- Reliable
    
- Reusable
    
- Ideal for regression
    

### Best Practices:

- Automate stable features
    
- Maintain scripts
    
- Use meaningful assertions
    

---

# 1️⃣6️⃣ Non-Functional Testing

### Performance Testing

- Load Testing
    
- Stress Testing
    
- Scalability Testing
    

### Security Testing

- Penetration Testing
    
- Vulnerability Scanning
    

### Others:

- Usability Testing
    
- Compatibility Testing
    

---

# 1️⃣7️⃣ Software Testing Metrics (Just Know Meanings)

- **Defect Density** → Bugs per size
    
- **Test Coverage** → % tested
    
- **Pass Rate** → Passed tests / total
    
- **MTTF** → Avg time between failures
    
- **Defect Leakage** → Bugs missed before release
    

---

## 🧠 EXAM STRATEGY (IMPORTANT)

✔ Write **definitions clearly**  
✔ Use **headings & bullet points**  
✔ Add **examples wherever possible**  
✔ Draw **simple diagrams** if allowed

---

If you want 👉

- **MCQ practice**
    
- **Short-answer exam questions**
    
- **Model answers**
    
- **One-page revision sheet**
    

Just say the word 💪📘