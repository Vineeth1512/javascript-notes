
# ✅  Form & Input DOM Handling

## 🧠 What is Form & Input Handling in DOM?

It refers to **accessing**, **reading**, **validating**, and **submitting** form input data using JavaScript.

JavaScript allows you to:

✅ Get input values  
✅ Validate before submitting  
✅ Show error messages  
✅ Dynamically enable/disable buttons  
✅ Prevent invalid form submissions  

---

## 📌 Ways to Access Form & Input Elements

### 1️⃣ Using `document.forms`
```js
const form = document.forms["registerForm"];
const username = form["username"].value;
```

### 2️⃣ Using `getElementById()`
```js
const email = document.getElementById("email").value;
```

### 3️⃣ Using `querySelector()`
```js
const password = document.querySelector("#password").value;
```

---

## 🔍 Reading & Setting Values

```js
const input = document.getElementById("name");

console.log(input.value); // read
input.value = "Vineeth"; // set
```

---

## ✅ Form Submission Handling

Prevent form from submitting in case of errors using `event.preventDefault()`:

```js
document.getElementById("myForm").addEventListener("submit", function(e) {
  e.preventDefault();
  console.log("Form submitted!");
});
```

---

## 🔐 Input Validation

### Example: Check if empty

```js
function validate() {
  const name = document.getElementById("name").value;

  if(name.trim() === "") {
    alert("Name is required!");
    return false;
  }
  return true;
}
```

### Email Validation (Regex)

```js
function validateEmail(email){
  return /^\S+@\S+\.\S+$/.test(email);
}
```

---

## 🔁 Realtime Input Validation (`input` event)

```js
const pwd = document.getElementById("password");
pwd.addEventListener("input", () => {
  if(pwd.value.length < 6) {
    pwd.style.borderColor = "red";
  } else {
    pwd.style.borderColor = "green";
  }
});
```

---

## ✅ Checking Checkbox & Radio Status

```js
const isChecked = document.getElementById("accept").checked;
console.log(isChecked); // true/false
```

```js
const gender = document.querySelector("input[name='gender']:checked").value;
console.log(gender);
```

---

## 📌 Select Dropdown Handling

```js
const city = document.getElementById("city");
console.log(city.value);
```

---

## ⭐ Useful DOM Form Properties

| Property | Meaning |
|---------|---------|
| `value` | Current input value |
| `checked` | For checkbox/radio selection |
| `disabled` | Disable input |
| `selectedIndex` | Dropdown selected option index |
| `files` | Uploaded file list |
| `focus()` | Focus cursor into input |
| `reset()` | Reset all fields |

Example:

```js
document.getElementById("myForm").reset();
```

---

## 🛑 Required + Custom Error Messages (Constraint API)

```html
<input id="age" type="number" required min="18" max="60">
```

JS Custom Message:
```js
const age = document.getElementById("age");
age.addEventListener("invalid", () => {
  age.setCustomValidity("Age must be between 18–60!");
});
```

---

## 🧪 FormData — Very Important!

Used to send form data to backend (AJAX)

```js
const form = document.getElementById("myForm");
const data = new FormData(form);

for (let pair of data.entries()) {
  console.log(pair[0] + ": " + pair[1]);
}
```

---

## 🎯 Real-Time Scenarios (Interview Level)

| Scenario | How DOM helps |
|---------|----------------|
| Login form | Validate username & password before submit |
| Signup | Check mobile number/email format, match passwords |
| Payment form | Disable submit button until all info valid |
| Search box | Show suggestions while typing |

---

## 🧠 Quick Interview Questions

| Question | Expected Answer |
|---------|----------------|
| What is `preventDefault()`? | Stops form from submitting automatically |
| How to get selected radio button? | `querySelector("input[name='x']:checked").value` |
| What is FormData used for? | Collect & send form values programmatically |
| How to validate email? | Regex + `.test()` method |

---
