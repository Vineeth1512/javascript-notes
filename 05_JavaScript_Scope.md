# 🗂️ JavaScript – Scope (5W1H Notes)

---

## 🧩 Topic: JavaScript Scope

---

### ❓ **What**
**Scope** in JavaScript determines **where variables and functions are accessible** in the code.  
Types of scope:
1. **Global Scope** – Accessible everywhere in the program.  
2. **Function Scope** – Accessible only inside the function (used with `var`).  
3. **Block Scope** – Accessible only inside a block `{}` (used with `let` and `const`).  
4. **Lexical/Static Scope** – Scope defined by the position of code in the source file.

🧠 In simple words:  
> Scope is the **visibility or accessibility of variables** in different parts of the code.

---

### 💡 **Why**
- To **control access to variables** and avoid conflicts.  
- To **prevent accidental overwriting** of variables in other parts of the program.  
- To enable **modular and maintainable code**.  
- Scope is essential for **closures and private variables**.

---

### 🕒 **When**
- Every time a variable or function is declared, it is assigned a **scope** automatically.  
- Scope is **determined at compile time** (lexical scope).  
- When a function executes, **function and block scopes** are created.

---

### 📍 **Where**
- In **Global Scope** → Variables declared outside functions/blocks.  
- In **Function Scope** → Variables declared inside functions using `var`.  
- In **Block Scope** → Variables declared inside `{}` using `let` or `const`.  
- Everywhere JS runs: Browser, Node.js, apps.

---

### 👨‍💻 **Who**
- **Developer** writes code with variables and functions.  
- **JavaScript engine** enforces the rules of scope.  
- **Users** indirectly influence variable values through inputs.

---

### ⚙️ **How**
#### 1️⃣ Global Scope
```javascript
let globalVar = "I am global";
function showGlobal(){
  console.log(globalVar); // Accessible
}
showGlobal();
console.log(globalVar); // Accessible
```
#### 2️⃣ Function Scope
```javascript
function testFunction(){
  var functionVar = "I am inside function";
  console.log(functionVar); // Accessible
}
testFunction();
console.log(functionVar); // Error: Not accessible
```
#### 3️⃣ Block Scope
```javascript
if(true){
  let blockVar = "I am block scoped";
  const blockConst = "Also block scoped";
  console.log(blockVar); // Accessible
}
console.log(blockVar); // Error: Not accessible
```
#### 4️⃣ Lexical Scope (Static Scope)
```
function outer() {
  let outerVar = "outer";
  function inner() {
    console.log(outerVar); // Can access outerVar
  }
  inner();
}
outer();
```
#### 🧭 Summary Table (5W1H Overview)

| 🏷️ Category | 💬 Explanation                                                                         |
| ------------ | -------------------------------------------------------------------------------------- |
| **What**     | Determines where variables/functions are accessible.                                   |
| **Why**      | To control access, prevent conflicts, and write modular code.                          |
| **When**     | When variables/functions are declared and executed.                                    |
| **Where**    | Global, function, and block scopes in JS environment.                                  |
| **Who**      | JS engine enforces scope; developers declare variables/functions.                      |
| **How**      | `var` → function scope, `let/const` → block scope, lexical scope for nested functions. |
---
## 🌐 Real-Time Scenario – Example: Gmail Compose Button

On **Gmail**:

- Clicking **“Compose”** creates a **function scope** for opening the email editor.  
- Variables like `emailContent` are **local** to this function and cannot interfere with other emails.  
- **Global scope** holds user data like `userName` or `emailID`.  
- **Block scope** ensures temporary variables inside loops or conditionals don’t conflict.



```javascript
let userName = "Vineeth"; // Global scope
function composeEmail(){
  let emailContent = "Hello!"; // Function scope
  if(true){
    let tempDraft = "Draft saved"; // Block scope
  }
}
```
---


## 🧾 Key Points / Summary

✅ **Scope** determines where variables are accessible.  
✅ There are **Global, Function, Block, and Lexical scopes**.  
✅ `var` → function-scoped, `let` & `const` → block-scoped.  
✅ Scope prevents **variable conflicts** and enables **closures**.  
✅ Understanding scope is crucial for **debugging** and **writing clean JS code**.

---

## 💼 Interview Level – How to Answer in Your Own Words

> “**Scope** in JavaScript defines the accessibility of variables and functions.  
> Variables can be **global**, **function-scoped**, or **block-scoped** depending on where and how they are declared.  
> **Example:** In **Gmail**, the compose email function has local variables that don’t interfere with global variables like the user’s name.  
> Proper understanding of scope prevents conflicts and enables modular, maintainable code.”

---

## 💡 Tip

Always mention the **difference between `var`, `let`, and `const`**, and include **Lexical Scope** when explaining in interviews.

