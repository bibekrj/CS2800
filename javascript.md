# JavaScript Essentials

---

## 1) Basic JavaScript & Linking to HTML

JavaScript adds interactivity and logic to your website. To use it, you need to connect a `.js` file to your HTML page using the `<script>` tag.

**How to link JS in a web page**
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>JS Demo</title>
  </head>
  <body>
    <h1>My Page</h1>

    <!-- Your script should usually go before </body> so the DOM is loaded -->
    <script src="script.js"></script>
  </body>
</html>
```

**Inline vs external**
- External file (`<script src="script.js">`) = reusable, cleaner ✅  
- Inline (`<script> ... </script>`) = quick demos, not great for projects

---

## 1.1) Data Types (Primitives & Objects)

JavaScript handles various types of data, from numbers and text to objects and arrays. Understanding data types helps prevent errors when performing operations.

**Primitives:** `string`, `number`, `boolean`, `null`, `undefined`, `bigint`, `symbol`  
**Objects:** arrays, plain objects, functions, dates, etc.

```js
typeof "hi"        // "string"
typeof 42          // "number"
typeof true        // "boolean"
typeof undefined   // "undefined"
typeof null        // "object"  // historical quirk
typeof {}          // "object"
Array.isArray([])  // true
```

---

## 2) Variable Declaration

Variables store data that your program can use and modify. Use `let` and `const` for modern JavaScript; avoid `var` for better control over scope.

- `const` — **default** for values that won’t be reassigned
- `let` — reassignable
- (Avoid `var` in modern code)

```js
const API_URL = "/data.json";
let count = 0;
count += 1;
```

**Scope:** `let`/`const` are block-scoped; `var` is function-scoped.

---

## 3) Control Statements

Control statements let your code make decisions and execute different blocks depending on conditions. Common types are `if`, `else`, and `switch`.

```js
const score = 78;

if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else {
  console.log("Keep going!");
}

const role = "student";
switch (role) {
  case "admin":   console.log("Welcome, admin"); break;
  case "student": console.log("Welcome, student"); break;
  default:        console.log("Welcome");
}
```

---

## 4) Loops

Loops allow you to repeat tasks automatically without rewriting code. They’re often used to go through arrays or lists of items.

```js
const nums = [10, 20, 30];

for (let i = 0; i < nums.length; i++) {
  console.log(nums[i]);
}

for (const n of nums) {
  console.log(n);
}

nums.forEach((n, i) => {
  console.log(i, n);
});
```

---

## 5) Alerts, Prompts, and Console

These are ways to communicate with users or check what’s happening in your code. Alerts and prompts interact with users; `console.log()` helps with debugging.

```js
alert("Hello!");                // blocking pop-up
const name = prompt("Your name?");
console.log("Hi,", name);       // shows in DevTools console (F12)
```

Use `console.log`, `console.warn`, `console.error` for debugging.

---

## 6) Type Casting

Type casting converts data from one type to another. It’s common when reading user input or dealing with numeric calculations.

**Explicit casting**
```js
Number("123");      // 123
String(99);         // "99"
Boolean("")         // false
Boolean("text")     // true
parseInt("08", 10); // 8
parseFloat("3.14"); // 3.14
```

**Common gotcha**
```js
"5" + 1   // "51"  (string concatenation)
Number("5") + 1  // 6
```

---

## 7) Form Validation (Simple)

Form validation ensures that users enter correct and complete data before submission. It helps prevent errors and improves user experience.

HTML:
```html
<form id="productForm">
  <input id="name" placeholder="Name" required>
  <input id="price" placeholder="Price" type="number" required>
  <input id="qty" placeholder="Quantity" type="number" required>
  <button type="submit">Save</button>
  <p id="error" aria-live="polite"></p>
</form>
```

JS:
```js
const form = document.getElementById("productForm");
const err  = document.getElementById("error");

form.addEventListener("submit", (e) => {
  e.preventDefault();
  const name  = document.getElementById("name").value.trim();
  const price = Number(document.getElementById("price").value);
  const qty   = Number(document.getElementById("qty").value);

  if (!name) { err.textContent = "Name is required."; return; }
  if (!Number.isFinite(price) || price <= 0) { err.textContent = "Price must be > 0."; return; }
  if (!Number.isInteger(qty) || qty <= 0) { err.textContent = "Quantity must be a positive integer."; return; }

  err.textContent = ""; // all good
});
```

---

## 8) DOM & `document.getElementById`

The DOM (Document Object Model) represents the structure of your HTML document. You can access and modify elements using JavaScript functions like `getElementById`.

```js
const title = document.getElementById("title");
title.textContent = "Updated!";

const input = document.getElementById("name");
console.log(input.value);
```

Other handy selectors:
```js
document.querySelector(".class");
document.querySelectorAll("table tr");
```

---

## 9) Declaring Functions vs Assigning to Elements

Functions let you organize and reuse logic. They can be declared independently or attached to elements as event handlers.

**Named (declarative) function**
```js
function calculateTotal(price, qty) {
  return price * qty;
}
```

**Assigning a handler directly**
```js
document.getElementById("saveBtn").onclick = function () {
  console.log("Saved!");
};
```

**Why it’s different**
- A **named function** is reusable and clean.
- `element.onclick` overwrites existing handlers.
- Prefer `addEventListener` to attach multiple listeners safely.

---

## 10) What is a JSON Object?

JSON (JavaScript Object Notation) is a format used to store and share structured data. It looks like a JavaScript object but is stored as a string.

```js
const product = { name: "Pen", price: 1.5, qty: 3 };
const json = JSON.stringify(product);
const back = JSON.parse(json);
```

---

## 11) Store/Retrieve a JSON Value in `localStorage` (Keys & Values)

`localStorage` saves small data directly in the browser, even after the page is closed. It only stores strings, so use `JSON.stringify()` and `JSON.parse()`.

```js
const user = { id: 1, name: "Bibek" };
localStorage.setItem("user", JSON.stringify(user));

const raw = localStorage.getItem("user");
const userObj = raw ? JSON.parse(raw) : null;
```

---

## 12) Store Multiple Items (Array of Objects) to `localStorage`

You can store multiple entries by pushing them into an array and saving that array as one JSON string in `localStorage`.

```js
function saveProduct(prod) {
  const key = "products";
  const list = JSON.parse(localStorage.getItem(key)) || [];
  list.push(prod);
  localStorage.setItem(key, JSON.stringify(list));
}

const prod = { name: "Notebook", price: 2.0, qty: 5, total: 10 };
saveProduct(prod);
```

---

## 13) Retrieve & Display Multiple Items in a Table

This lets you show all stored data visually on your web page. You can loop through the array and create a table row for each item.

```js
function renderProducts() {
  const key = "products";
  const rows = JSON.parse(localStorage.getItem(key)) || [];
  const tbody = document.querySelector("#productTable tbody");
  tbody.innerHTML = "";

  rows.forEach(p => {
    const tr = document.createElement("tr");
    tr.innerHTML = `
      <td>${p.name}</td>
      <td>${Number(p.price).toFixed(2)}</td>
      <td>${p.qty}</td>
      <td>${Number(p.total).toFixed(2)}</td>
    `;
    tbody.appendChild(tr);
  });
}

document.addEventListener("DOMContentLoaded", renderProducts);
```

