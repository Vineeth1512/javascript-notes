
# 🔄 JavaScript Promise Combinators — 5W1H Notes

✅ `Promise.all()` | `Promise.race()` | `Promise.any()`

---

## 1️⃣ ✅ Promise.all()

### 🧠 What?

Executes multiple Promises **in parallel** and returns result **only when all are resolved**.

### 🤔 Why?

To get **all required data** before continuing.

### 🕘 When?

When **all API calls are mandatory** for a result.

### 🌍 Where Used? (Example)

E-commerce → Fetch:
✔ Product
✔ Price
✔ Reviews
→ Then show product page ✅

### 👤 Who Uses?

Web developers → dashboards, multi-data loading, parallel requests

### 🔧 How?

```js
Promise.all([fetchUser(), fetchOrders(), fetchWishlist()])
  .then(results => console.log(results))
  .catch(error => console.log("Failed:", error));
```

✅ Runs fast (parallel)
⚠ If **any fails** → entire Promise.all() **fails** ❌

---

## 2️⃣ ⚡ Promise.race()

### 🧠 What?

Returns the **first completed** Promise
(✅ resolved or ❌ rejected → both count)

### 🤔 Why?

Speed-priority logic (timeout or fallback server)

### 🕘 When?

First server response wins ✅

### 🌍 Real Example

Backup API strategy:

```js
Promise.race([
  fetch("https://api1.com"),
  fetch("https://backup-api.com")
])
.then(res => console.log("Winner:", res))
.catch(err => console.log("Error:", err));
```

✅ Fastest response wins
⚠ Rejection also wins → use carefully

---

## 3️⃣ 🎯 Promise.any()

### 🧠 What?

Returns **first successful** Promise ✅
❌ Ignores failures completely

### 🤔 Why?

Always give user a working response even if some fail

### 🕘 When?

Multiple API replicas / CDN fallback logic

### 🌍 Real Example

Video streaming first-available CDN:

```js
Promise.any([
  fetch("https://cdn1.com/video"),
  fetch("https://cdn2.com/video"),
  fetch("https://cdn3.com/video")
])
.then(res => console.log("Loaded:", res))
.catch(err => console.log("All failed!", err));
```

⚠ Fails only if **all** fail → `AggregateError`

---

## 🧩 All Three — Quick Comparison Table

| Feature       | Promise.all()        | Promise.race()      | Promise.any()      |
| ------------- | -------------------- | ------------------- | ------------------ |
| Returns       | When **all succeed** | **First completed** | **First success**  |
| If one fails? | ❌ Entire thing fails | ✅ Still returns     | ❌ Only if all fail |
| Use Case      | Required data        | Speed priority      | Best success       |
| Performance   | Fast (parallel)      | Fastest             | First success wins |

---

## 🔥 Real-World Web Scenarios

| Website         | Use Case                    | Combinator     |
| --------------- | --------------------------- | -------------- |
| ✅ Amazon        | Product + price + stock     | Promise.all()  |
| ✅ YouTube       | Video from fastest CDN      | Promise.any()  |
| ✅ Google Search | Fastest microservice result | Promise.race() |
| ✅ Netflix       | Subtitles + metadata        | Promise.all()  |

---

## 🧠 Interview Answer (In Your Own Words ✅)

**`Promise.all()`** waits for all promises and fails if any fails.
**`Promise.race()`** returns whichever finishes first (success or fail).
**`Promise.any()`** returns the first success and ignores failures.
Used for **parallel async operations** to improve performance.

✅ Clean
✅ Keyword-rich
✅ Interview-ready

---

## ✅ Summary Table

| Topic               | One Line Answer ✅   |
| ------------------- | ------------------- |
| Promise.all()       | Wait for all        |
| Promise.race()      | First response wins |
| Promise.any()       | First success wins  |
| Best Error Handling | `.any()` ✅          |
| Mandatory APIs      | `.all()` ✅          |
| Speed Priority      | `.race()` ✅         |

---
