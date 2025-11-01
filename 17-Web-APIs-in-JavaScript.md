# 🌐 Web APIs in JavaScript (5W1H Notes)

---

## ✅ What are Web APIs?

Web APIs are **browser-provided features** that extend JavaScript’s capabilities beyond what the language itself can handle.

They support:

* DOM Manipulation
* Timers
* Network/HTTP Requests
* Multimedia
* Browser Storage
* Many other interactive functionalities

📌 JavaScript does **not** include these features natively — **the browser provides them**.

---

## ✅ Why Web APIs?

JavaScript is:

* ✅ Single-threaded
* ✅ Good for logic execution
* ❌ Not designed for async tasks by itself

Web APIs allow:
✔ Non-blocking behavior
✔ Better performance
✔ Real-world user interactions

---

## ✅ Where are Web APIs used?

Inside the **Web Browser Runtime Environment**, not inside the JS engine.

| Browser | Engine         | Web API Provider |
| ------- | -------------- | ---------------- |
| Chrome  | V8             | Blink            |
| Firefox | SpiderMonkey   | Gecko            |
| Safari  | JavaScriptCore | WebKit           |

---

## ✅ When do they execute?

Whenever your code uses browser features:

* Click events → *Event API*
* Server communication → *Fetch API*
* Timers → *Timer API*

---

## ✅ Who provides Web APIs?

✅ Web Browsers (Chrome, Edge, Firefox, Safari)
✅ Node.js provides **Node APIs** (not Web APIs)

---

## ✅ How do Web APIs work?

1️⃣ JS calls a Web API function
2️⃣ Browser executes task in background
3️⃣ After completion → callback moves to:

* Microtask Queue → Promises ✅
* Callback Queue → Timers & Events ✅
  4️⃣ Event Loop pushes tasks to Call Stack when free

---

## 🧩 Example Code

```js
console.log("Start");

setTimeout(() => console.log("Timer Done"), 2000);

fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(() => console.log("Fetched"));

console.log("End");
```

### ✅ Output

```
Start
End
Fetched      ← Microtask Queue first
Timer Done   ← Callback Queue next
```

---

## ✅ Types of Common Web APIs

| API Type        | Examples                                    |
| --------------- | ------------------------------------------- |
| DOM APIs        | `document.getElementById()`, `.innerHTML`   |
| Storage APIs    | `localStorage`, `sessionStorage`, IndexedDB |
| Network APIs    | `fetch()`, `XMLHttpRequest`                 |
| Timer APIs      | `setTimeout()`, `setInterval()`             |
| Event APIs      | `addEventListener()`, `onClick`             |
| Multimedia APIs | `Audio()`, `Video()`, WebRTC                |
| Geolocation API | `navigator.geolocation`                     |
| Canvas API      | 2D/3D drawing                               |

---

## 🌍 Real Website Example — YouTube

* DOM API → update thumbnails & search results
* Fetch API → load video & comments
* Timer API → buffering/stream updates
* Event API → play, pause, scroll

➡ Without Web APIs → No interaction, No dynamic loading

---

## 📝 Interview-Level Answer

> Web APIs are browser-provided capabilities that allow JavaScript to perform asynchronous and interactive operations like DOM manipulation, networking, and timers. They run outside the JS engine and return results via task queues processed by the Event Loop.

🔥 Short, clear & perfect for interviews!

---

## ✅ Summary Table

| Feature              | JavaScript       | Web APIs           |
| -------------------- | ---------------- | ------------------ |
| Provided by          | JS Engine        | Web Browser        |
| Supports async tasks | ❌ No             | ✅ Yes              |
| Example              | Variables, loops | DOM, Fetch, Timers |

---

✅ Markdown conversion complete!
