# 🎯 DOM Access Methods 

## ✅ Why Do We Need DOM Access Methods?
To **read, modify, style, delete, or add elements**, JavaScript must first locate the element from the DOM Tree.

👉 These methods help target the correct node.

---

## 🏷️ 1️⃣ getElementById()

| Feature | Value |
|--------|------|
| Returns | Single Element |
| Type | Element Object |
| Live update? | ✅ Yes |
| Speed | ⚡ Fastest selector |

Example:
```js
const heading = document.getElementById("title");
heading.style.color = "red";
```
📌 ID must be **unique** in a page.

## 🧪 2️⃣ getElementsByClassName()

| Feature      | Value                                  |
| ------------ | -------------------------------------- |
| Returns      | HTMLCollection (Live)                  |
| Access       | Index-based like array                 |
| Loop Support | ✅ Yes (convert to array or use for-of) |

```js
const buttons = document.getElementsByClassName("btn");
buttons[0].textContent = "Clicked!";
```
## 🔖 3️⃣ getElementsByTagName()

| Feature  | Value                                |
| -------- | ------------------------------------ |
| Returns  | HTMLCollection (Live)                |
| Best for | Selecting all `li`, `p`, `div`, etc. |

```js
const items = document.getElementsByTagName("li");
console.log(items.length);
```

## 🎯 4️⃣ querySelector()

| Feature       | Value                      |
| ------------- | -------------------------- |
| Returns       | First matching element     |
| Selector Type | CSS Selectors (powerful ✅) |

```js
const card = document.querySelector(".product-card");
```

More CSS selector examples:
```js
document.querySelector("#title");
document.querySelector(".btn.primary");
document.querySelector("ul li:first-child");
```
---
## 🎯 5️⃣ querySelectorAll()


| Feature  | Value                    |
| -------- | ------------------------ |
| Returns  | NodeList (Static ❌ Live) |
| Looping  | ✅ has forEach()          |
| Best Use | Select multiple elements |

```js
document.querySelectorAll("li").forEach(item => {
  console.log(item.textContent);
});
```

## 🔥 HTMLCollection vs NodeList (Interview Favorite)

| Property                |    HTMLCollection   |           NodeList          |
| ----------------------- | :-----------------: | :-------------------------: |
| Returned by             | class/tag selectors |       querySelectorAll      |
| Live update?            |        ✅ Yes        |             ❌ No            |
| Supports forEach?       |         ❌ No        |            ✅ Yes            |
| Contains only elements? |        ✅ Yes        | ❌ Can include comments/text |

---

## 🧭 6️⃣ DOM Root Selectors

| Method                     | Use             |
| -------------------------- | --------------- |
| `document.documentElement` | Select `<html>` |
| `document.head`            | Select `<head>` |
| `document.body`            | Select `<body>` |

```js
document.body.style.background = "#111";
```
## ☑️ 7️⃣ Form-based Selector

| Method           | Use                                           |
| ---------------- | --------------------------------------------- |
| `document.forms` | Select all `<form>` elements by index or name |

```js
document.forms[0].submit();
```
## 🧑‍💻 Real-Time Example — Highlight Active Menu

```js
const navLinks = document.querySelectorAll(".nav a");

navLinks.forEach(link => {
  link.addEventListener("click", () => {
    document.querySelector(".active")?.classList.remove("active");
    link.classList.add("active");
  });
});
```
✅ Result: Active menu changes → Modern UX

## ⚠️ Common Interview Questions

| ❓ Question                                            | ✅ Short Answer                          |
| ----------------------------------------------------- | --------------------------------------- |
| Which is faster: `getElementById` or `querySelector`? | `getElementById()`                      |
| What does `querySelectorAll` return?                  | Static NodeList                         |
| HTMLCollection vs NodeList?                           | NodeList supports forEach & is not live |
| Can we chain `getElementById`?                        | ❌ No, returns a single element          |
