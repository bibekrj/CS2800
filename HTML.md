# 📄 HTML Basics: Tags & Elements Cheat Sheet

HTML (HyperText Markup Language) is the standard language for creating webpages. It uses **tags** to structure content.

---

## 🧱 1. Document Structure

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My First Page</title>
    <meta charset="UTF-8" />
    <meta name="description" content="Basic HTML example" />
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

| Tag | Description |
|-----|-------------|
| `<!DOCTYPE html>` | Defines HTML5 document type |
| `<html>` | Root of the document |
| `<head>` | Metadata, links, scripts (not visible) |
| `<title>` | Title of the page (appears in tab) |
| `<meta>` | Extra information (charset, SEO, viewport) |
| `<link>` | Link external resources like CSS |
| `<body>` | Main visible content |

---

## 📝 2. Text Elements

```html
<h1>Main Heading</h1>
<h2>Sub Heading</h2>
<p>This is a paragraph.</p>
<strong>Important text</strong>
<em>Emphasized text</em>
<br />
<hr />
```

| Tag | Description |
|-----|-------------|
| `<h1>`–`<h6>` | Headings, H1 is largest |
| `<p>` | Paragraph |
| `<strong>` | Bold (semantically strong) |
| `<em>` | Italic (emphasized) |
| `<br>` | Line break |
| `<hr>` | Horizontal line |

---

## 🔗 3. Links and Images

```html
<a href="https://www.example.com" target="_blank">Visit Example</a>

<img src="image.jpg" alt="Description of image" width="200" />
```

| Tag | Description |
|-----|-------------|
| `<a>` | Hyperlink |
| `<img>` | Embed image (no closing tag) |
| `href` | URL of the link |
| `src` | Image source |
| `alt` | Alternative text (accessibility) |

---

## 📋 4. Lists

### Unordered List
```html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
</ul>
```

### Ordered List
```html
<ol>
  <li>First</li>
  <li>Second</li>
</ol>
```

### Description List
```html
<dl>
  <dt>HTML</dt>
  <dd>Standard markup language</dd>
</dl>
```

| Tag | Description |
|-----|-------------|
| `<ul>` | Unordered (bulleted) list |
| `<ol>` | Ordered (numbered) list |
| `<li>` | List item |
| `<dl>` | Description list |
| `<dt>` | Term |
| `<dd>` | Definition |

---

## 🧭 5. Tables

```html
<table border="1">
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>25</td>
    </tr>
  </tbody>
</table>
```

| Tag | Description |
|-----|-------------|
| `<table>` | Defines a table |
| `<tr>` | Table row |
| `<th>` | Table header |
| `<td>` | Table cell |
| `<thead>`, `<tbody>`, `<tfoot>` | Organize table sections |

---

## 🧍 6. Forms and Inputs

```html
<form action="/submit" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" />

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" />

  <textarea name="message" rows="4"></textarea>

  <select name="country">
    <option value="us">United States</option>
    <option value="mx">Mexico</option>
  </select>

  <input type="checkbox" id="agree" />
  <label for="agree">I agree</label>

  <button type="submit">Submit</button>
</form>
```

| Tag | Description |
|-----|-------------|
| `<form>` | Form container |
| `<input>` | Text, checkbox, radio, password, etc. |
| `<label>` | Describes input |
| `<textarea>` | Multi-line text box |
| `<select>` & `<option>` | Dropdown list |
| `<button>` | Clickable button |

---

## 🧰 7. Semantic Layout Elements (HTML5)

```html
<header>Page Header</header>
<nav>Navigation Menu</nav>
<main>Main content area</main>
<article>Independent content block</article>
<section>Section of related content</section>
<aside>Sidebar or extra content</aside>
<footer>Page Footer</footer>
```

| Tag | Description |
|-----|-------------|
| `<header>` | Top section of page or article |
| `<nav>` | Navigation links |
| `<main>` | Main content |
| `<article>` | Independent, self-contained content |
| `<section>` | Thematic grouping |
| `<aside>` | Sidebar or complementary content |
| `<footer>` | Bottom section |

---

## 🎨 8. Multimedia

```html
<video controls width="320">
  <source src="movie.mp4" type="video/mp4" />
  Your browser does not support the video tag.
</video>

<audio controls>
  <source src="song.mp3" type="audio/mpeg" />
</audio>
```

| Tag | Description |
|-----|-------------|
| `<video>` | Embeds a video |
| `<audio>` | Embeds audio |
| `<source>` | Defines media source |

---

## 🧠 9. Miscellaneous & Useful Tags

```html
<span>This is inline text</span>
<div>This is a block container</div>
<code>console.log("Hello")</code>
<pre>
function greet() {
  console.log("Hello World");
}
</pre>
<abbr title="World Wide Web">WWW</abbr>
```

| Tag | Description |
|-----|-------------|
| `<div>` | Block container |
| `<span>` | Inline container |
| `<code>` | Inline code formatting |
| `<pre>` | Preformatted text (keeps spacing) |
| `<abbr>` | Abbreviation with tooltip |

---

## ⚡ 10. Comments

```html
<!-- This is a comment -->
```

- Comments are **ignored by browsers**.
- Useful for notes or explanations inside HTML files.

---

## 🌐 11. Special Characters (Entities)

| Character | Code |
|----------|------|
| `<` | `&lt;` |
| `>` | `&gt;` |
| `&` | `&amp;` |
| `©` | `&copy;` |
| `®` | `&reg;` |
| Non-breaking space | `&nbsp;` |

---

## ✅ Quick Summary Table

| Category | Common Tags |
|----------|-------------|
| Structure | `<!DOCTYPE>`, `<html>`, `<head>`, `<body>` |
| Text | `<h1>`–`<h6>`, `<p>`, `<strong>`, `<em>` |
| Links & Media | `<a>`, `<img>`, `<video>`, `<audio>` |
| Lists | `<ul>`, `<ol>`, `<li>` |
| Tables | `<table>`, `<tr>`, `<th>`, `<td>` |
| Forms | `<form>`, `<input>`, `<textarea>`, `<select>` |
| Semantic | `<header>`, `<main>`, `<footer>`, `<section>` |
| Misc | `<div>`, `<span>`, `<code>`, `<pre>` |

---
