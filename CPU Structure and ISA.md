
---

# 🌟 Chapter 1: Introduction to Computer Architecture

### What is Computer Architecture?

Computer architecture is the **blueprint** of a computer — it explains **how the system’s parts work together** to process data and run programs.

It includes:

- **Design** of components (CPU, memory, I/O devices)
    
- **Organization** of these components and their interactions
    
- Both **hardware and software aspects** that affect performance
    

🧠 _Think of computer architecture like the floor plan of a house — it shows how everything connects._

---

## 🧩 Computer Architecture vs Computer Organization

|Aspect|Computer Architecture|Computer Organization|
|---|---|---|
|Focus|What the system **does**|How it **does** it|
|Visible to programmer?|✅ Yes|❌ No|
|Examples|Instruction set, data types|Clock speed, memory size|
|Analogy|Blueprint of the house|The plumbing and wiring inside|

💡 **Tip to remember:**  
Architecture = _Visible (Logic)_  
Organization = _Invisible (Structure)_

---

## 🧠 Language of Instructions

Humans use languages like English or Sinhala,  
Computers use their own simple language — called **machine instructions**.

For example:

```
ADD A, B
MUL A, B
```

The **Instruction Set Architecture (ISA)** is the **complete set of instructions** a CPU can execute.

📘 ISA defines what the processor can do — add, move, multiply, compare, jump, etc.

---

## ⚙️ Features of a Good Instruction Set Architecture (ISA)

A good ISA must be:

1. **Complete** – can perform all necessary operations
    
2. **Concise** – not too many instructions (usually 32–1000)
    
3. **Generic** – not overly specific (avoid “add 15” type of instructions)
    
4. **Simple** – easy for the CPU to execute
    

🧠 _Easy way to remember → CGCS: Complete, Generic, Concise, Simple._

---

## 🏗️ Designing an ISA: Key Considerations

When designing an ISA, architects consider:

- Number and type of instructions
    
- Instruction complexity
    
- How data moves between memory and CPU
    

There are **two main ISA paradigms:**

### 1. RISC (Reduced Instruction Set Computer)

- Fewer, simpler instructions (about 64–128)
    
- Easier and faster to execute
    
- Example: **ARM processors**
    

### 2. CISC (Complex Instruction Set Computer)

- Larger instruction set
    
- More complex operations in a single instruction
    
- Example: **Intel x86 processors**
    

🧠 _Memory trick: RISC = “Simple & Speedy”, CISC = “Complex but Compact.”_

---

## 🪜 Levels of Machine Architecture

Computers work on several “levels”:

1. **User ISA Level** – the part visible to the programmer
    
2. **System ISA Level** – privileged instructions for the operating system
    
3. **Hardware Level** – where physical execution happens
    

---

## 👷 Role of a Computer Architect

A computer architect:

- Designs the ISA for **easy programming and good performance**
    
- Designs hardware for **efficient instruction execution**
    
- Balances performance, cost, and power
    
- Ensures compatibility with OS and applications
    

💭 There’s no single _best_ computer — it depends on user needs and cost.

---

## 💰 Computer Cost Factors

1. Hardware design cost
    
2. Software development cost (OS, apps)
    
3. Manufacturing cost
    
4. Price to the buyer
    

---

## ⚡ Computer Performance Factors

Performance depends on:

- Program size and frequency
    
- Number of users
    
- I/O device speed
    
- Technology advancements
    
- Architecture innovation
    

---

## 🕐 Defining Performance

### Response Time

- Time taken from the **start to the end** of a task
    
- Also known as **execution time**
    

### Throughput

- Number of jobs done per second (like cars produced per hour in a factory)
    

🧠 _Example:_  
If it takes 4 hours to make 1 car → response time = 4h  
If factory produces 6 cars/hour → throughput = 6 cars/hour

---

## 💻 CPU Time – True Measure of Processor Performance

CPU Time measures:

> How long the processor was _actually executing instructions_ (not waiting for I/O or multitasking).

It’s the best measure of how powerful the CPU is.

---

## ⏱️ Cycles Per Instruction (CPI)

Every CPU has a **clock** — a tiny oscillator that ticks billions of times per second.  
Each tick = one **cycle**.

- CPU speed = number of cycles per second (Hz, MHz, GHz)
    
- **CPI** = number of cycles required for one instruction
    

---

## 📐 Factors Affecting Processor Performance

1. **Clock Rate** – how fast the clock ticks
    
2. **CPI** – cycles per instruction
    
3. **Instruction Count (IC)** – number of instructions in a program
    

They are **interdependent** — changing one can affect the others.

---

## 🧮 CPU Time Formula


$\text{CPU Time} = \text{Instruction Count} \times \text{CPI} \times \text{Clock Cycle Time}$  
$or$  
$\text{CPU Time} = \frac{\text{Instruction Count} \times \text{CPI}}{\text{Clock Rate}}$  


---

## 🚀 Performance Improvement Tips

- Faster clock → may increase power use or complexity
    
- Lower CPI → simpler instructions (RISC helps)
    
- Fewer instructions → better compiler design
    

All must be balanced together.

---

## 🧩 Example Problem

**Given:**  
Program runs in 10s on 400 MHz CPU  
We want 6s runtime, but total cycles increase 1.2×

**Solution idea:**  
We need a higher clock rate to compensate for extra cycles.

Formula:  

$\text{New Clock Rate} = \text{Old Clock Rate} \times \frac{\text{New CPU Time} \times 1.2}{\text{Old CPU Time}}$  


---

## 🏁 Key Takeaways

- **Computer Architecture** = Design visible to programmers
    
- **ISA** = Defines what CPU can do
    
- **RISC** vs **CISC** = Simplicity vs Complexity
    
- **Performance** measured by CPU time, response time, throughput
    
- **CPU Time = IC × CPI × Clock Cycle Time**
    
- Optimization requires balancing all factors
    

---
Excellent 👏 Let’s continue to **Part 2: CPU Performance & Example Calculations** — written in the same **exam-friendly, book-style format** that makes it easy to memorize and understand.

---

# 🌟 Chapter 2: CPU Performance and Calculations

Performance is the heart of computer architecture.  
Every design decision — clock rate, instruction set, or compiler choice — ultimately aims to **improve performance**.

---

## ⚡ 1. What Does "Performance" Mean?

Performance simply tells **how fast** a computer runs a program.

We can measure it in **two main ways:**

|For Users|For System Managers|
|---|---|
|**Response Time** – how long it takes to finish one task|**Throughput** – how many tasks are completed per unit time|

🧠 **Trick to remember:**

> Response time = one program  
> Throughput = many programs

---

## 🕐 2. Response Time (Execution Time)

**Response Time** is the total time between the start and the end of a program.

Example:

> If your game takes 10 seconds to load, its response time = 10s.

---

## 📊 3. Throughput

Throughput = Number of jobs completed per second (or hour).

Example:

> A factory makes 6 cars per hour → throughput = 6 cars/hour.

⚠️ **Note:**  
Throughput and response time are _not always linked._  
A system can complete more jobs (high throughput) without making individual jobs faster.

---

## 🧮 4. CPU Time — The True Measure

CPU time is **the time during which the CPU actually executes instructions** (excluding waiting for I/O, OS tasks, etc.).

Formula:  
$$
  
\text{CPU Time} = \text{CPU Clock Cycles} \times \text{Clock Cycle Time}  
  
$$
or  
$$

\text{CPU Time} = \frac{\text{CPU Clock Cycles}}{\text{Clock Rate}}  

$$

🧠 **Memory tip:**  
More cycles → more time  
Higher clock → less time

---

## ⏱️ 5. Clock Cycle and Clock Rate

- **Clock Cycle:** One tick of the CPU clock (the time between pulses)
    
- **Clock Rate:** Number of clock cycles per second
    

**Units:**

- 1 MHz = 1 million cycles/sec
    
- 1 GHz = 1 billion cycles/sec
    

Example:

> A 2 GHz processor = 2,000,000,000 cycles per second.

---

## ⚙️ 6. CPI (Cycles Per Instruction)

Different instructions take different amounts of time.

- Simple instructions (like ADD) → fewer cycles
    
- Complex ones (like DIV or LOAD) → more cycles
    

 
$$
\text{CPI} = \frac{\text{Total Clock Cycles}}{\text{Instruction Count}}  
$$


🧠 **Think:** CPI shows how many clock ticks one instruction needs on average.

---

## 🔢 7. The Golden Formula for CPU Time

This is the most important formula in this topic — memorize it!

$$
\boxed{\text{CPU Time} = \text{Instruction Count (IC)} \times \text{CPI} \times \text{Clock Cycle Time}}  
$$


or equivalently,


$$
\boxed{\text{CPU Time} = \frac{\text{IC} \times \text{CPI}}{\text{Clock Rate}}}  
$$


---

## 🧩 8. Factors Affecting Processor Performance

|Factor|Description|Controlled by|
|---|---|---|
|**Clock Rate**|Speed of CPU cycles (GHz)|Hardware technology|
|**CPI**|How many cycles per instruction|ISA & CPU design|
|**Instruction Count (IC)**|How many instructions in a program|Compiler & programmer|

🧠 **Trick:** Remember as the triangle:

```
     Performance
     /     |     \
 Clock  CPI   Instruction
 Rate         Count
```

All three must be balanced!

---

## ⚡ 9. Performance Improvement — What Happens When You Change One Factor

- Increasing **Clock Rate** → usually increases speed, but may cause more power usage or heat.
    
- Reducing **CPI** → possible by simplifying the instruction set (RISC idea).
    
- Reducing **Instruction Count** → can be done by a smarter compiler or optimized code.
    

⚠️ Changing one can affect the others — they are **interdependent**.

---

## 🧮 10. Example Problem 1

**Question:**  
A program runs in **10 seconds** on a **400 MHz** computer.  
We want it to run in **6 seconds**, but increasing the clock rate makes the total clock cycles increase by **1.2×**.

What is the **minimum clock rate** required?

---

### Step 1: Formula


$$
\text{CPU Time} = \frac{\text{Clock Cycles}}{\text{Clock Rate}}  
$$

We know:

- Old Time = 10s
    
- New Time = 6s
    
- New Cycles = 1.2 × Old Cycles
    
- Old Clock Rate = 400 MHz
    

---

### Step 2: Build ratio

[  
$$
\frac{\text{Old Time}}{\text{New Time}} = \frac{\text{Old Clock Cycles} / \text{Old Clock Rate}}{\text{New Clock Cycles} / \text{New Clock Rate}}  
$$
]

Simplify:  
[  
$$
\frac{10}{6} = \frac{1 / 400}{1.2 / \text{New Clock Rate}}  
$$
]

---

### Step 3: Solve for new clock rate

[  
$$
\text{New Clock Rate} = 400 \times \frac{1.2 \times 6}{10}  
$$
]

[  
$$
\text{New Clock Rate} = 288 \text{ MHz}  
$$
]

**Answer:** ✅ Minimum required clock rate = **288 MHz**

---

## 🧮 11. Example Problem 2

We have two computers, **A** and **B**, that use the same ISA.

|Computer|Clock Cycle Time|CPI|
|---|---|---|
|A|10 ns|2.0|
|B|20 ns|1.2|

Which one is faster?

---

### Step 1: Formula

[  
$$
\text{CPU Time} = \text{IC} \times \text{CPI} \times \text{Clock Cycle Time}  
$$
]

(Since both have same IC, compare CPI × Cycle Time)

---

### Step 2: Calculate

- A → 2.0 × 10 ns = 20 ns
    
- B → 1.2 × 20 ns = 24 ns
    

**Smaller time = faster processor**

✅ **Computer A** is faster!

---

## 🎯 12. Key Takeaways for Exams

- **Performance = 1 / Execution Time**
    
- **CPU Time = IC × CPI × Clock Cycle Time**
    
- **Higher clock rate** → faster CPU
    
- **Lower CPI** → more efficient instructions
    
- **Lower IC** → better compiler/programmer
    
- **RISC** = simple instructions, fewer cycles
    
- **CISC** = complex instructions, higher CPI
    
- **Response Time ≠ Throughput**
    

🧠 **Mnemonic:**

> “**I See Clock**” → IC × CPI × Clock Time → CPU Time Formula

---
