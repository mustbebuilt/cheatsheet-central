# Markdown Cheat Sheet for Beginners

Markdown is a simple way to format text for README files, documentation, notes, and GitHub pages.

## 1. Headings

Use headings to organize content.

```md
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

This creates a hierarchy from largest to smallest heading.

---

## 2. Paragraphs and line breaks

Write normal text as paragraphs.

```md
This is a paragraph.

This is another paragraph.
```

A blank line separates paragraphs.

To force a line break, add two spaces at the end of a line or use `<br>`.

```md
First line  
Second line
```

---

## 3. Bold and italic

```md
**bold text**
*italic text*
***bold and italic***
```

Examples:

- **Important**
- *emphasis*
- ***very important***

---

## 4. Lists

### Unordered list

```md
- Item 1
- Item 2
- Item 3
```

### Ordered list

```md
1. First item
2. Second item
3. Third item
```

### Nested list

```md
- Parent item
  - Child item
  - Another child item
```

---

## 5. Links

```md
[GitHub](https://github.com)
```

This displays as a clickable link.

You can also link to a file in the same repository:

```md
[README](README.md)
```

---

## 6. Images

```md
![Alt text](https://example.com/image.jpg)
```

Or for a local file:

```md
![Project screenshot](images/screenshot.png)
```

---

## 7. Code blocks

### Inline code

```md
Use the command `git status` to check your files.
```

### Code fence

```md
```bash
git status
git add .
git commit -m "Update project"
```
```

Use a language label like `bash`, `javascript`, `python`, `json`, or `md` when helpful.

---

## 8. Blockquotes

```md
> This is a quote.
> It can span multiple lines.
```

Example:

> Important: Always test your code before pushing.

---

## 9. Horizontal rules

```md
---
```

This creates a horizontal line.

---

## 10. Tables

```md
| Name | Role | Email |
| ---- | ---- | ----- |
| Alice | Developer | alice@example.com |
| Ben | Tester | ben@example.com |
```

Example output:

| Name | Role | Email |
| ---- | ---- | ----- |
| Alice | Developer | alice@example.com |
| Ben | Tester | ben@example.com |

---

## 11. Task lists

```md
- [x] Set up the project
- [x] Create the README
- [ ] Add tests
```

This is useful for checklists in project documentation.

---

## 12. Escaping characters

If you want to show special characters literally, escape them with a backslash.

```md
\*not italic\*
\# not a heading
```

---

## 13. Emojis

```md
:rocket: Launch
:warning: Important
:check: Done
```

Examples:

- :rocket: Launch
- :warning: Important
- :check: Done

---

## 14. Common README structure

A typical README file might look like this:

```md
# Project Name

Short description of what the project does.

## Features

- Fast setup
- Easy to use
- Good documentation

## Installation

```bash
npm install
```

## Usage

```bash
npm start
```

## License

This project is licensed under the MIT License.
```

---

## 15. Best practices for README files

- Keep it short and clear
- Start with a project title
- Explain what the project does
- Include install and run steps
- Add screenshots when useful
- Use headings to organize sections
- Keep examples easy to copy

---

## 16. Quick starter template

```md
# My Project

A short description of the project.

## Overview

Describe the problem this project solves.

## Features

- Feature one
- Feature two
- Feature three

## Getting Started

```bash
git clone https://github.com/username/project.git
cd project
npm install
```

## Usage

```bash
npm start
```

## Contributing

Open a pull request with a clear description.

## License

MIT
```

---

## 17. Summary

Markdown is the standard way to write readable documentation for GitHub and developer projects.

The most important things to remember are:

- headings for structure
- lists for steps/items
- fenced code blocks for examples
- links for navigation
- tables for data
- emphasis for readability

Use Markdown to make your project documentation clear, clean, and easy to read.
