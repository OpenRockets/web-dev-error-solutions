# 🐞 CSS Challenge:  Three-Column Layout with Sticky Header


This challenge focuses on creating a responsive three-column layout using CSS.  We'll implement a sticky header that remains fixed at the top of the viewport as the user scrolls.  This example uses plain CSS, but could easily be adapted to use a framework like Tailwind CSS.


**Description of the Styling:**

The layout consists of a header, a main content area divided into three equal columns, and a footer. The header should stick to the top of the browser window on scroll.  The three columns should adjust responsively to different screen sizes, ideally maintaining equal width wherever possible.  We'll use flexbox for its flexibility in handling layout and responsiveness.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Three-Column Sticky Header</title>
<style>
body {
  margin: 0;
}

header {
  background-color: #333;
  color: white;
  padding: 1em;
  position: sticky;
  top: 0;
  z-index: 1; /* Ensure header stays on top */
}

main {
  display: flex;
  flex-wrap: wrap; /* Allow columns to wrap on smaller screens */
}

.column {
  flex: 1 0 33.33%; /* Each column takes 1/3 of the available width */
  padding: 1em;
  box-sizing: border-box; /* Include padding in element width */
}

footer {
  background-color: #333;
  color: white;
  padding: 1em;
  text-align: center;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .column {
    flex: 1 0 50%; /* Two columns on medium screens */
  }
}

@media (max-width: 500px) {
  .column {
    flex: 1 0 100%; /* One column on small screens */
  }
}
</style>
</head>
<body>

<header>
  <h1>Sticky Header</h1>
</header>

<main>
  <div class="column">Column 1</div>
  <div class="column">Column 2</div>
  <div class="column">Column 3</div>
</main>

<footer>
  <p>&copy; 2023 My Website</p>
</footer>

</body>
</html>
```


**Explanation:**

* **`position: sticky;`:** This is crucial for the sticky header.  It combines aspects of `position: relative;` and `position: fixed;`. The element is positioned relative to its parent until it crosses a specified threshold (in this case, the top of the viewport), at which point it becomes fixed.
* **`z-index: 1;`:** This ensures the header stays on top of other elements.
* **`flex: 1 0 33.33%;`:**  This is the core of the three-column layout using flexbox.  `flex: 1` allows the columns to grow and shrink proportionally to available space. `0` sets the minimum width to 0 (allowing columns to shrink below 33.33% if necessary), and `33.33%` sets the initial width.
* **`@media` queries:** These handle responsiveness.  As the screen size decreases, the number of columns adjusts accordingly.
* **`box-sizing: border-box;`:** This ensures that padding and border are included within the element's total width, preventing unexpected layout issues.

**Links to Resources to Learn More:**

* **CSS Flexbox:** [MDN Web Docs - CSS Flexible Box Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
* **CSS Position Sticky:** [MDN Web Docs - position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **CSS Media Queries:** [MDN Web Docs - @media](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

