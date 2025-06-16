# 🐞 CSS Challenge:  Multi-Level Nested Navigation Menu


This challenge involves creating a multi-level nested navigation menu using CSS.  The goal is to build a visually appealing and user-friendly menu that expands and collapses sub-menus on hover.  We'll be using plain CSS (no preprocessors like Sass or Less) for this example, focusing on fundamental CSS techniques.  This approach could easily be adapted to Tailwind CSS by replacing the custom CSS classes with Tailwind's utility classes.

**Description of the Styling:**

The menu will have a clean, modern look.  The top-level items will be displayed horizontally. On hovering over a top-level item, its sub-menu will slide down smoothly.  Sub-menus will be indented visually to show the hierarchical structure. We'll use a subtle background color to highlight active menu items and sub-menus.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Navigation Menu</title>
<style>
nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

nav ul li {
  display: inline-block;
  position: relative;
}

nav a {
  display: block;
  padding: 10px 20px;
  text-decoration: none;
  color: #333;
}

nav a:hover {
  background-color: #f0f0f0;
}

nav ul li ul {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #fff;
  border: 1px solid #ccc;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

nav ul li:hover > ul {
  display: block;
}

nav ul li ul li {
  display: block; /* Sub-menu items are stacked vertically */
}

nav ul li ul a {
  padding: 5px 20px;
}

</style>
</head>
<body>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a>
      <ul>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Our History</a></li>
      </ul>
    </li>
    <li><a href="#">Services</a>
      <ul>
        <li><a href="#">Service 1</a></li>
        <li><a href="#">Service 2</a></li>
        <li><a href="#">Service 3</a>
          <ul>
            <li><a href="#">Sub-Service 1</a></li>
            <li><a href="#">Sub-Service 2</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

</body>
</html>
```

**Explanation:**

*   The core structure uses nested unordered lists (`<ul>`) to represent the menu hierarchy.
*   `position: relative` on parent list items allows absolute positioning of sub-menus.
*   `display: none` initially hides sub-menus.  `li:hover > ul` uses the adjacent sibling combinator to show the sub-menu only when the parent list item is hovered.
*   CSS is used to style the menu items, add spacing, and create a visual hierarchy using indentation and background colors.  Box shadow adds a subtle 3D effect.


**Links to Resources to Learn More:**

*   **MDN Web Docs - CSS Selectors:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)  (Learn about selectors like `:hover` and adjacent sibling combinator)
*   **MDN Web Docs - Positioning:** [https://developer.mozilla.org/en-US/docs/Web/CSS/position](https://developer.mozilla.org/en-US/docs/Web/CSS/position) (Understand `position: relative` and `position: absolute`)
*   **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (A great resource for CSS tutorials and articles)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

