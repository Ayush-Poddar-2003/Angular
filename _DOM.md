# DOM

DOM (Document Object Model) is a programming representation of an HTML document.

When a browser loads a webpage, it converts HTML into a tree of objects that JavaScript can interact with.

So instead of reading raw HTML, the browser works with objects.

```html
<html>
  <body>
    <h1>Hello</h1>
    <button>Click</button>
  </body>
</html>
```
```
Document
  |
  html
   |
  body
  /   \
h1    button

Each item in this tree is called a DOM node.
```
---
### DOM Nodes

Everything in the DOM is a node.

| Node Type      | Example          |
| -------------- | ---------------- |
| Document Node  | entire page      |
| Element Node   | `<div>`, `<p>`   |
| Text Node      | text inside tags |
| Attribute Node | id, class        |

```html
<p id="title">Hello World</p>
```
```
Element Node → p
Attribute Node → id="title"
Text Node → Hello World
```

---

### What is a DOM Property?

A property is a value stored inside a DOM object.

Properties represent the current state of the element.