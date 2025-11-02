# ✨ JavaScript Strings — Detailed Notes (5W1H + Examples)

## ✅ 1️⃣ What is a String?
A **String** is a **sequence of characters** enclosed in quotes.

```js
let name = "Vineeth";
let city = 'Hyderabad';
let message = `Hello JS`; // Template Literal
```

📌 Strings are **immutable** → once created, cannot be changed in memory.

---

## ✅ 2️⃣ Why use Strings?
Used to represent **textual data** such as:

- Names
- Emails
- Messages
- API responses
- Search functionality

---

## ✅ 3️⃣ When to use Strings?
Whenever working with **characters / text processing**

Examples:
✅ Form validation → email, password  
✅ Display UI text  
✅ Search and filtering  
✅ Chat messaging  

---

## ✅ 4️⃣ Where Strings are used?
📌 Everywhere in UI & backend communication

Example:
```js
let age = 25;
console.log("Age: " + age);
```

---

## ✅ 5️⃣ How to create Strings?

| Method | Example |
|--------|---------|
| Using quotes ✅ | `"Hello"` `'Hi'` |
| Template literals ✅ | ``Hello ${name}`` |
| new String() ❌ | `new String("Hello")` |

```js
typeof "Hello"      // "string"
typeof new String() // "object"
```

---

## 📌 String Properties & Indexing
```js
let str = "JavaScript";
console.log(str.length); // 10
console.log(str[0]); // J
console.log(str.charAt(4)); // S
```

✅ Index starts from 0  
✅ Strings are **read-only**

---

## 🎯 Common String Methods

| Method | Purpose |
|--------|---------|
| toUpperCase() | Convert to uppercase |
| toLowerCase() | Convert to lowercase |
| trim() | Remove extra spaces |
| includes() | Search substring |
| indexOf() | First index |
| lastIndexOf() | Last index |
| slice() | Extract substring by index |
| substring() | Similar to slice |
| replace() | Replace characters |
| split() | Convert string → array |

Example:
```js
"JavaScript".toUpperCase();
```

---

## 🧠 Template Literals — Powerful
- Support variables inside string ✅
- Support multi-line ✅

```js
let name = "Vineeth";
console.log(`Welcome ${name} to JavaScript!`);
```

---

## 🔍 Search & Replace with Regex
```js
"Hello JS".match(/JS/);
"Hello JS".replace(/JS/, "World");
```

---

## 🔁 Loop Through Strings
```js
for (let char of "JS") {
  console.log(char);
}
```

---

## 🧹 Immutability — Important!
```js
let s = "ABC";
s[0] = "Z";
console.log(s); // "ABC" ❌ no change
```

📌 A new string is created behind the scenes.

---

## 🧪 Conversion to String
```js
String(100); // "100"
(100).toString(); // "100"
100 + ""; // "100"
```

---

## ✅ Real-Time Example — Masking
```js
let card = "1234567812345678";
console.log(card.slice(-4).padStart(card.length, "*"));
// ************5678
```

---

## 🧠 Interview Q&A

**Q: Why are strings immutable?**  
➡ Security, memory optimization, and performance.

**Q: slice() vs substring()?**  
➡ `slice()` supports negative indexes, `substring()` doesn't.

**Q: What does length count?**  
➡ UTF-16 code units.

**Q: "5" + 2 output?**  
➡ "52" (string concatenation)

---

## 🏁 Summary
✔ Strings store characters  
✔ Immutable in nature  
✔ Many built-in powerful methods  
✔ Template literals make dynamic strings easier  

---

✅ End of Notes ✅
