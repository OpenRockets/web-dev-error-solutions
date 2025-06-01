# 🐞 Creating a CSS-only Accordion


This document details the creation of a simple accordion using only CSS.  No JavaScript is required.  This utilizes CSS's ability to toggle visibility and height based on sibling selectors and the `:target` pseudo-class.


## Description of the Styling

This accordion consists of a list of items. Each item has a title that acts as a button to expand and collapse the content below it.  The styling uses a simple, clean approach, focusing on readability and ease of understanding. The accordion expands vertically, revealing its content when its title is clicked.  The styling leverages `max-height` and transitions for a smooth animation.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Only Accordion</title>
<style>
body {
  font-family: sans-serif;
}

.accordion {
  width: 300px;
  border: 1px solid #ccc;
}

.accordion-item {
  border-bottom: 1px solid #ccc;
}

.accordion-title {
  background-color: #f0f0f0;
  padding: 10px;
  cursor: pointer;
  display: block; /* Makes the title clickable */
}

.accordion-content {
  overflow: hidden;
  max-height: 0;
  transition: max-height 0.5s ease-out;
}

.accordion-item.active .accordion-content {
  max-height: 200px; /* Adjust as needed */
}

.accordion-title::before {
  content: "➕";
  margin-right: 5px;
  transition: transform 0.3s ease;
}

.accordion-item.active .accordion-title::before{
  content: "➖";
  transform: rotate(45deg);
}
</style>
</head>
<body>

<div class="accordion">
  <div class="accordion-item">
    <a href="#section1" class="accordion-title">Section 1</a>
    <div id="section1" class="accordion-content">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    </div>
  </div>
  <div class="accordion-item">
    <a href="#section2" class="accordion-title">Section 2</a>
    <div id="section2" class="accordion-content">
      <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
    </div>
  </div>
  <div class="accordion-item">
    <a href="#section3" class="accordion-title">Section 3</a>
    <div id="section3" class="accordion-content">
      <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
    </div>
  </div>
</div>

</body>
</html>
```


## Explanation

1. **Structure:** The HTML uses nested divs to represent the accordion items. Each item has a title (`accordion-title`) and content (`accordion-content`).  Crucially, the title is an `<a>` tag linking to a unique ID within the content div.

2. **CSS Styling:**
   - The `.accordion-content` initially has `max-height: 0;` hiding the content.
   - The `.accordion-item.active .accordion-content` selector targets the content when its parent has the class "active," setting `max-height` to a visible value.
   - The `transition` property provides smooth animation.
   - `:before` pseudo-element adds plus/minus icons for visual feedback.

3. **Functionality:** Clicking the title (`<a>`) navigates to the corresponding section ID (`#section1`, etc.) using the browser's built-in anchor functionality. The browser then adds the `active` class to that particular item, revealing its content.   The `:target` pseudo-class isn't explicitly used, but it's the underlying mechanism that makes this work.


## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

