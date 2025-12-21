# HTML & CSS Fundamentals

> **🎓 CS Perspective:** HTML and CSS form the **declarative** layer of web development—you describe *what* you want, not *how* to render it. HTML implements a **tree data structure** (the DOM) using nested tags, which the browser parses into an in-memory tree. CSS applies styles through a **pattern-matching system** (selectors) with a **specificity algorithm** to resolve conflicts. The cascade follows a well-defined **precedence hierarchy**: inline > ID > class > element. This separation of structure (HTML) and presentation (CSS) embodies the **separation of concerns** principle, making code more maintainable and enabling different stylesheets for different devices (responsive design).

---

## 📌 HTML Document Structure

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link href="style.css" rel="stylesheet" />
    <title>Page Title</title>
  </head>
  <body>
    <!-- Content goes here -->
  </body>
</html>
```

| Element | Purpose |
|---------|---------|
| `<!DOCTYPE html>` | Declares HTML5 document |
| `<html>` | Root element |
| `<head>` | Metadata, links, title |
| `<body>` | Visible content |

---

## 📌 Common HTML Elements

### Headings & Text
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<p>Paragraph text</p>
```

### Links & Images
```html
<a href="https://example.com">Link text</a>
<img src="image.jpg" alt="Description" />
```

### Forms
```html
<form id="my-form">
  <input type="text" placeholder="Enter text" />
  <button>Submit</button>
</form>
```

---

## 📌 CSS Selectors

| Selector | Syntax | Specificity |
|----------|--------|-------------|
| **Element** | `p { }` | Low (0,0,1) |
| **Class** | `.classname { }` | Medium (0,1,0) |
| **ID** | `#idname { }` | High (1,0,0) |
| **Descendant** | `#parent h2 { }` | Combined |
| **Universal** | `* { }` | Lowest (0,0,0) |

```css
/* Element selector */
p {
  margin-bottom: 20px;
}

/* Class selector */
.first {
  color: red;
}

/* ID selector */
#course-image {
  width: 300px;
}

/* Descendant selector */
#your-name h2 {
  color: olivedrab;
}
```

---

## 📌 CSS Box Model

Every element is a box with:

```
┌─────────────────────────────────────┐
│             MARGIN                  │
│  ┌───────────────────────────────┐  │
│  │          BORDER               │  │
│  │  ┌─────────────────────────┐  │  │
│  │  │       PADDING           │  │  │
│  │  │  ┌───────────────────┐  │  │  │
│  │  │  │     CONTENT       │  │  │  │
│  │  │  └───────────────────┘  │  │  │
│  │  └─────────────────────────┘  │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

### box-sizing Property
```css
* {
  box-sizing: border-box; /* Width includes padding + border */
}
```

| Value | Width Calculation |
|-------|-------------------|
| `content-box` | width = content only (default) |
| `border-box` | width = content + padding + border |

---

## 📌 Common CSS Properties

### Colors & Backgrounds
```css
body {
  background-color: rgb(255, 247, 201);
  color: #444;
}

a {
  background-color: yellowgreen;
}
```

### Typography
```css
body {
  font-family: Arial, sans-serif;
  font-size: 20px;
}

h1 {
  font-size: 35px;
}
```

### Spacing
```css
h1 {
  margin-bottom: 25px;  /* Outside spacing */
  padding: 50px;        /* Inside spacing */
}
```

### Borders
```css
#your-name {
  border: 5px solid #444;
}
```

### Sizing
```css
#your-name {
  width: 400px;
}

#course-image {
  width: 300px;
}
```

---

## 📌 CSS Reset

Remove default browser styles for consistency:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

---

## 📌 Linking CSS to HTML

```html
<!-- External stylesheet (recommended) -->
<link href="style.css" rel="stylesheet" />

<!-- Internal styles -->
<style>
  p { color: blue; }
</style>

<!-- Inline styles (avoid) -->
<p style="color: blue;">Text</p>
```

### Specificity Hierarchy (Highest → Lowest)
1. Inline styles
2. ID selectors
3. Class selectors
4. Element selectors
5. Universal selector
