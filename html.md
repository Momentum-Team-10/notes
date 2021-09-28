# Intro to HTML

## The structure of web pages

---

# HTML

## HyperText Markup Language

You "mark up" the content of a document to describe where things go and how they should be displayed.

- paragraphs are enclosed with "p" tags
- divisions of a page get "div" tags
- buttons get "button" tags

---

# What is HTML?

- Code that describes the structure of the page's content; instructions for the browser to render the page.
- Think of it as the skeleton of the page
- Works with CSS (styling) and JS (behavior)

Let's look at the page source for [momentumlearn.com](https://www.momentumlearn.com)

---

# Tags vs Elements

## A **tag** is one part of an **element**.

## An **element** is made up of opening and closing tags and any content between them.

---

# Tags and Elements

**Opening** and **closing** tags wrap content and tell you something about its purpose.

These "p" tags designate a paragraph element.

```html
<p>Hello, World!</p>
```

**Self-closing** tags are valid without closing tags.
**Empty**, or **void**, elements have self-closings tags and no content or children but often do have attributes.

```html
<link href="main.css" rel="stylesheet" />
<img src="images/chihuahua.jpg" />
<br />
```

---

# Anatomy of an element

- opening and closing tags
- optional content (text)
- optional attributes

[MDN Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

---

# HTML Attributes

Attributes provide information about an element's contents.
They have a **name** and a **value**.

```html
<a href="https://www.momentumlearn.com">Momentum Learning</a>
```

Most attributes can only be used on specific elements, but some are **global** -- that is, they can be used with any element.

The most common global attributes are **class** and **id**:

```html
<div class="container" id="root"></div>
```

[MDN Attribute Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)

---

# A Closer Look at HTML Attributes

- An attribute has one key (attribute name)
- An attribute has one value\* (attribute value)
- Keys are not enclosed in quotation marks
- Values are enclosed in quotation marks
- An `=` sign separates the key and value
- Multiple attributes are separated by a space
- Don't duplicate attributes on the same element

\*usually

---

# HTML Document Structure & Page Hierarchy

Things to consider as you build with HTML:

- relationships between elements
- the structure of the html document (the order and placement of elements)
- semantics (the relationship of structural elements to their content)

---

# Relationships between Elements

## Nesting

Elements can nest inside one another. This is a tree-like structure, creating a hierarchy of relationships.

As in a family tree, an HTML document structure has ancestors, parents, children, and siblings.

---

```html
<section>
  <h2>Rhodesian Ridgeback</h2>
  <p>Rhodesian Ridgebacks are fierce, loyal dogs. Read some facts about them</p>
  <ul>
    <li>Also known as the African Lion Hound</li>
    <li>Bred as big-game hunting compantions</li>
    <li>Adults weigh 70-85 lbs</li>
  </ul>
</section>
```

---

# Let's build an HTML page together!

[team examples repo](https://github.com/momentum-team-8/examples)

---

# Typical structure of an HTML page

- `<!DOCTYPE html>` sets the version of html for the browser
- `<html>` the root element of the page; wraps all the others
- `<head>` contains metadata about the document; this is not meant to be displayed in the browser window, but contains information the page needs.
  - `link`, `meta`, `title`, `style`
- `<body>` contains the content of the document. There can be only one of these in a single html document.
- Inside the `<body>` element are nested all the other major structural components of a page. These typically include a header, a nav bar, the main content, a sidebar, and a footer

---

# Semantic HTML

"Semantic" refers to the meaning of something. In linguistics, we are talking about the meaning of words.

**Semantic HTML** refers to HTML elements that carry some meaning about the purpose of the content they contain.

Writing semantic html means that you choose tags based on the meaning and importance of the content, not based on how you want the page to look.

---

## Not Semantic

```html
<div>
  <div>
    <div>Amazing Dog Stories</div>
  </div>
  <div>
    <div>Chihuahua Rescues Owner from Burning Building</div>
    <div>Lorem ipsum dolor sit amet...</div>
  </div>
</div>
```

---

## Semantic

```html
<section>
  <header>
    <h1>Amazing Dog Stories</h1>
  </header>
  <article>
    <h2>Chihuahua Rescues Owner from Burning Building</h2>
    <p>Lorem ipsum dolor sit amet...</p>
  </article>
</section>
```

[MDN Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

---

# Block vs inline elements

**Block** elements take up the full width of its parent container, appearing to start on a new line on the page and stack on top of each other.

**Inline** elements appear to continue on the same line as their sibling elements. They only take up as much space as necessary.

---

# Common block elements

- `<p>`
- `<div>`
- `<h1>` - `<h6>`
- `<ul>` and `<ol>`
- `<li>`
- `<nav>`
- `<header>`

[MDN Block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)

---

# Common inline elements

- `<span>`
- `<img>`
- `<a>`

[MDN Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)

---

# Grouping elements in a block

## <div>

This element is not semantic!
It is a container, used for grouping other elements in a block-level box.
We group things so we can treat them as a unit with CSS or with JavaScript.

```html
<div class="fish-detail">
  <img src="images/channel-catfish.png" alt="channel catfish">
  <ul>
    <li>Has a forked tail with black spots</li>
    <li>Native to the Mississippi Basin</li>
    <li>Active from sunset to midnight</li>
</div>
```

---

# Grouping elements inline

## `<span>`

An inline equivalent of a `<div>`

```html
<p>
  A <span class="fish-species">striped bass</span> can be silver, copper, or
  greenish in color
</p>
```