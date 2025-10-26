# 🔒 Closures in JavaScript (5W1H Notes)

---

## 🧩 Topic: Closures in JavaScript

---

### ❓ **What**
A **closure** is the **combination of a function and its lexical environment** (the scope in which it was created).

When a function is defined inside another function, the **inner function** remembers the **variables of the outer function** even after the outer function has finished executing.

🧠 In simple words:  
> A closure allows a function to **“remember” variables** from its parent scope **even after the parent is gone.**

---

### 💡 **Why**
- To **preserve data** after a function’s execution.  
- To **create private variables and methods**.  
- To build **modular, reusable, and secure** JavaScript code.  
- Commonly used in **event handlers, callbacks, and async programming**.

---

### 🕒 **When**
- When a **function is nested** inside another function.  
- When the **inner function is returned or passed** as a callback.  
- When variables need to **retain their values** between function calls.

---

### 📍 **Where**
- In **every execution context**, closures are automatically created when an inner function references outer variables.  
- Used in browsers, Node.js, frameworks like React (hooks), and APIs.

---

### 👨‍💻 **Who**
- **Developers** use closures to protect data and manage state.  
- **JavaScript engine** creates closures automatically when it detects variable references from outer scopes.

---

### ⚙️ **How**
#### Example 1️⃣: Basic Closure
```javascript
function outer() {
  let count = 0;
  function inner() {
    count++;
    console.log(count);
  }
  return inner;
}

const counter = outer(); 
counter(); // Output: 1
counter(); // Output: 2
```

🧩 Here, `inner()` forms a closure — it remembers count from `outer()` even after `outer()`finishes executing.

---
#### Example 2️⃣: Private Variables using Closures
```javascript
function createBankAccount() {
  let balance = 1000;

  return {
    deposit(amount) {
      balance += amount;
      console.log(`Deposited: ₹${amount}. New Balance: ₹${balance}`);
    },
    withdraw(amount) {
      if (amount <= balance) {
        balance -= amount;
        console.log(`Withdrawn: ₹${amount}. Remaining Balance: ₹${balance}`);
      } else {
        console.log("Insufficient funds!");
      }
    }
  };
}

const myAccount = createBankAccount();
myAccount.deposit(500);   // Deposited: ₹500. New Balance: ₹1500
myAccount.withdraw(200);  // Withdrawn: ₹200. Remaining Balance: ₹1300
```
🧠 The balance variable is **private** — it’s accessible only through the closure functions `deposit` and `withdraw`.


---
# 🌐 Real-Time Scenario – Example: Amazon Shopping Cart

## 📌 Scenario Breakdown

On **Amazon**, when you add an item to the cart:

- The **total count of items** is maintained using **closures**.  
- Even when you navigate to another page, the count persists until you **clear it** or **checkout**.

### 💻 Example Code

```javascript
function cartCounter() {
  let itemCount = 0;

  return function() {
    itemCount++;
    console.log(`Items in Cart: ${itemCount}`);
  };
}

const addItem = cartCounter();
addItem(); // Items in Cart: 1
addItem(); // Items in Cart: 2
```

#### 🧾 Key Points / Summary – JavaScript Closures

✅ A **closure** gives a function access to its **outer scope variables**.  
✅ Created automatically when an **inner function references variables** from its outer function.  
✅ Helps in **data hiding** and **state management**.  
✅ Widely used in **callbacks**, **event handlers**, and **React Hooks**.  
✅ Avoid unnecessary closures to prevent **memory leaks**.

---
#### 🧭 Summary Table (5W1H Overview)

| 🏷️ Category | 💬 Explanation                                                                |
| ------------ | ----------------------------------------------------------------------------- |
| **What**     | A function that remembers variables from its outer scope.                     |
| **Why**      | To preserve data, create private variables, and manage state.                 |
| **When**     | When an inner function accesses outer variables.                              |
| **Where**    | In browsers, Node.js, React hooks, event handlers.                            |
| **Who**      | Developers use it; JS engine automatically manages closures.                  |
| **How**      | By returning or passing inner functions that reference outer scope variables. |


#### 💼 Interview Level – How to Answer in Your Own Words

> “A **closure** in JavaScript is formed when an inner function remembers and accesses variables from its outer function, even after the outer function has returned.  
> **Example:** Amazon’s cart counter uses a closure to remember how many items were added.  
> Closures help **maintain state**, create **private variables**, and are widely used in **event handling** and **frameworks like React**.”
