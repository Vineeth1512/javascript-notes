
# 🚀 ES6+ Features (Modern JavaScript)

## ✅ 1️⃣ let & const (Block Scope)
```js
let x = 5;
const y = 10;
```
- let → block scope
- const → block scope + no reassignment

---

## ✅ 2️⃣ Arrow Functions
```js
const add = (a, b) => a + b;
```

---

## ✅ 3️⃣ Template Literals
```js
const name = "Vineeth";
console.log(`Hello, ${name}!`);
```

---

## ✅ 4️⃣ Default Parameters
```js
function greet(name = "Guest"){}
```

---

## ✅ 5️⃣ Spread Operator
```js
const arr2 = [...arr1, 3,4];
```

---

## ✅ 6️⃣ Rest Parameter
```js
function sum(...nums){}
```

---

## ✅ 7️⃣ Destructuring
```js
const {name, age} = user;
```

---

## ✅ 8️⃣ Classes
```js
class Person{ constructor(name){ this.name = name; }}
```

---

## ✅ 9️⃣ Modules (import/export)
```js
export const msg = "Hello";
import { msg } from "./file.js";
```

---

## ✅ 10️⃣ Promises (all, race, any, allSettled)

---

## ✅ 11️⃣ async / await
```js
async function fetchData(){ await fetch(url); }
```

---

## ✅ 12️⃣ Map & Set
```js
const set = new Set([1,2,2]);
```

---

## ✅ 13️⃣ Optional Chaining
```js
console.log(user?.address?.city);
```

---

## ✅ 14️⃣ Nullish Coalescing
```js
const x = null ?? "default";
```

---

### ✅ Summary Table
| Feature | Why Used? |
|--------|------------|
| let/const | Block scope + safer |
| Arrow functions | Short + no own this |
| Spread/Rest | Merge & split values |
| Destructuring | Quick extraction |
| async/await | Cleaner async code |
| Optional chaining | Prevent null errors |
| Nullish Coalescing | Better default handling |
