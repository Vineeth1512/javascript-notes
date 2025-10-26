# ⚙️ Functions in JavaScript (5W1H Notes)

---

## 🧩 Topic: JavaScript Functions

---

### ❓ What
A **Function** in JavaScript is a **block of reusable code** designed to perform a specific task.  
It allows you to **organize**, **reuse**, and **modularize** your code efficiently.

🧠 In simple terms:  
> A function is like a **machine** — you give it input, it performs a task, and gives you output.

Example:
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Vineeth"));
```

### 💡 Why Use Functions?

- To **avoid repetition** of code.  
- To improve **code reusability** and **readability**.  
- To **organize logic** into smaller, maintainable parts.  
- To **return specific outputs** based on inputs.  
- To enhance **modular programming** and **debugging**.  

---

### 🕒 When to Use Functions?

- When a **task needs to be performed multiple times**.  
- When you want to **encapsulate logic** (e.g., calculations, API calls).  
- When writing **event handlers**, **callbacks**, or **asynchronous tasks**.  

---

### 📍 Where Are Functions Used?

Functions are used in **every part of JavaScript** — frontend and backend.  
Common examples:  
- In **React components** (functional components).  
- In **Node.js APIs** (request handlers).  
- In **event listeners**, **loops**, and **data processing**.  
- In **business logic** and **utility functions**.  

---

### 👨‍💻 Who Uses Functions?

- **Developers** define and invoke functions.  
- The **JavaScript Engine** executes them using **Execution Contexts** and the **Call Stack**.
---

### ⚙️ How
#### 1️⃣ Function Declaration
```javascript
function add(a, b) {
  return a + b;
}
console.log(add(3, 5)); // 8
```

#### 2️⃣ Function Expression
```javascript
const multiply = function (x, y) {
  return x * y;
};
console.log(multiply(2, 4)); // 8
```

#### 3️⃣ Arrow Function (ES6)

Compact syntax introduced in ES6.
```javascript
const greet = (name) => `Hello, ${name}!`;
console.log(greet("Vineeth"));
```

#### 4️⃣ Anonymous Function

A function without a name, often used as a callback.
```javascript

setTimeout(function () {
  console.log("This runs after 2 seconds");
}, 2000);
```

#### 5️⃣ Function with Default Parameters
```javascript
function welcome(name = "Guest") {
  return `Welcome, ${name}!`;
}
console.log(welcome()); // Welcome, Guest!
```

#### 6️⃣ Function Returning Another Function (Closure)
```javascript

function outer() {
  return function inner() {
    console.log("I’m an inner function!");
  };
}
outer()(); // Calling both at once
```
#### 7️⃣ Named Function Expression
```javascript
const factorial = function fact(n) {
  if(n === 0) return 1;
  return n * fact(n - 1);
};
console.log(factorial(5)); // 120
```
- Name helps in recursion/debugging, stored in a variable.
#### 8️⃣ Immediately Invoked Function Expression (IIFE)
```javascript
(function () {
  console.log("IIFE runs immediately!");
})();
```

# 🌐 Real-Time Scenario (Example: Amazon Search Filter)
On Amazon , functions are used for searching, filtering, and sorting products.
```javascript
function filterProducts(products, minPrice) {
  return products.filter((p) => p.price >= minPrice);
}

const products = [
  { name: "Phone", price: 15000 },
  { name: "Laptop", price: 50000 },
  { name: "Mouse", price: 700 }
];

console.log(filterProducts(products, 1000));
// Output: [{ name: "Phone", price: 15000 }, { name: "Laptop", price: 50000 }]
```
--- 

# 🧭 Summary Table (5W1H Overview)
| 🏷️ Category | 💬 Explanation                                                   |
| ------------ | ---------------------------------------------------------------- |
| **What**     | A reusable block of code that performs a specific task.          |
| **Why**      | To avoid repetition, improve reusability, and organize logic.    |
| **When**     | When a task repeats or modularization is needed.                 |
| **Where**    | In all web and backend logic (React, Node.js, etc.).             |
| **Who**      | Developers define and invoke them; JS engine executes them.      |
| **How**      | Using declarations, expressions, arrow functions, and callbacks. |

---

## 🧾 Key Points / Summary – JavaScript Functions

✅ Functions **enhance reusability** and **reduce redundancy**.  
✅ They can **accept parameters** and **return values**.  
✅ Support **declarations**, **expressions**, and **arrow function** syntax.  
✅ Used for **logic separation** and **callback handling**.  
✅ Essential for **modular programming** and **asynchronous operations**.  

---

## 🗣️ Interview Level – How to Answer in Your Own Words

> “A **function** in JavaScript is a reusable block of code that performs a specific task.  
> It improves **code reusability** and **readability**.  
> **Example:** Amazon uses functions to filter products or calculate prices dynamically.  
> Functions can be **declared**, **expressed**, or written as **arrow functions**, depending on the use case.”
