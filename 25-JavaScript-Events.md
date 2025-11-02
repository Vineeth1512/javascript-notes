# ✅ JavaScript Events — Attractive Notes

## 📌 What is an Event?

An **event** is an action that happens in the browser.

✅ User clicks a button  
✅ Mouse moves  
✅ Keyboard key pressed  
✅ Page loaded  
✅ Form submitted  

➡️ JavaScript listens for events and executes a **callback function** 🎯

---

## 🔔 Event Types

| Category | Examples |
|---------|----------|
| Mouse Events | click, dblclick, mouseover, mouseout |
| Keyboard Events | keydown, keyup, input |
| Form Events | submit, change, focus, blur |
| Window Events | load, resize, scroll |
| Clipboard Events | copy, paste |

---

## 🎯 `addEventListener()` — Best Way ✅

✅ Modern Standard  
✅ Multiple listeners allowed  
✅ Can remove listener  

```js
element.addEventListener("event", callback);
```

📌 Example:
```js
btn.addEventListener("click", () => {
  console.log("Button clicked!");
});
```

---

## 🧠 Event Object (`event` / `e`)

Every event gives full details:

```js
button.addEventListener("click", (e) => {
  console.log(e.target); // element clicked
});
```

| Property | Meaning |
|----------|---------|
| e.target | Element that triggered event |
| e.type | Event type (click, input, etc.) |
| e.clientX/Y | Mouse position |

---

## ✅ Prevent Default Behavior

Prevents browser action like page refresh on form submit 👇

```js
form.addEventListener("submit", (e) => {
  e.preventDefault();
  console.log("Form Submitted!");
});
```

Disable link navigation:
```js
link.addEventListener("click", e => e.preventDefault());
```

---

## 📌 Event Propagation (Bubbling & Capturing)

📌 Phases  
1️⃣ Capturing → Top → Target  
2️⃣ Target  
3️⃣ Bubbling → Target → Top ✅ (Default)

Example:
```html
<div id="parent">
  <button id="child">Click Me</button>
</div>
```
```js
parent.addEventListener("click", () => console.log("Parent"));
child.addEventListener("click", () => console.log("Child"));
```
✅ Output: **Child → Parent**

Capturing mode:
```js
parent.addEventListener("click", () => console.log("Parent"), true);
```
Output: **Parent → Child**

---

## 🔥 Event Delegation

✔ Listen on *parent*  
✔ Detect *child* element via `e.target`  
✔ Perfect for dynamic elements! 🚀

Example:
```js
document.addEventListener("click", (e) => {
  if(e.target.classList.contains("delete-btn")){
    e.target.closest(".card").remove();
  }
});
```

Benefits:  
✅ Performance boost  
✅ Future elements supported

---

## 🪝 Removing Event Listeners

```js
function greet() {
  console.log("Hello!");
}

button.addEventListener("click", greet);
button.removeEventListener("click", greet);
```
⚠️ Works only with **named functions**

---

## 🚦 Keyboard Events

```js
input.addEventListener("keydown", (e) => {
  console.log(e.key);
});
```

Used for: Login forms ✅, Search ✅, Games 🎮

---

## 📌 Auto Remove Event Listener

```js
btn.addEventListener("click", () => {
  alert("Clicked only once!");
}, { once: true });
```

---

## 🌐 Window Events

```js
window.addEventListener("scroll", () => {
  console.log("Scrolling...");
});
```

Used for: Sticky navbar ✅, Lazy loading ✅, Animations ✅

---

## ✅ Real-Time Project — Mobile Menu

```js
menu.addEventListener("click", () => {
  nav.classList.toggle("open");
});
```

Event + DOM Manipulation = Responsive UI ✨

---

## 📝 Quick Interview Notes

| Question | Best Answer |
|---------|-------------|
| Bubbling vs Capturing? | Bubbling: bottom → top ✅ (default), Capturing: top → bottom |
| What is event delegation? | Parent handles child events using e.target |
| Why `addEventListener` instead of `onclick`? | Multiple handlers + remove possible |
| stopPropagation() | Stops bubbling/capturing |
| preventDefault() | Prevents browser action (e.g., form submit refresh) |

---

✨ End of Notes — You’re Learning Smart! 🚀
