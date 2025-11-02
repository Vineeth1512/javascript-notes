# 🧮 JavaScript Arrays — 

## ✅ 1️⃣ What is an Array?

A JavaScript **Array** is a **data structure** used to store multiple values in a **single variable**, ordered by **index**.

```js
let fruits = ["Apple", "Banana", "Mango"];
```

📌 Index starts from **0**  
📌 Arrays can store **different data types**

```js
let mixed = [10, "Hi", true, { name: "Vineeth" }];
```

---

## ✅ 2️⃣ Why use Arrays?

| Feature | Benefit |
|--------|---------|
| Group related data | Clean & organized coding |
| Dynamic size | You can add/remove items anytime |
| Built-in methods | Fast and easy operations |
| Iterable | You can loop through items |

---

## ✅ 3️⃣ When to use Arrays?

✔ When storing a list of data  
✔ When order matters  
✔ When accessing elements by index

Example:
```js
let scores = [95, 87, 90];
console.log(scores[1]); // 87
```

---

## ✅ 4️⃣ Where Arrays are used?

📌 E-commerce → product list  
📌 Social Media → posts, comments  
📌 Navigation menus  
📌 Form inputs storage  
📌 API data

---

## ✅ 5️⃣ How Arrays Work Internally?

- Stored in **contiguous** memory but dynamic resizing handled by JS engine  
- Elements accessed using **index**  
- Array is technically an **object** with key-value pairs

```js
console.log(typeof []); // object
```

---

# 📌 Array Creation Methods

| Syntax | Example |
|--------|---------|
| Literal | `let arr = [1,2,3]` |
| Constructor | `let arr = new Array(3)` |
| Empty array | `let arr = []` |

---

# 🔁 Array Common Methods (Most Used)

## ✅ Add / Remove elements

| Method | Description | Example |
|--------|-------------|---------|
| `push()` | Add to end | `arr.push(10)` |
| `pop()` | Remove from end | `arr.pop()` |
| `unshift()` | Add to beginning | `arr.unshift(5)` |
| `shift()` | Remove from beginning | `arr.shift()` |
| `splice()` | Add/remove in middle | `arr.splice(2, 1)` |

---

## 🔍 Search Methods

| Method | What it does |
|--------|--------------|
| `indexOf()` | Find index |
| `includes()` | Check existence |
| `find()` | Returns matching element |
| `findIndex()` | Returns index of match |

---

## 🎛 Transform Methods

| Method | Mutates Original? | Description |
|--------|------------------|-------------|
| `map()` | ❌ No | Convert each element |
| `filter()` | ❌ No | Filter based on condition |
| `reduce()` | ❌ No | Combine into one value |
| `slice()` | ❌ No | Copy part of array |
| `splice()` | ✅ Yes | Add/remove elements |

---

## 🔄 Looping Methods

| Method | Output |
|--------|--------|
| `forEach()` | Iterates (no return) |
| `map()` | New array |
| `for…of` | Direct element access |
| `for…in` | Index/keys |

---

# 🧠 Spread & Rest with Arrays

```js
let a = [1,2];
let b = [...a, 3,4]; // spread
console.log(b);

function test(...numbers) { // rest
  console.log(numbers);
}
```

---

# 🧹 Copy vs Reference

```js
let a = [1,2];
let b = a; 
b.push(3);
console.log(a); // [1,2,3] ❌ (reference copy)

// ✅ Correct way (clone)
let c = [...a];
```

---

# ✅ Real Time Example

📌 YouTube: List of recommended videos  
📌 Netflix: Continue Watching list  
📌 Food Delivery: Items in cart

```js
let cart = [];
cart.push("Burger");
cart.push("Pizza");
console.log(cart); // ["Burger", "Pizza"]
```

---

# 🧪 Interview Q&A

✅ Q: Is an Array in JS Hetrogeneous or Homogeneous?  
✔ Heterogeneous — supports multiple data types.

✅ Q: What is difference between `forEach()` vs `map()`?  
✔ `map()` returns a new array, `forEach()` doesn't.

✅ Q: Why typeof array returns object?  
✔ Arrays are a special type of **object** with numeric keys.

---
