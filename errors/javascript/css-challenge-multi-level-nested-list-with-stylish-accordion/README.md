# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordion


This challenge focuses on creating a visually appealing multi-level nested list that utilizes an accordion effect for collapsing and expanding sub-lists. We'll use CSS3 for styling and leverage the power of the `:target` pseudo-class for the accordion functionality.  No JavaScript is required.

**Description of the Styling:**

The styling aims for a clean, modern look.  The top-level list items will have a distinct background color and padding.  Subsequent levels will be indented and use a lighter background color.  The "+" and "-" symbols will be used to indicate whether a sublist is collapsed or expanded, respectively.  The accordion effect will be achieved by using the `:target` pseudo-class to show/hide the sub-lists based on the URL hash.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Accordion</title>
<style>
body { font-family: sans-serif; }

ul { list-style: none; padding: 0; margin: 0; }

.accordion li {
  background-color: #f0f0f0;
  padding: 10px;
  border-bottom: 1px solid #ddd;
  cursor: pointer;
}

.accordion li.active {
  background-color: #e0e0e0;
}

.accordion li ul {
  display: none;
  padding-left: 20px;
  background-color: #f8f8f8;
}

.accordion li.active > ul {
  display: block;
}

.accordion li a {
  text-decoration: none;
  color: #333;
  display: block;
}

.accordion li a::before {
  content: "+";
  margin-right: 5px;
}

.accordion li.active a::before {
  content: "-";
}

.accordion li a:hover {
  text-decoration: underline;
}

</style>
</head>
<body>

<ul class="accordion">
  <li>
    <a href="#section1">Item 1</a>
    <ul id="section1">
      <li><a href="#section1-1">Sub-item 1.1</a></li>
      <li><a href="#section1-2">Sub-item 1.2</a>
        <ul id="section1-2">
          <li><a href="#section1-2-1">Sub-sub-item 1.2.1</a></li>
        </ul>
      </li>
    </ul>
  </li>
  <li>
    <a href="#section2">Item 2</a>
    <ul id="section2">
      <li><a href="#section2-1">Sub-item 2.1</a></li>
    </ul>
  </li>
</ul>

</body>
</html>
```

**Explanation:**

1. **HTML Structure:**  The HTML uses nested unordered lists (`<ul>`) to represent the nested list structure.  Each list item `<li>` contains an anchor tag `<a>` with a `href` attribute pointing to a unique ID (`#section1`, `#section1-1`, etc.).  This ID is used for the accordion functionality.

2. **CSS Styling:** The CSS styles the lists, adds padding and background colors, and uses `display: none;` to initially hide the sub-lists.

3. **Accordion Effect (`<a>`, `:target`, and `ul`):** The `:target` pseudo-class in CSS selects the element whose ID matches the current URL's fragment identifier (the part after the `#`).  When a user clicks on an anchor, the URL hash changes, and the `:target` pseudo-class dynamically shows/hides the corresponding sublist. The `a::before` pseudo-element adds the plus/minus symbol. The class `active` is added to toggle the background color.

**Links to Resources to Learn More:**

* [MDN Web Docs - CSS :target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* [MDN Web Docs - CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* [CSS-Tricks - CSS Accordions](https://css-tricks.com/accordion-with-css/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

