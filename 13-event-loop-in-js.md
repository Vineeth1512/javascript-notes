# ⏳ Event Loop in JavaScript (5W1H Notes)

---

## ✅ What is Event Loop?

The **Event Loop** is a mechanism in JavaScript that constantly checks the **Call Stack** and **callback queues** (including the **Microtask Queue**) and decides what to execute next. It enables asynchronous, non-blocking execution in JavaScript.

---

## ✅ Why Event Loop?

JavaScript is **single-threaded** — only one operation executes at a time. The Event Loop allows long-running tasks (like API calls, `setTimeout`, promises) to run asynchronously without blocking other code.

---

## ✅ Where does it work?

Inside the **JavaScript runtime environment**, mainly:

* **Browser** (uses Web APIs)
* **Node.js** (uses libuv / C++ APIs under the hood)

---

## ✅ When does it run?

It runs **continuously** as long as the program is active — always checking:

* Is the Call Stack empty?

  * If **yes** → take the next callbacks from queues and execute them.

---

## ✅ Who controls it?

The **JavaScript runtime environment** controls the Event Loop — not the developer.

---

## ✅ How Event Loop Works (Step-by-step)

1. Normal synchronous code runs → goes to the **Call Stack**.
2. Asynchronous tasks (e.g. `setTimeout`, `fetch`, `Promise`) are handed off to **Web APIs** / background workers.
3. When an async task finishes, its callback is queued in either:

   * **Microtask Queue** (Promises, `MutationObserver`)
   * **Callback (Task) Queue** (e.g. `setTimeout`, DOM events)
4. The **Event Loop** repeatedly checks:

   * Is the **Call Stack** empty?

     * If yes → first execute all tasks in the **Microtask Queue** (drain it)
     * Then execute the next task from the **Callback (Task) Queue**

> Note: Microtasks are drained fully before the event loop processes the next task from the callback queue.

---

## ✅ Priority Order

**Microtask Queue > Callback (Task) Queue**

*Practical takeaway:* **Promise** callbacks run before `setTimeout` callbacks scheduled for the same tick.

---

## 📝 Quick Example

```js
console.log('start');

setTimeout(() => console.log('timeout'), 0);

Promise.resolve().then(() => console.log('promise'));

console.log('end');

// Output:
// start
// end
// promise
// timeout
```

---
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");

## 🔑 Summary

* The Event Loop makes asynchronous JS possible while keeping single-threaded execution.
* Microtasks (Promises) have priority over macrotasks (`setTimeout`, events).
* Understanding the Event Loop helps debug timing and ordering issues in async code.

---

#### 🔁 Simple Diagram 

Call Stack  <-- Executes code
    ↑
Event Loop  <-- Controls execution flow
    ↓
Microtask Queue (High Priority: Promises)
Callback Queue (Low Priority: setTimeout, events)

---
#### ✅ Example: Why Promises run first?

```javascript
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");
```
#### ✅ Output:

```javascript
Start
End
Promise
Timeout
```
📌 Because **Promises (Microtasks)** finish first before **setTimeout (Task queue).**

---
#### ✅ Real-Time Analogy

- **Call Stack** = Kitchen where food is cooked immediately

- **Web APIs** = Assistants doing background tasks

- **Microtask Queue** = VIP customer orders (served first)

- **Callback Queue** = Normal customer orders

- **Event Loop** = Manager who decides what to serve next
