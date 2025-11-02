# 🧱 JavaScript Objects 

## ✅ 1️⃣ What is an Object?

JavaScript **Object** is a data structure used to store data in **key–value pairs**.

```js
let person = {
  name: "Vineeth",
  age: 24,
  city: "Hyderabad"
};
```

📌 Keys → Properties  
📌 Values → Data  
📌 Order does **not** matter

---

## ✅ 2️⃣ Why Objects?

| Reason | Benefit |
|--------|---------|
| Store complex data | Easy handling of real-world entities |
| Group related info | Structured data |
| Dynamic | Add/remove/update anytime |
| Methods inside | Behaviors + Data together |

Example representing a **real entity**:

```js
let car = {
  brand: "BMW",
  start() { console.log("Engine Started"); }
};
```

---

## ✅ 3️⃣ When to use Objects?

✔ When storing entity-based information  
✔ When data has **attributes + behavior**  
✔ When accessing values by name  

---

## ✅ 4️⃣ Where are Objects used?

📌 API responses  
📌 User profiles  
📌 Cart items in e-commerce  
📌 Configuration settings  
📌 Local Storage data  
📌 JSON communication  

Example API Response:

```js
fetch("url")
  .then(res => res.json())
  .then(data => console.log(data));
```

---

## ✅ 5️⃣ How to Create Objects? (5 Ways)

| Method | Example |
|--------|---------|
| Object Literal ✅ | `let obj = {}` |
| new Object() | `let obj = new Object()` |
| Constructor Function | `function User(){}` |
| ES6 Class | `class User {}` |
| Object.create() | Prototype based |

```js
const user = {};
user.name = "Vineeth";
```

---

# 🎛 Object Access Methods

```js
console.log(person.name);   // Dot notation
console.log(person["city"]); // Bracket notation
```

✔ Brackets used when key has spaces or dynamic value

---

# 🧩 Add / Update / Delete Properties

```js
person.email = "vineeth@email.com"; // Add
person.age = 25; // Update
delete person.city; // Delete
```

---

# 🚀 Object Methods

```js
let student = {
  name: "Kumar",
  greet() {
    console.log(`Hello ${this.name}`);
  }
};

student.greet();
```

📌 `this` refers to the object calling the method

---

# 🔍 Looping Through Objects

```js
for (let key in person) {
  console.log(key, person[key]);
}
```

---

# 📌 Object Utility Methods

| Method | Purpose |
|--------|---------|
| Object.keys(obj) | Array of keys |
| Object.values(obj) | Array of values |
| Object.entries(obj) | Array of key–value pairs |
| Object.assign() | Copy/merge objects |
| Object.freeze() | Prevent updates |
| Object.seal() | Modify allowed, add/remove not allowed |

Example:

```js
let copy = Object.assign({}, person);
```

---

# 🔁 Nested Objects

```js
let profile = {
  details: {
    name: "Vineeth",
    skills: ["JS", "React"]
  }
};

console.log(profile.details.skills[1]);
```

---

# 🌍 JSON — Very Important!

📌 JSON = JavaScript Object Notation  
📌 Used in APIs, DBs, Config files

```js
let data = '{"name":"Vineeth"}';

let obj = JSON.parse(data);  // Convert JSON → Object
let str = JSON.stringify(obj); // Object → JSON
```

---

# 🧠 Object vs Array

| Feature | Object | Array |
|--------|--------|-------|
| Order | Not guaranteed | Ordered |
| Access | Keys | Index |
| Best for | Entities | Lists |

---

# ✅ Real-time Examples

```js
let cartItem = {
  id: 101,
  product: "Laptop",
  price: 65000,
  qty: 1
};

console.log(cartItem.price * cartItem.qty);
```

---

# 🧪 Interview Q&A

✔ What is an Object in JS?  
➡ Collection of key–value pairs stored as reference type.

✔ Why typeof null returns object?  
➡ A JavaScript **bug** from 1995, never fixed.

✔ Difference: `==` vs `===` for objects  
➡ Always compared by **reference**.

```js
{} === {} // false
```

✔ What is `this` in an object?  
➡ Refers to the object calling the method.

---

# 🏁 Summary

✔ Objects store data in key:value pairs  
✔ Best for representing entities  
✔ Methods define behavior  
✔ Used everywhere in real-world applications  

---
