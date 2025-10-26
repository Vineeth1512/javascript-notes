# 📝 JavaScript – Variables (5W1H Notes)

---

## 🧩 Topic: JavaScript Variables

---

### ❓ **What**
A **variable** is a **named storage** in memory that holds a value.  
In JavaScript, variables can store **any data type**, including numbers, strings, arrays, objects, or functions.

Three ways to declare variables:
1. **var** – function-scoped, can be redeclared, hoisted.  
2. **let** – block-scoped, cannot be redeclared in the same scope.  
3. **const** – block-scoped, cannot be redeclared or reassigned.

🧠 In simple words:  
> Variables are **containers that store data** to be used later in your program.

---

### 💡 **Why**
- To **store and manipulate data** dynamically.  
- To **reuse values** without rewriting them.  
- To make code **readable and maintainable**.  
- To handle **user inputs, calculations, and application state**.

---

### 🕒 **When**
- When declaring a variable to store information, e.g., user input, API response.  
- When updating values during program execution.  

---

### 📍 **Where**
- **Browser**: Form data, DOM elements, user interactions.  
- **Node.js**: Server variables, API data, database queries.  
- Anywhere JS code runs.

---

### 👨‍💻 **Who**
- **Developer** declares variables.  
- **JavaScript engine** manages memory and execution.  
- **Users** indirectly influence variable values via inputs and interactions.

---

### ⚙️ **How**
#### 1️⃣ Declaring Variables
```javascript
var name = "Vineeth";  // var
let age = 25;          // let
const country = "India"; // const
```

#### 2️⃣ Updating Variables
```javascript
name = "Vineeth Kumar"; // allowed for var/let
// country = "USA";     // Error: const cannot be reassigned
```
#### 3️⃣ Scope Examples
```javascript
function testVar() {
  var x = 10; // function scope
  if(true){
    var x = 20; // same variable updated
    console.log(x); // 20
  }
  console.log(x); // 20
}

function testLet() {
  let y = 10; // block scope
  if(true){
    let y = 20; // new block-scoped variable
    console.log(y); // 20
  }
  console.log(y); // 10
}
```

## 🌐 Real-Time Scenario – Example: User Login Form


On **LinkedIn Login Page**:

| Input | Stored in JS Variable |
|-------|--------------------|
| Username input | `username` |
| Password input | `password` |

**Example Code:**
```javascript
let username = document.getElementById("username").value;
let password = document.getElementById("password").value;
```
---
## 🧭 Summary Table (5W1H Overview)

| 🏷️ Category | 💬 Explanation                                                        |
| ------------ | --------------------------------------------------------------------- |
| **What**     | Named storage in memory to hold data.                                 |
| **Why**      | To store, reuse, and manipulate values.                               |
| **When**     | When declaring variables or updating data.                            |
| **Where**    | Browser scripts, Node.js, apps, APIs.                                 |
| **Who**      | Developers declare them; JS engine manages memory.                    |
| **How**      | Declared using `var`, `let`, `const`; scope determines accessibility. |
---
## 🧾 Key Points / Summary – JavaScript Variables

✅ Variables store data temporarily in memory.  
✅ `var` = function-scoped, `let` = block-scoped, `const` = immutable.  
✅ Scope determines where variables are accessible.  
✅ Variables enable dynamic, interactive web applications.

---

## 🗣️ Interview Level – How to Answer in Your Own Words

> “A **variable** in JavaScript is like a labeled container for storing data.  
> I can use **var, let, or const** depending on scope and mutability.  
> **Example:** On LinkedIn’s login form, `username` and `password` are variables that hold user input values.  
> Using variables allows JS to **store, access, and manipulate data dynamically**.”

---

## 💡 Tip

Mention **scope**, **mutability**, and provide a **real-world example** in your answer.


