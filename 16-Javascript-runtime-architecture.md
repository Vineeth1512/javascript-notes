# 🏗️ JavaScript Runtime Architecture (5W1H Notes)

---

## ✅ What is JavaScript Runtime?

A **runtime environment** where JavaScript code executes.

It consists of multiple components:

* ✔ Call Stack
* ✔ Memory Heap
* ✔ Event Loop
* ✔ Web APIs
* ✔ Task Queues (Microtask & Callback Queues)

📌 JavaScript alone cannot handle async operations — runtime provides that ability.

---

## ✅ Why does it exist?

Because JavaScript is **single‑threaded** and needs support for:

* Asynchronous tasks (AJAX, DOM events, timers)
* Non‑blocking execution
* Smooth UI and performance

🎯 Purpose: Enable efficient async behavior in JavaScript.

---

## ✅ Where does it work?

Depending on the environment:

| Environment | Example                 | Engine Used              | Extra Support Provided          |
| ----------- | ----------------------- | ------------------------ | ------------------------------- |
| Browser     | Chrome, Firefox, Safari | V8, SpiderMonkey, WebKit | Web APIs (DOM, fetch, timers)   |
| Server      | Node.js                 | V8                       | Node APIs (Filesystem, network) |

---

## ✅ When is it used?

Every time JavaScript executes:

* Rendering UI
* Making API calls
* DOM interaction
* Backend code execution

➡ Runtime **constantly manages** synchronous + asynchronous tasks.

---

## ✅ Who are the main components?

| Component          | Role                                     |
| ------------------ | ---------------------------------------- |
| 🧠 Call Stack      | Executes synchronous code                |
| 📦 Memory Heap     | Stores variables & objects               |
| 🌐 Web APIs        | Executes async work (fetch, DOM, timers) |
| 🧾 Callback Queue  | Holds macrotask callbacks                |
| 🔁 Microtask Queue | Holds Promises and microtasks            |
| 🔄 Event Loop      | Moves tasks to the Call Stack            |

---

## ✅ How does it work? (Flow Diagram)

```
     ┌────────────┐
     │ Call Stack │  ← Executes code
     └─────▲──────┘
           │
   ┌───────┴────────┐
   │ Event Loop      │  ← Coordinator
   └───────▲────────┘
           │
 ┌────────┴─────────┐
 │ Task Queues       │
 │(Micro & Callback) │
 └────────▲─────────┘
          │
 ┌────────┴─────────┐
 │ Web APIs/Node APIs│ ← Async tasks run here
 └───────────────────┘
```

---

## 🧠 Example Execution

```js
console.log("1");

setTimeout(() => console.log("2"), 0);

Promise.resolve().then(() => console.log("3"));

console.log("4");
```

✅ Output Order:

```
1
4
3  ← Microtask Queue first
2  ← Callback Queue second
```

---

## 🌍 Real-Time Scenario – Netflix Example

* UI Rendering → Call Stack + DOM APIs
* Fetch movie details → Web APIs
* Promises updating UI → Microtask Queue
* Video buffering/events → Callback Queue + Event Loop

📌 Without runtime architecture → UI would freeze during streaming.

---

## 📝 Interview‑Level Answer (Your Own Words)

> JavaScript runtime is the environment that executes JavaScript. It includes the call stack, memory heap, event loop, Web APIs, and queues. While JavaScript is single‑threaded, the runtime makes async execution possible. The Event Loop ensures microtasks run before callbacks to maintain correct order.

🔥 Short, clear & impressive for interviews!

---

## ✅ Summary Table

| Feature                    | JS Engine        | Runtime          |
| -------------------------- | ---------------- | ---------------- |
| Handles logic & execution? | ✅ Yes            | ✅ Yes            |
| Handles async tasks?       | ❌ No             | ✅ Yes            |
| Examples                   | V8, SpiderMonkey | Browser, Node.js |

---

