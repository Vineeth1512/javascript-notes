
# 🚀 JavaScript ES6+ Features — Detailed Notes

ECMAScript 2015 (ES6) introduced major enhancements to JavaScript, followed by ES7, ES8, ES9, etc. Below are the most important ES6+ features explained with examples:

---

## ✅ 1️⃣ let & const — Block Scope, Hoisting & TDZ

### ✨ Block Scope
```js
if (true) {
  let x = 10;
  const y = 20;
}
console.log(x); // ❌ Error: x is not defined
```

### 🧠 TDZ (Temporal Dead Zone)
Variables exist but are not accessible before declaration.
```js
console.log(a); // ❌ ReferenceError
let a = 5;
```

### ✅ const = Constant Reference
```js
const arr = [1, 2, 3];
arr.push(4);   // ✅ allowed  
arr = [5, 6];  // ❌ not allowed (reassignment)
```

📌 Best Practice → Use **const** by default & **let** only when value changes.

---

## ✅ 2️⃣ Arrow Functions — Short & Smart ✅
```js
const add = (a, b) => a + b;
console.log(add(2, 3)); // Output: 5
```

🔥 Auto-bind `this`
```js
const person = {
  name: "Vineeth",
  greet: function () {
    setTimeout(() => {
      console.log(this.name); // ✅ Correct `this`
    }, 500);
  }
};
person.greet();
```

✅ Best for callbacks & array methods  
❌ Not for object methods or constructors

---

## ✅ 3️⃣ Template Literals — Backtick Magic
```js
let name = "Vineeth";
let age = 22;
console.log(`Hi I am ${name} and my age is ${age}`);
```
✔ Multi-line  
✔ Variable embedding  

---

## ✅ 4️⃣ Default Parameters
```js
function greet(name = "Guest") {
  return `Hello ${name}`;
}
console.log(greet()); // Hello Guest ✅
```

---

## ✅ 5️⃣ Spread Operator — Expands Values
### Array Example
```js
const nums = [1, 2, 3];
const more = [...nums, 4, 5];
console.log(more);
```

### Object Example
```js
const user = { name: "Vineeth" };
const updated = { ...user, age: 22 };
console.log(updated);
```

📌 Very useful in **React state updates**

---

## ✅ 6️⃣ Rest Parameter — Packs Arguments
```js
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b);
}
console.log(sum(1,2,3,4)); // 10
```

⚡ Opposite of Spread Operator

---

## ✅ 7️⃣ Destructuring — Fast Extraction
### Object Example
```js
const user = { name: "Vineeth", age: 22 };
const { name, age } = user;
console.log(name, age);
```

### Array Example
```js
const colors = ["red", "green", "blue"];
const [first, , last] = colors;
console.log(first, last);
```

---

## ✅ 8️⃣ Classes — Blueprint for Objects
```js
class Person {
  constructor(name){
    this.name = name;
  }
  speak(){
    console.log(`Hi, I'm ${this.name}`);
  }
}
const p = new Person("Vineeth");
p.speak();
```

📌 Behind the scenes → Still uses prototypes

---

### ✅ Quick Revision Chart ✅

Feature | Why Used?
------- | ----------
let / const | Modern variable declarations
Arrow Functions | Cleaner functions + lexical this
Template Literals | Dynamic strings & multi-line
Spread / Rest | Expand & collect values smartly
Destructuring | Cleaner access to data
Classes | Better OOP syntax

---

✨ ES6 = Modern, Clean & Interview Favorite Questions ✅

---

> Save this & revise before every interview! 🔥🚀


## ✅ 9️⃣ Modules (import / export)

### 🔹 Named Export
```js
// file.js
export const name = "Vineeth";
export function greet(){ return "Hello"; }
```

### 🔹 Import
```js
import { name, greet } from "./file.js";
console.log(name);      // Output: Vineeth
console.log(greet());   // Output: Hello
```

📌 Helps in maintaining reusable, clean code architecture.

---

## ✅ 🔟 Promises — Async Operations Handler

```js
const data = new Promise((resolve) => {
  resolve("Data Loaded");
});

data.then(result => console.log(result));
// Output: Data Loaded
```

### 🔹 Promise Combinators
| Method | Behavior |
|--------|----------|
| Promise.all() | Wait for all ✅ but fails if any ❌ |
| Promise.race() | First resolved/rejected result |
| Promise.any() | First resolved ✅ ignores failures |
| Promise.allSettled() | Returns results regardless success/fail |

---

## ✅ 1️⃣1️⃣ async / await — Cleaner Promises

```js
async function fetchData() {
  return "Server Response";
}
fetchData().then(console.log);
// Output: Server Response
```

With await:
```js
async function display() {
  const result = await fetchData();
  console.log(result);
}
display();
// Output: Server Response
```

📌 Makes async code look synchronous.

---

## ✅ 1️⃣2️⃣ Map & Set

### 🔹 Set: Unique Values
```js
const items = new Set([1, 2, 2, 3]);
console.log(items); 
// Output: Set {1, 2, 3}
```

### 🔹 Map: Key-Value, Any Type keys
```js
const user = new Map();
user.set("name", "Vineeth");
console.log(user.get("name"));
// Output: Vineeth
```

📌 Better than plain objects for large data lookup.

---

## ✅ 1️⃣3️⃣ Optional Chaining (?.)

```js
const user = { profile: { name: "Vineeth" } };
console.log(user?.profile?.name);  
// Output: Vineeth
console.log(user?.address?.city);
// Output: undefined ✅ (No crash)
```

📌 Prevents runtime `undefined` errors.

---

## ✅ 1️⃣4️⃣ Nullish Coalescing (??)

```js
const result = null ?? "Default";
console.log(result);
// Output: Default
```

Difference from `||`:
```js
console.log(0 || "fallback"); // fallback ❌
console.log(0 ?? "fallback"); // 0 ✅
```

---

## ✅ 1️⃣5️⃣ Symbols — Unique Hidden Keys

```js
const sym = Symbol("id");
const obj = { [sym]: 101 };
console.log(obj[sym]);
// Output: 101
```

📌 Not enumerable → good for private object fields

---

## ✅ 1️⃣6️⃣ Iterators & Generators

```js
function* counter(){
  yield 1;
  yield 2;
}
const c = counter();
console.log(c.next().value); // 1
console.log(c.next().value); // 2
```

📌 Used in data streams, infinite sequences.

---

## ✅ 1️⃣7️⃣ Enhanced Object Literals

```js
let name = "Vineeth";
let user = { name, greet(){ return "Hi"; } };
console.log(user.greet());
// Output: Hi
```

---

## ✅ 1️⃣8️⃣ for...of Loop

```js
for (const n of [10,20,30]) console.log(n);
// Output: 10 20 30
```

📌 Works on iterable values (Arrays, Maps, Sets)

---

## ✅ 1️⃣9️⃣ BigInt — Large Numbers

```js
const big = 12345678901234567890n;
console.log(big + 10n);
// Output: 12345678901234567900n
```

---

## ✅ Summary Cheat Sheet

| Feature | Real-Time Use |
|--------|----------------|
| Modules | Code splitting, frontend structure |
| Promises | API calls, async tasks |
| Map/Set | Data filtering, caching, tracking states |
| Optional Chaining | Safe nested property access |
| Symbols | Secure object properties |
| Async/Await | Modern API development |

---

### 🎯 You are now strong in Modern JavaScript ES6+ 🚀


