# 🧭 JavaScript Control Statements (5W1H Notes)

---

## 🧩 Topic: JavaScript Control Statements

---

### ❓ **What**
**Control Statements** in JavaScript are instructions that **control the flow of execution** of a program based on certain conditions or repetitions.

🧠 In simple terms:  
> Control statements decide **which code to run**, **when**, and **how many times** it should run.

They include:
- **Conditional statements** → `if`, `else if`, `else`, `switch`
- **Looping statements** → `for`, `while`, `do...while`
- **Jump statements** → `break`, `continue`, `return`

---

### 💡 **Why**
- To make your program **interactive and dynamic**.  
- To **execute code selectively** based on conditions.  
- To **repeat actions efficiently** using loops instead of writing repetitive code.  
- To **control when to stop or skip iterations**.

---

### 🕒 **When**
- When you want to perform **different actions** based on a condition.  
- When you need to **repeat a task** multiple times (like iterating over an array).  
- When you want to **exit a loop early** or **skip certain iterations**.

---

### 📍 **Where**
- Used in **decision-making logic**, **loops**, and **functions**.  
- Commonly used in:
  - Form validation scripts.
  - Dynamic rendering in React.
  - Backend API logic.
  - Game development and UI interactions.

---

### 👨‍💻 **Who**
- **Developers** write control statements to manage logic flow.  
- **JavaScript Engine** executes them sequentially or conditionally.

---

### ⚙️ **How**

#### 🔸 1️⃣ Conditional Statements
Used to execute code blocks based on specific conditions.

```javascript
let marks = 85;

if (marks >= 90) {
  console.log("Grade: A+");
} else if (marks >= 75) {
  console.log("Grade: A");
} else {
  console.log("Grade: B");
}
```
#### 🔸 2️⃣ Switch Statement

Used when you have **multiple possible values** to check for the same variable.
```javascript
let day = "Saturday";

switch (day) {
  case "Monday":
    console.log("Start of work week");
    break;
  case "Saturday":
  case "Sunday":
    console.log("Weekend! 🎉");
    break;
  default:
    console.log("Midweek hustle");
}
```
#### 🔸 3️⃣ Looping Statements

**a) For Loop**
```javascrit
for (let i = 1; i <= 5; i++) {
  console.log("Count:", i);
}
```

**b) While Loop**
```javascrit
let num = 1;
while (num <= 3) {
  console.log("Number:", num);
  num++;
}
```


**c) Do...While Loop**

```javascrit
let count = 1;
do {
  console.log("Executed at least once:", count);
  count++;
} while (count <= 3);
```

#### 🔸 4️⃣ Jump Statements

Used to **change the flow** of loops or functions.
```javascrit
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue; // skip 3
  if (i === 5) break;    // stop at 5
  console.log(i);
}
```
---

##### 🌐 Real-Time Scenario (Example: YouTube Auto-Play Logic)

On YouTube control statements are used for autoplay and ad skipping logic
```javascrit
   let videosWatched = 0;

while (videosWatched < 3) {
  console.log("Playing video...");
  videosWatched++;

  if (videosWatched === 2) {
    console.log("Ad will play next");
    continue; // skip to next iteration without autoplay
  }
}
```
🎥 Here:

- While loop controls video playback.

- Continue skips certain iterations (like ad breaks).

- If condition checks when to trigger ads or autoplay.

---

# 🧭 Summary Table (5W1H Overview)
| 🏷️ Category | 💬 Explanation                                                           |
| ------------ | ------------------------------------------------------------------------ |
| **What**     | Statements that control the flow of execution.                           |
| **Why**      | To execute code conditionally or repeatedly.                             |
| **When**     | When logic needs decision-making or iteration.                           |
| **Where**    | In loops, conditions, and function logic.                                |
| **Who**      | Developers write them; JS engine executes them.                          |
| **How**      | Using `if`, `switch`, `for`, `while`, `do...while`, `break`, `continue`. |

---


## 🧾 Key Points / Summary

✅ **Control statements** direct the flow of program execution.  
✅ Include **conditional**, **looping**, and **jump** statements.  
✅ Make your code **efficient**, **dynamic**, and **logical**.  
✅ Used everywhere — from **form validation** to **API handling**.  
✅ Enable **decision-making** and **automation** in web applications.  

---

## 🗣️ Interview Level – How to Answer in My Own Words

> “Control statements in JavaScript decide the flow of execution.  
> They include `if-else`, `switch`, loops, and jump statements.  
> For example, **YouTube** uses them to handle autoplay and ad logic.  
> These statements help execute code based on conditions and repeat tasks efficiently.”
