# 🧮 JavaScript – Data Types (5W1H Notes)

---

## 🧩 Topic: JavaScript Data Types

---

### ❓ **What**
JavaScript **data types** define the **kind of values** a variable can hold.  
There are two main categories:
1. **Primitive Data Types** (immutable):
   - Number
   - String
   - Boolean
   - Undefined
   - Null
   - Symbol
   - BigInt
2. **Non-Primitive / Reference Data Types** (mutable):
   - Object
   - Array
   - Function

🧠 In simple words:  
> Data types tell JavaScript **what kind of value** a variable contains and how it should behave.

---

### 💡 **Why**
- To **allocate memory efficiently**.  
- To **perform operations correctly** (e.g., adding numbers vs concatenating strings).  
- To **avoid type-related bugs**.  
- To help **developers understand what values variables hold**.

---

### 🕒 **When**
- Every time a **variable is declared and assigned a value**, a data type is automatically assigned.  
- During **runtime**, JS uses these data types for operations and comparisons.  

---

### 📍 **Where**
- In **browser JavaScript**: variables in scripts, DOM manipulation, user inputs.  
- In **Node.js**: server-side variables, API responses, database operations.

---

### 👨‍💻 **Who**
- **JavaScript engine** assigns data types dynamically (JS is a dynamically typed language).  
- **Developers** interact with and manipulate these types using operators and functions.

---

### ⚙️ **How**
- **Primitive Example:**
```javascript
let name = "Vineeth"; // String
let age = 25;         // Number
let isStudent = true; // Boolean
let salary;           // Undefined
let id = null;        // Null
```
- **Non Primitive Example:**
```
let person = {name: "Vineeth", age: 25}; // Object
let numbers = [1,2,3,4];                // Array
function greet(){console.log("Hi");}    // Function
```
---
# 🧭 Summary Table (5W1H Overview)

| 🏷️ Category | 💬 Explanation                                                   |
| ------------ | ---------------------------------------------------------------- |
| **What**     | Data types define the kind of value a variable can hold.         |
| **Why**      | To allocate memory efficiently and perform operations correctly. |
| **When**     | When variables are declared and assigned values.                 |
| **Where**    | In browser scripts, Node.js, and apps.                           |
| **Who**      | JS engine assigns types; developers use them.                    |
| **How**      | Primitive types (immutable) and Reference types (mutable).       |

---
## 🌐 Real-Time Scenario – Example: Amazon Search


On **Amazon**:

| Data | JavaScript Type |
|------|----------------|
| Product names | `String` |
| Product price | `Number` |
| Availability | `Boolean` |
| User cart | `Array of Objects` |

**Explanation:**  
JavaScript uses these data types to **display products**, **calculate total price**, and **check stock dynamically**.

---

## 🧾 Key Points / Summary

✅ JS is **dynamically typed**, so types are assigned at runtime.  
✅ **Primitive types** are immutable; **Reference types** are mutable.  
✅ Correct usage prevents **runtime errors and bugs**.  
✅ JavaScript is used **everywhere**: frontend, backend, apps, APIs.

---

## 💼 Interview Level – How to Answer in Your Own Words

> “JavaScript has **primitive types** like numbers, strings, booleans, and null, which are immutable,  
> and **reference types** like objects and arrays, which are mutable.  
> 
> **Example:** On **Amazon**, product names are strings, prices are numbers, and the cart is an array of objects.  
> JS automatically assigns types, which helps perform operations correctly.

