# ➕ JavaScript Operators (5W1H Notes)

---

## 🧩 Topic: JavaScript Operators

---

### ❓ **What**
**Operators** in JavaScript are **symbols or keywords** used to **perform specific operations** on one or more values (operands).  
They allow you to perform **mathematical, comparison, logical, and assignment tasks** in your program.

🧠 In simple words:  
> Operators are the **action symbols** that make JavaScript “do things” like add, compare, assign, or decide.

---

### 💡 **Why**
- To **perform operations** like calculations, comparisons, or logical decisions.  
- To make JavaScript **dynamic and interactive**.  
- To **control the flow of logic** in conditions and loops.  
- To **manipulate and transform data** easily.

---

### 🕒 **When**
- Whenever you need to **evaluate an expression** or **make a decision**.  
- Used while assigning values, performing arithmetic, comparing data, or applying logical conditions.  

---

### 📍 **Where**
- Used **everywhere** in JavaScript:
  - In variables and expressions.
  - In conditional statements (`if`, `switch`).
  - In loops (`for`, `while`).
  - In functions and event handling.
  - In frameworks like React and Node.js APIs.

---

### 👨‍💻 **Who**
- **Developers** use them to build logic.  
- **JavaScript Engine** interprets and executes them.  

---

### ⚙️ **How**

#### 🧮 1️⃣ Arithmetic Operators
Used to perform mathematical operations.
```javascript
let x = 10, y = 3;
console.log(x + y); // 13
console.log(x - y); // 7
console.log(x * y); // 30
console.log(x / y); // 3.33
console.log(x % y); // 1
console.log(x ** y); // 1000 (Exponentiation)
```
#### 🟰 2️⃣ Assignment Operators

Used to assign and update variable values.
```javascript
let num = 5;
num += 3; // num = num + 3 → 8
num *= 2; // num = 16

```
#### ⚖️ 3️⃣ Comparison Operators

Used to compare two values (returns true/false).

```javascript

console.log(5 == "5");   // true  (loose equality)
console.log(5 === "5");  // false (strict equality)
console.log(10 > 5);     // true
console.log(10 != 5);    // true

```
#### 🔀 4️⃣ Logical Operators

Used to combine conditions
```javascript
let a = true, b = false;
console.log(a && b); // false
console.log(a || b); // true
console.log(!a);     // false

```
#### ➕ 5️⃣ Unary Operators

Operate on a single operand.
```javascript
let n = 10;
console.log(++n); // 11
console.log(--n); // 10

```
#### ❔ 6️⃣ Ternary Operator (Conditional)
Acts as a shorthand for `if-else`.

```javascript
let age = 18;
let result = age >= 18 ? "Adult" : "Minor";
console.log(result); // Adult

  ```
#### 🧠 7️⃣ Type Operators
Used for type checking or conversion.
```javascript
console.log(typeof "Vineeth"); // string
console.log(typeof 123);       // number
```
---

#### 🧭 Summary Table (5W1H Overview)

| 🏷️ Category | 💬 Explanation                                                                   |
| ------------ | -------------------------------------------------------------------------------- |
| **What**     | Symbols that perform operations on operands.                                     |
| **Why**      | To perform calculations, comparisons, and logical checks.                        |
| **When**     | Used in expressions, loops, and conditions.                                      |
| **Where**    | In all JS environments (browser, Node.js, APIs).                                 |
| **Who**      | Developers write them; JS engine executes them.                                  |
| **How**      | Using arithmetic, comparison, logical, assignment, unary, and ternary operators. |
