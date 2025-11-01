# 🧠 JavaScript Call Stack (5W1H Notes)

---

## ✅ What is Call Stack?

The **Call Stack** is a data structure in JavaScript that stores and controls the execution order of functions.

📌 It follows the principle: **LIFO → Last In, First Out**

---

## ✅ Why Call Stack?

Because JavaScript is **single-threaded**, meaning it can execute only **one task at a time**.

The Call Stack helps JavaScript:

* ✔ Keep track of function execution
* ✔ Manage the flow from one function to another
* ✔ Return control once execution completes

---

## ✅ Where does it work?

Inside the **JavaScript Engine**

* Example: **Google V8 Engine** (Chrome, Node.js)

---

## ✅ When is it used?

Every time a function is invoked, the engine:
1️⃣ Pushes the function into the **Call Stack**
2️⃣ Executes the function
3️⃣ Pops it out once completed

This continues **until the entire program finishes execution**.

---

## ✅ Who manages the Call Stack?

🧠 Controlled and managed by the **JavaScript Engine**

* e.g., **V8** (Chrome/Node.js), **SpiderMonkey** (Firefox)

---

## ✅ How does it work? (Execution Flow)

1. The **Global Execution Context** is pushed first
2. Each function call creates a **new Stack Frame** and is pushed on top
3. After execution, it is removed (popped)
4. If stack becomes empty → Program ends ✅

---

## 🔔 Key Notes

* If too many functions stack up without ending → ❌ **Stack Overflow Error**
* The Call Stack only handles **synchronous** code

---

✅ Example

```js
function a() {
  b();
}
function b() {
  console.log("Hello!");
}
a();
```

📌 Execution order in Call Stack:
1️⃣ Global Context
2️⃣ a()
3️⃣ b()
→ b() completes → popped out
→ a() completes → popped out
→ Program ends

---

### 🏁 Summary

| Feature    | Description                       |
| ---------- | --------------------------------- |
| Purpose    | Controls function execution order |
| Works On   | LIFO principle                    |
| Managed By | JavaScript Engine                 |
| Handles    | Only synchronous tasks            |

---
####  🔁 Example Code
```javascript
function A() {
  console.log("Inside A");
  B();
}

function B() {

  console.log("Inside B");
}

A();
console.log("End");
```
#### ✅ Execution Order:

| Step | Action        | Call Stack         |
| ---- | ------------- | ------------------ |
| 1    | Start Program | Global()           |
| 2    | Call A()      | A(), Global()      |
| 3    | Call B()      | B(), A(), Global() |
| 4    | B() finishes  | A(), Global()      |
| 5    | A() finishes  | Global()           |
| 6    | Program ends  | (Empty)            |

---

#### ✅ Summary Table
| Topic      | Key Point                 |
| ---------- | ------------------------- |
| Type       | LIFO (Last In First Out)  |
| Used for   | Function execution order  |
| Managed by | JavaScript Engine         |
| Overflow   | Too many recursive calls  |
| Visibility | Only top element executed |
