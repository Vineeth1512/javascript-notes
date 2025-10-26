# 🧠 JavaScript – Execution Context & Call Stack (5W1H Notes)

---

## 🧩 Topic: JavaScript Execution Context & Call Stack

---

### ❓ **What**
- An **Execution Context (EC)** is an **environment** where JavaScript code is evaluated and executed.  
- It contains information like:
  - **Variable Object (VO)**: Stores variables, function declarations.  
  - **Scope Chain**: Determines variable access.  
  - **this value**: Context of function execution.  
- The **Call Stack** is a **stack data structure** that keeps track of **active execution contexts** in the order they are called.

🧠 In simple words:  
> Execution Context = “Where my code runs”  
> Call Stack = “The order in which my code runs”

---

### 💡 **Why**
- Execution Context ensures every function or block has its **own environment** to run safely.  
- The Call Stack helps **manage multiple function calls** in a predictable way.  
- Helps **track execution order**, avoid conflicts, and handle **nested functions**.  

Without EC and Call Stack, JavaScript **wouldn’t know which function is running or which variables belong where**.

---

### 🕒 **When**
- Created **every time a function is called**.  
- Also created for **global code execution**.  
- Destroyed when a function **finishes execution**, and control returns to the previous context.

---

### 📍 **Where**
- **Global Execution Context (GEC)** – created when a JS file starts executing.  
- **Function Execution Context (FEC)** – created whenever a function is invoked.  
- **Eval Execution Context** – rarely used, created by `eval()` function.  

All contexts exist **inside the Call Stack**, which is maintained by the JavaScript engine (V8, SpiderMonkey, etc.).

---

### 👨‍💻 **Who**
- **JavaScript Engine** creates Execution Contexts automatically.  
- **Developers** trigger new contexts by calling functions.  
- **Users** indirectly trigger contexts by interacting with the webpage (e.g., button clicks).

---

### ⚙️ **How**
#### 1️⃣ Execution Context Creation Phase:
- **Variable Object is created** → stores variables and functions.  
- **Scope Chain is set** → links to outer scopes.  
- **this value** is determined.  

#### 2️⃣ Execution Phase:
- Code runs **line by line**.  
- Variables are assigned values, and functions are executed.  

#### 3️⃣ Call Stack Handling:
- **Global EC** is pushed first.  
- Each **function call** pushes a new EC on top.  
- When function finishes, its EC is **popped off**.  

---

### 🌐 **Real-Time Scenario (Example: YouTube)**
When you watch a video on **[YouTube](https://www.youtube.com)**:  
1. Global EC is created when the page loads.  
2. Clicking the “Play” button creates a **function EC** for the `playVideo()` function.  
3. The Call Stack manages which function runs first:
   - `updateUI()` → updates play button  
   - `fetchVideoData()` → loads video metadata  
   - `displayAds()` → optional function for ads  

The Call Stack ensures functions execute in the **correct order** without conflict.  
After each function completes, its EC is removed, keeping memory clean.

---

### 🧾 **Key Points / Summary**
✅ Global Execution Context is created when JS code starts.  
✅ Function Execution Context is created every time a function is called.  
✅ Execution Context contains **Variable Object, Scope Chain, this**.  
✅ Call Stack manages **order of execution**.  
✅ Helps track **nested function calls** and **execution flow**.

---

### 📚 **Quick Example**
```javascript
function first() {
  console.log("Inside first function");
  second();
}

function second() {
  console.log("Inside second function");
}

first();
console.log("Global code finished");
```
---
# Summary Table (5W1H Overview)
| 🏷️ Category | 💬 Explanation                                                               |
| ------------ | ---------------------------------------------------------------------------- |
| **What**     | The environment where JS code runs and the stack that tracks function calls. |
| **Why**      | To manage execution flow, variables, and function calls safely.              |
| **When**     | When code starts running or a function is called.                            |
| **Where**    | Global or function scope inside the JS engine’s Call Stack.                  |
| **Who**      | JS Engine creates it; developers trigger function calls.                     |
| **How**      | EC created → Code executed → EC removed; Call Stack manages order.           |
---
# 💼 Interview Level – How to Answer in My Own Words

---

## 🗣️ Sample Answer (Short & Confident)

> “**Execution Context** is the environment where JavaScript code runs.  
> Every time a function is called, a **new execution context** is created, containing:
> - **Variables**  
> - **Functions**  
> - **Scope Chain**  
> - **`this` value**  
>
> The **Call Stack** keeps track of which context is currently running and ensures functions execute in order.  
> 
> **Example:** On **YouTube**, when I click Play, the engine creates function contexts for `playVideo`, `updateUI`, and `fetchVideoData`, executes them in order, and removes them once done.”

---


## 🧠 Example One-Liner

> “The **Execution Context** is where JS code runs. Every function call creates a new context, tracked by the **Call Stack**. For instance, clicking Play on **YouTube** creates function contexts for video playback and UI updates, executed in order.”
