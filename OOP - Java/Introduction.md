Topic No : 1
Next Topic : [[new Keyword]]

## OOPS for Java

#### I'm Starting to learn oops concepts in java programming language using the You tube playlist by Kunal Kushwaha and taking notes.

#### [Link for the Youtube Playlist](https://youtu.be/BSVKUk58K6U?si=sz1hTbznRzNiqPwh) and referring [github repository](https://github.com/premnath018/oops_java) 

#### In class, functions will be referred as methods
## Why OOP

If you need to storing data of multiple datatypes, we can create a class as template and creating object as their instances

## What is 'class'

A class is a named group of properties and functions
We can create our own datatype.

The variables used inside the classes are instance variable

## 🔹 JVM vs JRE vs JDK (Core Java)

### 1️⃣ **JVM (Java Virtual Machine)**

**What it is:**  
JVM is a **runtime engine** that **executes Java bytecode**.

**Main responsibilities:**

- Loads `.class` files
- Verifies bytecode (security)
- Converts bytecode → machine code
- Manages memory (Heap, Stack)
- Handles Garbage Collection

**Key points interviewers like:**

- JVM is **platform dependent**
- Bytecode is **platform independent**
- JVM does **not** compile Java code
- JVM exists **only at runtime**

**Internal components:**

- Class Loader
- Runtime Data Areas
- Execution Engine
- Garbage Collector

👉 Example:

> `.class` file runs on Windows JVM, Linux JVM, Mac JVM — same bytecode, different JVMs

---

### 2️⃣ **JRE (Java Runtime Environment)**

**What it is:**  
JRE provides the **environment to run Java programs**.

**Contains:**

- JVM
- Core libraries (`java.lang`, `java.util`, etc.)
- Supporting files

**What it can do:**

- ✅ Run Java programs
- ❌ Cannot compile Java code

**Use case:**

- End users
- Production servers

👉 Formula:

`JRE = JVM + Libraries`

---

### 3️⃣ **JDK (Java Development Kit)**

**What it is:**  
JDK is a **complete toolkit to develop Java applications**.

**Contains:**

- JRE
- Compiler (`javac`)
- Debugger (`jdb`)
- Archiver (`jar`)
- Other dev tools

**What it can do:**

- ✅ Write Java code
- ✅ Compile Java code
- ✅ Run Java code

**Use case:**

- Developers

👉 Formula:

`JDK = JRE + Development Tools`

---

## 🔁 Comparison Table (Product-Company Friendly)

| Feature            | JVM     | JRE   | JDK        |
| ------------------ | ------- | ----- | ---------- |
| Executes code      | ✅       | ✅     | ✅          |
| Compiles code      | ❌       | ❌     | ✅          |
| Platform dependent | ✅       | ✅     | ✅          |
| Used by            | Runtime | Users | Developers |
| Contains JVM       | ❌       | ✅     | ✅          |

---

## ⭐ Common Interview Traps & Answers

### ❓ Why Java is platform independent?

✔ Because **bytecode** is platform independent  
❌ Not because JVM is platform independent

---

### ❓ Can we run Java program without JRE?

❌ No — JVM and libraries are required

---

### ❓ Can we compile Java program without JDK?

❌ No — compiler (`javac`) is part of JDK

---

### ❓ Is JVM part of OS?

❌ No — JVM runs **on top of OS**

---

## 🧠 One-Line Interview Answer

> **JVM** executes Java bytecode,  
> **JRE** provides runtime environment,  
> **JDK** provides tools to develop, compile, and run Java applications.