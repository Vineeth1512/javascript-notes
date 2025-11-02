# ✨ DOM Manipulation 

DOM Manipulation = Changing the structure, content, and style of a webpage dynamically using JavaScript.

- ✅ Update Text
- ✅ Change Styles
- ✅ Add / Remove Elements
- ✅ Apply Animations
- ✅ Real-time UI Updates

🏗️ 1️⃣ Content Manipulation

| Property      | What it does      | Allows HTML? | Shows Hidden Text? |
| ------------- | ----------------- | ------------ | ------------------ |
| `textContent` | Gets/Sets text    | ❌            | ✅                  |
| `innerText`   | Visible text only | ❌            | ❌                  |
| `innerHTML`   | Gets/Sets HTML    | ✅            | ✅                  |

```js
title.textContent = "Welcome!";
message.innerHTML = "<strong>Success!</strong>";
```
#### ⚠️ Security Alert:
Avoid `innerHTML` with user input → XSS attack risk ❌
## 🧩 2️⃣ Attribute Manipulation

| Action       | Method                      |
| ------------ | --------------------------- |
| Add / Update | `setAttribute(attr, value)` |
| Read         | `getAttribute(attr)`        |
| Remove       | `removeAttribute(attr)`     |

```js
img.setAttribute("src", "photo.png");
console.log(img.getAttribute("alt"));
link.removeAttribute("href");

```
✨ Shortcut:
```js
input.id = "emailInput";
```

## 🎨 3️⃣ Style Manipulation

```js
element.style.color = "red";
element.style.backgroundColor = "yellow";

```
❌ Not recommended for multiple styles (inline clutter)
✅ Better → Use `classList` for CSS control ✅

## 🏷️ 4️⃣ Class Manipulation (Best Practice)

| Method       | Purpose       |
| ------------ | ------------- |
| `add()`      | Add class     |
| `remove()`   | Remove class  |
| `toggle()`   | Switch ON/OFF |
| `contains()` | Check class   |

```js
button.classList.toggle("active");
```
Used for:
✔ Dark Mode Toggle | ✔ Sidebar Open/Close | ✔ Form Validation

## 🧱 5️⃣ Creating Elements

```js
const div = document.createElement("div");
div.textContent = "New Element";

```

## 🔌 6️⃣ Inserting Elements

| Method          | Position       |
| --------------- | -------------- |
| `append()`      | Inside end     |
| `prepend()`     | Inside start   |
| `before()`      | Before element |
| `after()`       | After element  |
| `appendChild()` | Old method     |

```js
const list = document.querySelector("ul");
const li = document.createElement("li");
li.textContent = "Item Added";
list.append(li);
```
## ❌ 7️⃣ Removing Elements
```js
element.remove();

```
🕹️ Old (Backward Compatible):
```js
element.parentElement.removeChild(element);
```
## ⚙️ 8️⃣ Replace Element
```js
oldElement.replaceWith(newElement);
```
---
## 🎯 Interview Questions (Quick Answers)

| Question                    | Best Answer                                               |
| --------------------------- | --------------------------------------------------------- |
| innerHTML vs textContent?   | `innerHTML` parses HTML — `textContent` is plain text ✅   |
| append vs appendChild?      | append → multiple nodes/strings, appendChild → only nodes |
| Why classList.toggle?       | Perfect for menus/themes — ON/OFF behavior                |
| createElement vs innerHTML? | createElement is safer/faster for multiple updates        |
| Why DocumentFragment?       | Avoids multiple reflows → better performance ✅            |

## ✅ Quick Summary Table
| Feature                | Best Method          |
| ---------------------- | -------------------- |
| Modify text            | `textContent`        |
| Insert HTML            | `innerHTML`          |
| Multiple style changes | `classList`          |
| Add element inside end | `append()`           |
| Insert before element  | `before()`           |
| Remove element         | `remove()`           |
| Batch DOM updates      | `DocumentFragment` ✅ |
