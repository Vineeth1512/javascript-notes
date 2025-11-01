# 🔄 Callback Queue & Microtask Queue in JavaScript (5W1H Notes)

---

## ✅ What are Callback Queue & Microtask Queue?

These are **task queues** that store asynchronous callbacks waiting to be executed by the **Event Loop**.

| Queue                          | Used For                                                                      | Priority          |
| ------------------------------ | ----------------------------------------------------------------------------- | ----------------- |
| **Microtask Queue**            | Promises (`then`, `catch`, `finally`), `MutationObserver`, `queueMicrotask()` | ⭐ Higher Priority |
| **Callback (Macrotask) Queue** | `setTimeout`, `setInterval`, DOM events, API callbacks                        | ⭐ Lower Priority  |

---

## ✅ Why do they exist?

JavaScript is **single-threaded** so async tasks cannot run immediately.
These queues help JavaScript:

✔ Avoid blocking the main thread
✔ Improve performance
✔ Maintain smooth UI
✔ Ensure correct async ordering

---

## ✅ Where do they work?

Inside the **JavaScript Runtime Environment** (Browser or Node.js) along with:

* Call Stack
* Event Loop
* Web APIs

---

## ✅ When are they used?

Whenever an async task completes:

* API response returns
* Timer finishes
* DOM event triggers
* Promise resolves

---

## ✅ Who manages them?

🎯 Managed by the **Event Loop** inside the JavaScript Runtime

---

## ✅ How do they work?

1️⃣ Async task runs in **Web APIs** / background

2️⃣ When completed → callback is queued to:

* ✔ **Microtask Queue** → Promises
* ✔ **Callback Queue** → Timers & Events

3️⃣ The **Event Loop** checks:

* If **Call Stack empty** → execute **Microtasks first** ✅
* After completing microtasks → run **Callback Queue** tasks

---

## 🔥 Priority Rule

📌 **Microtasks always execute before Macrotasks**
Even if `setTimeout(() => {}, 0)` — microtasks win ✅

---

## 🧪 Example

```js
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve()
  .then(() => console.log("Promise"));

console.log("End");
```

### ✅ Output

```
Start
End
Promise ✅ (Microtask first)
Timeout ✅ (Callback later)
```

---

## 🌍 Real-Time Analogy

| Queue               | Analogy                     |
| ------------------- | --------------------------- |
| **Microtask Queue** | VIP Queue 🏆 (served first) |
| **Callback Queue**  | Normal Queue 🎫             |

Even if a normal queue person arrives earlier, VIP gets served before them.

---

## 📝 Interview Level Answer

> In JavaScript, asynchronous callbacks go into two types of queues: Microtask and Callback Queue. Promises go into the Microtask Queue which has higher priority, while timers and events go into the Callback Queue. The Event Loop always executes all microtasks first before processing other callbacks, ensuring proper async execution order.

---

## ✅ Quick Summary Table

| Feature          | Microtask Queue              | Callback Queue                           |
| ---------------- | ---------------------------- | ---------------------------------------- |
| Priority         | Higher                       | Lower                                    |
| Contains         | Promises, `MutationObserver` | `setTimeout`, DOM events, AJAX callbacks |
| Execution Moment | After current script         | After microtasks finish                  |
| Managed By       | Event Loop                   | Event Loop                               |

---

