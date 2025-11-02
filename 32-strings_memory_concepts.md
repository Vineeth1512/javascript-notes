
# JavaScript Strings – Memory Concepts (Stack vs Heap + Immutability)

## 1️⃣ Strings are Primitives stored in Stack
- Primitive values store **actual value** in stack memory.
- Each variable gets its own copy.

```js
let a = "Hello";
let b = a;
```

| Variable | Memory Type | Value |
|---------|-------------|------|
| a | Stack | "Hello" |
| b | Stack | "Hello" (copied) |

---

## 2️⃣ Actual String Value Internally Stored in Heap (Optimization)
JavaScript uses **String Pooling** — avoids duplicate heap entries.

```js
let x = "JS";
let y = "JS";
```

- `"JS"` stored **once**
- `x` & `y` reuse heap memory

---

## 3️⃣ Strings are Immutable
Once created → cannot change.

```js
let name = "Vineeth";
name = "Kumar"; // New string created
```

| Result |
|--------|
| Original string stays in heap until GC |
| New string assigned in stack |

Reasons for immutability:
- Security
- Performance optimization
- Safe sharing across memory

---

## 4️⃣ String Operations Create New Strings
```js
let s = "Hello";
s += " World"; // New string created
```

Avoid heavy concatenation → prefer:
- template literals
- `array.join("")`

---

## 5️⃣ References vs Value Copy
```js
let a = "Hi";
let b = a;
b = "Bye";
```
✅ Changing `b` does NOT affect `a`.

---

## ✅ Interview Quick Answers
| Question | Answer |
|---------|--------|
| Are strings mutable? | ❌ No, they are immutable |
| Where are primitives stored? | ✅ Stack |
| Does same string duplicate in memory? | ❌ No, pooled in heap |
| Changing string modifies original? | ❌ Creates new string |

---

### ✅ Summary Table
| Concept | Status |
|--------|--------|
| Primitive | ✅ |
| Stack storage | ✅ |
| Heap internal pooling | ✅ |
| Immutable | ✅ |

---

> 🔥 Key: Strings in JS are **primitive, stack-stored, immutable** with **heap optimization**
