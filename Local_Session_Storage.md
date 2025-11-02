
# ✅ F) Local & Session Storage (Web Storage API)

## 🧠 What is Web Storage API?

It provides browsers with storage that web apps can use to save data **on the client side**.

✅ Stores key–value pairs  
✅ Data is saved in the browser, not on the server  
✅ Faster than cookies  
✅ More storage space (~5–10 MB)

---

## 🌟 Two Types of Storage

| Feature | Local Storage | Session Storage |
|--------|--------------|----------------|
| Lifetime | Until manually cleared | Cleared when tab/window closed |
| Scope | Shared across browser tabs | Tab-specific |
| Capacity | ~10 MB | ~5 MB |
| Accessibility | Same domain pages | Only same tab |
| Auto Expiry | ❌ No | ✅ Yes |

---

## 📌 Common Use Cases

| Local Storage ✅ | Session Storage ✅ |
|----------------|----------------|
| Remember user login | Store OTP data |
| Dark/light theme preference | Temporary selected items |
| Save cart items | Form step progress |
| Save tokens (not recommended for sensitive data) | Page refresh restore |

---

## 🔑 Basic APIs (Very Important)

### ✅ Set Item
```js
localStorage.setItem("name", "Vineeth");
sessionStorage.setItem("token", "abc123");
```

### ✅ Get Item
```js
const name = localStorage.getItem("name");
```

### ✅ Remove Item
```js
localStorage.removeItem("name");
```

### ✅ Clear All Storage
```js
localStorage.clear();
sessionStorage.clear();
```

---

## 📌 Storing Objects (Use JSON)

Because Web Storage only stores strings ✅

```js
const user = { name: "Vineeth", age: 23 };

localStorage.setItem("user", JSON.stringify(user));
```

Reading it back 👇
```js
const userData = JSON.parse(localStorage.getItem("user"));
console.log(userData.name);
```

---

## 🔁 Session Storage Example

```js
sessionStorage.setItem("isLoggedIn", true);
console.log(sessionStorage.getItem("isLoggedIn")); // true
```

When tab is closed → automatically deleted ✅

---

## 📜 Check if Key Exists

```js
if(localStorage.getItem("theme")) {
  console.log("Theme already selected");
}
```

---

## 🔥 Real-Time Project Scenarios

| Project Module | Where Used | Why |
|----------------|-----------|-----|
| E-commerce cart | Local Storage | Persist even after reload |
| Quiz Application | Session Storage | Prevent refresh cheating |
| Blood Donation App | Local Storage Token | Maintains session |
| Dark mode | Local Storage | Permanent user preference |
| Multi-Step Form | Session Storage | Saves state until submit |

---

## ⚠️ Security Notes (Interview Favorite)

✅ Data is stored in **plain text** → 🔥 Not safe for passwords  
🚫 Avoid storing sensitive info like:  
- passwords
- bank details
- JWT refresh tokens

✅ Use **HTTP-only secure cookies** instead for sensitive auth data

---

## 🧠 Memory Flow

➡️ Browser loads website  
➡️ JS stores data in Web Storage  
➡️ Data remains available until  
 • Local Storage → manual delete  
 • Session Storage → tab closed  

---

## 🧪 Interview Questions + Answers

| Question | Answer |
|---------|--------|
| Difference between Local & Session Storage? | Lifetime + scope difference |
| Data type stored? | Only **strings** |
| How to store objects? | JSON.stringify() / JSON.parse() |
| Storage size? | ~5–10 MB |
| Safer than cookies? | Yes (no auto send to server), but still not secure for sensitive data |
| How to clear all? | `.clear()` |

---

## ✅ Summary

| Feature | Local Storage | Session Storage |
|--------|--------------|----------------|
| Permanent | ✅ Yes | ❌ No |
| Per Tab | ❌ No | ✅ Yes |
| Stores String Only | ✅ | ✅ |

---
