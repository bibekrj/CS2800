# 🎨 CSS Basics: Properties, Selectors & Layout Cheat Sheet

CSS (Cascading Style Sheets) is used to **style HTML elements** — control layout, colors, fonts, spacing, and more.

---

## 🧱 1. CSS Structure & Syntax

```css
selector {
  property: value;
}
```

Example:

```css
p {
  color: blue;
  font-size: 16px;
}
```

- **Selector** → Targets the HTML element(s)
- **Property** → What you want to change
- **Value** → How you want it changed

You can include CSS in three ways:

```html
<!-- Inline -->
<p style="color: red;">Hello</p>

<!-- Internal -->
<style>
  p { color: red; }
</style>

<!-- External -->
<link rel="stylesheet" href="styles.css" />
```

---

## 🧠 2. CSS Selectors

### Basic Selectors

| Selector | Example | Description |
|----------|---------|-------------|
| Element | `p {}` | Targets `<p>` elements |
| Class | `.btn {}` | Targets elements with `class="btn"` |
| ID | `#main {}` | Targets element with `id="main"` |
| Universal | `* {}` | Targets all elements |
| Grouping | `h1, h2, h3 {}` | Targets multiple selectors |

### Combinators

| Selector | Example | Meaning |
|----------|---------|---------|
| Descendant | `div p` | Selects `<p>` inside `<div>` |
| Child | `div > p` | Selects direct children only |
| Adjacent sibling | `h1 + p` | First `<p>` after `<h1>` |
| General sibling | `h1 ~ p` | All `<p>` after `<h1>` |

### Pseudo-classes

| Selector | Example | Description |
|----------|---------|-------------|
| `:hover` | `a:hover` | When mouse hovers |
| `:active` | `button:active` | When clicked |
| `:focus` | `input:focus` | When focused |
| `:nth-child(n)` | `li:nth-child(2)` | 2nd child |
| `:first-child` | `p:first-child` | First child |
| `:last-child` | `p:last-child` | Last child |

### Pseudo-elements

| Selector | Example | Description |
|----------|---------|-------------|
| `::before` | `p::before` | Content before element |
| `::after` | `p::after` | Content after element |
| `::first-letter` | `p::first-letter` | First letter styling |
| `::selection` | `::selection` | Text selection styling |

---

## 🌈 3. Colors, Units & Typography

### Colors

```css
color: red;
color: #ff0000;
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);
```

### Units

| Type | Example | Description |
|------|---------|-------------|
| Absolute | `px`, `cm`, `mm`, `in` | Fixed sizes |
| Relative | `%`, `em`, `rem`, `vw`, `vh` | Scale with parent or viewport |

### Typography

```css
font-family: "Arial", sans-serif;
font-size: 1.2rem;
font-weight: bold;
text-align: center;
text-transform: uppercase;
line-height: 1.5;
letter-spacing: 2px;
```

---

## 📦 4. The Box Model

Every element is a box consisting of:

```
+---------------------------+
|        margin             |
|  +---------------------+  |
|  |      border         |  |
|  |  +---------------+  |  |
|  |  |   padding     |  |  |
|  |  | +----------+  |  |  |
|  |  | | content  |  |  |  |
|  |  | +----------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

```css
.box {
  margin: 10px;
  border: 2px solid black;
  padding: 15px;
  width: 200px;
  height: 100px;
  box-sizing: border-box;
}
```

| Property | Description |
|----------|-------------|
| `margin` | Space **outside** the element |
| `border` | Edge line around the element |
| `padding` | Space **inside**, between content & border |
| `width` / `height` | Content box size |
| `box-sizing` | `border-box` includes padding & border in total size |

---

## 🧭 5. Positioning & Display

### Display Types

| Value | Description |
|-------|-------------|
| `block` | Takes full width (e.g. `<div>`) |
| `inline` | Flows within text (e.g. `<span>`) |
| `inline-block` | Inline but accepts width/height |
| `flex` | Enables flexbox layout |
| `grid` | Enables grid layout |
| `none` | Hides element |

### Positioning

| Value | Description |
|-------|-------------|
| `static` | Default |
| `relative` | Offset relative to itself |
| `absolute` | Positioned relative to nearest ancestor |
| `fixed` | Fixed to viewport |
| `sticky` | Scrolls then sticks |

Example:

```css
.box {
  position: absolute;
  top: 10px;
  left: 20px;
}
```

---

## 🧰 6. Flexbox Basics

Flexbox is great for **1D layouts** (row or column).

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}
```

| Property | Values | Description |
|----------|--------|-------------|
| `display` | `flex` | Enables flex layout |
| `flex-direction` | `row` \| `column` | Layout direction |
| `justify-content` | `center`, `space-between`… | Align **main axis** |
| `align-items` | `center`, `flex-start`… | Align **cross axis** |
| `gap` | `10px` | Space between items |

---

## 📝 7. Common Properties

### Background

```css
background-color: lightblue;
background-image: url('bg.jpg');
background-repeat: no-repeat;
background-size: cover;
```

### Borders & Radius

```css
border: 1px solid #333;
border-radius: 10px;
```

### Shadows

```css
box-shadow: 2px 4px 8px rgba(0,0,0,0.2);
text-shadow: 1px 1px 2px black;
```

### Overflow

```css
overflow: hidden;
overflow: auto;
```

---

## 🧠 8. Shorthand & Variables

### Shorthand

```css
/* Instead of separate properties */
margin: 10px 20px 15px 5px; /* top right bottom left */

/* border */
border: 2px dashed red;

/* background */
background: url(bg.jpg) no-repeat center/cover;
```

### CSS Variables

```css
:root {
  --main-color: #007bff;
  --padding: 10px;
}

button {
  background-color: var(--main-color);
  padding: var(--padding);
}
```

---

## 📱 9. Media Queries

Responsive design for different screen sizes:

```css
@media (max-width: 600px) {
  body {
    background-color: lightgray;
  }
}
```

- `max-width`: Apply when screen is **below** size
- `min-width`: Apply when screen is **above** size

---

## ✨ 10. Transitions & Animations

### Transitions

```css
button {
  background: blue;
  color: white;
  transition: background 0.3s ease;
}

button:hover {
  background: darkblue;
}
```

### Keyframe Animation

```css
@keyframes bounce {
  0% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
  100% { transform: translateY(0); }
}

.ball {
  animation: bounce 1s infinite;
}
```

---

## ✅ Quick Summary Table

| Category | Key Concepts |
|----------|--------------|
| Syntax | Selector `{ property: value; }` |
| Selectors | Elements, class `.class`, ID `#id`, pseudo |
| Units | px, %, em, rem, vw, vh |
| Colors | names, hex, rgb, rgba |
| Box Model | margin, border, padding, content |
| Layout | display, position, flexbox |
| Common Properties | background, border, shadow, overflow |
| Responsive | media queries |
| Fancy | transitions, animations, variables |

---
