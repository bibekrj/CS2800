# 📝 CS 2800 — Final Project  
**Assignment:** Multi-Page Website with Local Storage  
**Due:** Nov 21, 2025. 11:59 PM   
**Weight:** Refer Syllabus


## 📌 Overview
In this project, you’ll build a **multi-page storefront website** using **HTML**, **CSS**, and **JavaScript** (no frameworks). Your site should include a product browsing experience, a cart, and a checkout form that uses `localStorage` to persist data.

You’re expected to make the project **your own** — modify the layout, design, product data, and interactivity creatively while still meeting the core requirements.

---

## 🧱 Project Structure Requirements

Your project must include at least:

1. **Multiple HTML pages**, including:  
   - `index.html` (storefront)  
   - `product.html` (product details)  
   - `cart.html` (shopping cart)  
   - `checkout.html` (form with validation + draft saving)

2. **External CSS file** (`/css/styles.css`)  
   - Shared styling across pages  
   - Custom layout or design modifications encouraged

3. **External JavaScript files**, split logically, e.g.:  
   - `storage.js` for all localStorage logic  
   - `app.js` for rendering products, handling cart, checkout, etc.

4. **Consistent navigation** (e.g., header/footer) across all pages.

---

## 🛍️ Functional Requirements

Your website must allow users to:

- **Browse products** on the storefront (dynamic rendering from an array or external JSON).  
- **View product details** and add them to the cart.  
- **Add/remove/update items** in the cart, with totals updating dynamically.  
- **Persist cart contents** using `localStorage`.  
- **Fill out a checkout form** with basic validation (e.g., required fields, email format, ZIP code).  
- **Auto-save** form data to `localStorage` (draft saving) and allow draft loading or clearing.

---

## 🎨 Design & UX Requirements

- Use CSS to create a **cohesive, readable, and responsive layout**.  
- You may start from the provided styles but are encouraged to modify:
  - Colors / theme  
  - Typography  
  - Grid layout for products  
  - Card design or buttons
- Ensure your design remains **accessible** and **semantic** (e.g., proper use of headings, labels, alt text).

---

## 💡 Creative Freedom

You are encouraged to:

- Change the **theme** (e.g., bookstore, game shop, art gallery, etc.)  
- Add more product fields (e.g., rating, category, SKU)  
- Implement filtering, search, or sorting features  
- Include subtle animations or transitions  
- Make the checkout form more detailed (e.g., shipping options, payment mockup)  
- Fetch product data from an external `.json` file using `fetch()`  

> Your project should reflect your **personal design choices and coding style**, while meeting the functional and structural expectations.

---

## ✅ Minimum Technical Expectations

- Semantic, valid HTML  
- Proper use of external CSS & JS (no inline `<style>` or `<script>` for main logic)  
- Clear separation of concerns (e.g., business logic vs DOM manipulation vs storage)  
- Code that runs without console errors  
- Form validation and `localStorage` usage demonstrated

---

## 📂 Submission

- Submit by pushing it to GitHub Final Project Repository.
- Include a short `README.md` describing your theme, features, and any creative additions.

---

## 🧮 Grading Breakdown

| Component                     | Points |
|-------------------------------|--------|
| Project structure             | 10     |
| Functionality & interactivity | 25     |
| Form & validation             | 15     |
| CSS design                    | 20     |
| Code organization & clarity   | 15     |
| Creativity / extra features   | 15     |
| **Total**                     | 100    |
