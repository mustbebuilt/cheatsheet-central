# HTML Core 20 Cheat Sheet

A quick reference to the most useful HTML elements for building web pages.

## 1. `html`

Root element for the entire page.

```html
<html lang="en">
  ...
</html>
```

## 2. `head`

Contains metadata and page configuration.

```html
<head>
  <title>Page Title</title>
</head>
```

## 3. `body`

Contains the visible page content.

```html
<body>
  <h1>Hello</h1>
</body>
```

## 4. `title`

Sets the browser tab title.

```html
<title>My App</title>
```

## 5. `meta`

Provides metadata such as charset and viewport.

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

## 6. `h1` to `h6`

Headings for document structure.

```html
<h1>Main heading</h1>
<h2>Subheading</h2>
```

## 7. `p`

Paragraph text.

```html
<p>This is a paragraph of text.</p>
```

## 8. `a`

Hyperlink to another page or section.

```html
<a href="https://example.com">Visit site</a>
```

## 9. `img`

Embeds an image.

```html
<img src="image.jpg" alt="A cat" />
```

## 10. `ul`, `ol`, `li`

Lists for grouped content.

```html
<ul>
  <li>Milk</li>
  <li>Bread</li>
</ul>
```

## 11. `div`

Generic container for layout and grouping.

```html
<div class="card">
  Content
</div>
```

## 12. `span`

Inline container for styling or markup.

```html
<p>This is <span class="highlight">important</span>.</p>
```

## 13. `strong`

Important text displayed in bold.

```html
<strong>Important!</strong>
```

## 14. `em`

Emphasized text displayed in italics.

```html
<em>Careful</em>
```

## 15. `table`, `tr`, `td`

Creates data tables.

```html
<table>
  <tr><td>Name</td><td>Age</td></tr>
</table>
```

## 16. `form`

Collects user input.

```html
<form action="/submit" method="post">
  <input type="text" name="name" />
</form>
```

## 17. `input`

Text field, checkbox, radio, file upload, etc.

```html
<input type="email" name="email" placeholder="you@example.com" />
```

## 18. `button`

Clickable button control.

```html
<button type="submit">Send</button>
```

## 19. `section`

Groups related content into a thematic section.

```html
<section>
  <h2>About</h2>
  <p>...</p>
</section>
```

## 20. `header`, `nav`, `main`, `footer`

Semantic page regions for structure and accessibility.

```html
<header>Site title</header>
<nav>Links</nav>
<main>Main content</main>
<footer>Footer</footer>
```

> Quick rule: use semantic elements for structure, CSS for styling, and forms/inputs for user interaction.
