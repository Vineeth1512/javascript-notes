
# ✅ JavaScript BOM (Browser Object Model) 

## 🧠 What is BOM?

BOM (Browser Object Model) allows JavaScript to interact with the **browser itself** (not the web page).

➡️ It provides objects that control browser features like:  
✅ Navigation  
✅ Window popup control  
✅ URL control  
✅ Browser history  
✅ Screen & device information  

➡️ BOM = `window` object + its properties  
➡️ All BOM objects are part of global `window`

---

## 🔥 BOM vs DOM — Interview Favorite

| Feature | BOM | DOM |
|--------|-----|-----|
| Controls | Browser features | Web page content |
| Root object | `window` | `document` |
| Example | alert(), history.back() | getElementById() |
| Use Case | Navigation, dimensions | Read/modify HTML elements |

✅ DOM is inside BOM → `window.document`

---

## 🧱 BOM Main Objects (Root = window)

| BOM Object | Description |
|-----------|-------------|
| `window` | Global browser window |
| `document` | Represents webpage (DOM) |
| `location` | URL related info & actions |
| `history` | Browser navigation history |
| `navigator` | Browser/device info |
| `screen` | Screen resolution info |
| `console` | Logging |
| `localStorage` / `sessionStorage` | Web storage |

---

## ✅ window Object (Global Object)

```js
window.alert("Hello!");
alert("Hello!"); // same
```

### ✅ Timer Methods
```js
setTimeout(() => console.log("Once"), 2000);
setInterval(() => console.log("Repeated"), 1000);
```

### ✅ Popup Controls
```js
confirm("Are you sure?");
prompt("Enter your name");
```

---

## 🌍 Location Object

Used for URL info + redirections

```js
console.log(location.href);
console.log(location.hostname);
console.log(location.pathname);
```

### ✅ Redirect Page
```js
location.href = "https://google.com";
```

### ✅ Reload Page
```js
location.reload();
```

---

## 🕘 History Object

```js
history.back();  // Back to previous page
history.forward(); // Next page
history.go(-1); // Same as back()
```

⚠️ Cannot see actual history list (security)

---

## 🧭 Navigator Object  

Returns browser + device details

```js
console.log(navigator.userAgent);
console.log(navigator.language);
console.log(navigator.onLine); // true/false
```

Example: Detect Offline

```js
if(!navigator.onLine) {
  alert("You are offline!");
}
```

---

## 🖥️ Screen Object  

Used for screen resolution detection

```js
console.log(screen.width, screen.height);
```

Useful in responsive behavior or full-screen UI

---

## ✅ Console Object

✅ Debugging tool

```js
console.log("Info");
console.error("Error");
console.warn("Warning");
```

---

## 🎯 Real-Time Scenarios & BOM Usage

| Scenario | BOM Feature Used |
|---------|-----------------|
| Prevent refresh cheating | sessionStorage |
| Force navigation to login | location.href |
| Detect offline mode | navigator.onLine |
| Open support popup | window.open() |
| Redirect after logout | location.replace() |
| Check user's screen for UI | screen.width |

---

## 🔥 window.open()

```js
const newWin = window.open("https://chatgpt.com", "_blank", "width=500,height=400");
```

Close popup

```js
newWin.close();
```

---

## 🧠 Interview Questions

| Question | Best Answer (Short) |
|---------|-------------------|
| What is BOM? | JavaScript interface to control browser features |
| BOM root object? | window |
| Difference between BOM & DOM? | DOM = webpage elements, BOM = browser control |
| Example BOM Objects? | location, history, navigator, screen |
| Purpose of navigator? | Browser/device & online status |
| URL redirection method? | location.href |

---

## 📝 Summary

✔ BOM = window + browser control objects  
✔ Helps with URL, history, popups, tabs, browser detection  

---
