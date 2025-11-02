# 🔀 DOM Traversal — Moving Through the DOM Tree

## ✅ What is DOM Traversal?

DOM Traversal means **navigating the DOM structure** to find related elements such as:
- Parent of an element
- Children of an element
- Next or previous siblings
- Nearest matching ancestor

📌 Useful when:
✔ Selected element alone is not enough  
✔ We need to move **up/down/sideways** in DOM

---

## 🧭 1️⃣ Parent Traversal

| Property | Description |
|----------|-------------|
| `parentNode` | Can return ANY parent node

---
## 🌿 2️⃣ Children Traversal

| Property     | Returns        | Includes Text Nodes? |
| ------------ | -------------- | :------------------: |
| `children`   | HTMLCollection |         ❌ No         |
| `childNodes` | NodeList       |         ✅ Yes        |

✅ Recommended: `children`

```js const list = document.querySelector("ul");
console.log(list.children.length);
```
Other child properties:
```js
list.firstElementChild;
list.lastElementChild;
console.log(list.firstElementChild.textContent);

```
## 🔁 3️⃣ Sibling Traversal

| Property                        | Moves To         | Node Type       |
| ------------------------------- | ---------------- | --------------- |
| `nextElementSibling`            | Next sibling     | Element only ✅  |
| `previousElementSibling`        | Previous sibling | Element only ✅  |
| `nextSibling / previousSibling` | Any node         | ❌ Includes text |


```js
const secondItem = document.querySelector("li:nth-child(2)");
console.log(secondItem.nextElementSibling); // 3rd li
```
✅ Best Practice: Use `nextElementSibling` / `previousElementSibling`

## 🎯 4️⃣ closest() — Best for Finding Parent by Selector

| Method              | Behavior                                               |
| ------------------- | ------------------------------------------------------ |
| `closest(selector)` | Finds nearest ancestor element matching the selector ✅ |

```js

const btn = document.querySelector(".delete-btn");
const card = btn.closest(".card");
card.remove();
```
✅ Excellent for event delegation
❌ Searches **only upward**, not downward

## 🔍 5️⃣ querySelector() Inside an Element
You can search inside a selected element:

```js const card = document.querySelector(".card");
const title = card.querySelector(".title");
console.log(title.textContent);
```
📌 Prevents selecting wrong elements when multiple exist

## 🧠 Bonus: Advanced Tree Navigation

| Property                        | Description                     |
| ------------------------------- | ------------------------------- |
| `parentElement.querySelector()` | Search inside a specific parent |
| `offsetParent`                  | Nearest positioned ancestor     |
| `.remove()`                     | Remove selected element         |


## 🧪 Real-Time Example – Active Navigation Highlight

```js document.querySelectorAll("nav li").forEach(item => {
  item.addEventListener("click", () => {
    item.parentElement
        .querySelector(".active")
        ?.classList.remove("active");
    
    item.classList.add("active");
  });
});
```

📌 Uses `parentElement` + `querySelector` for controlled traversal ✅

---

## ✅ Real-Time Example – Remove Card Button

```HTML

<div class="card">
  <h2>Item</h2>
  <button class="remove">Remove</button>
</div>
```

```JavaScript

document.addEventListener("click", (e) => {
  if(e.target.classList.contains("remove")){
    e.target.closest(".card").remove();
  }
});
```

📌 closest() makes this reusable for many cards ✅
