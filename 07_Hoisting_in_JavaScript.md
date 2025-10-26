# 🚀 Hoisting in JavaScript (5W1H Notes)

---

## 🧩 Topic: Hoisting in JavaScript

---

### ❓ **What**
**Hoisting** is JavaScript’s default behavior of **moving declarations to the top** of their scope **before code execution**.

It means:
- Variables and function **declarations** are processed before any code runs.
- So, you can use variables and functions **before declaring them**.

🧠 In simple words:  
> Hoisting is like JS saying, “I’ll remember your declarations before running your code.”

---

### 💡 **Why**
- To allow **flexible coding** where functions can be called before their definitions.  
- Helps JavaScript **compile and execute** code efficiently.  
- Prevents **reference errors** during the creation phase of execution context.

---

### 🕒 **When**
- Happens during the **compilation phase**, before execution.  
- JS engine first scans the code, **allocates memory** for variables and functions.  
- Then executes the code line by line.

---

### 📍 **Where**
- Hoisting happens **inside every scope** (global, function, and block).  
- Works differently for **var**, **let**, **const**, and **functions**.

---

### 👨‍💻 **Who**
- **JavaScript Engine** (like V8 in Chrome) performs hoisting automatically.  
- **Developers** should understand it to avoid unexpected `undefined` or `ReferenceError` issues.

---

### ⚙️ **How**
#### 🧠 Step 1: Variable Hoisting
```javascript
console.log(a); // Output: undefined
var a = 10;
```
Explanation:

- During compilation, **var a** is hoisted (declared but not initialized).

- So **a** exists but has value **undefined** until line 2 executes.

#### 🚫 let & const Hoisting (Temporal Dead Zone)

```javascript
console.log(b); // ReferenceError
let b = 20;
```
Explanation:

- let and const are **hoisted but not initialized.**

- Accessing them before declaration throws an error (Temporal Dead Zone).

#### 🧩 Function Hoisting
```javascript
greet(); // Output: Hello Vineeth!
function greet() {
  console.log("Hello Vineeth!");
}
```
Explanation:

- Function **declarations** are fully hoisted (both name & body).

- You can safely call them before defining.
#### ⚠️ Function Expression Hoisting
```javascript
sayHi(); // TypeError
var sayHi = function() {
  console.log("Hi!");
};
```
Explanation:

- Function expressions are treated like variables.

- Only `sayHi` is hoisted, not its assigned function — hence, TypeError.

#### 🌐 Real-Time Scenario (Example: Netflix App Initialization)

When the **Netflix homepage loads,** several initialization functions (like loading recommendations, user profile, or autoplay logic) might be **defined later** in code but are **called early** thanks to hoisting.
```javascript
initializeApp();

function initializeApp(){
  loadUserProfile();
  loadRecommendations();
}

function loadUserProfile(){
  console.log("User profile loaded!");
}
```
#### 🧾 Key Points / Summary

- ✅ Hoisting moves declarations to the top of scope.
- ✅ var → hoisted with undefined.
- ✅ let/const → hoisted but not initialized (TDZ).
- ✅ Function declarations are fully hoisted.
- ✅ Function expressions are not hoisted like declarations.
- ✅ Understanding hoisting prevents unexpected bugs.

  ---
#### 🧭 Summary Table (5W1H Overview)
  | 🏷️ Category | 💬 Explanation                                                               |
| ------------ | ---------------------------------------------------------------------------- |
| **What**     | Automatic movement of declarations to the top of scope.                      |
| **Why**      | To ensure variables and functions are recognized before execution.           |
| **When**     | During the compile phase (before execution).                                 |
| **Where**    | In all scopes: global, function, and block.                                  |
| **Who**      | Managed by the JS engine.                                                    |
| **How**      | `var` initialized as undefined, `let/const` in TDZ, functions fully hoisted. |

---

#### 🗣️ Interview Level – How to Answer in My Own Words

“Hoisting in JavaScript is the process where variable and function declarations are moved to the top of their scope before execution.
For example, with `var`, you can access a variable before it’s declared but get `undefined`.
`let` and `const` are also hoisted but remain in a Temporal Dead Zone until declared.
I use this knowledge to avoid runtime errors and structure my functions clearly, just like how Netflix initializes app logic before defining all helper functions.”
