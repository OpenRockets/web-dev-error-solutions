# 🐞 CSS Challenge:  Responsive Multi-Level Navigation Menu


This challenge focuses on creating a responsive, multi-level navigation menu using CSS.  The goal is to build a menu that gracefully adapts to different screen sizes, smoothly revealing sub-menus on hover or click.  We'll use CSS3 for styling and focus on clean, semantic HTML for structure.  No JavaScript is required for this specific implementation.

**Description of the Styling:**

The navigation menu will feature:

* A main navigation bar with top-level menu items.
* Sub-menus that appear on hover (or click, depending on screen size).
* Clear visual hierarchy using spacing, color, and font sizes.
* Responsiveness – gracefully adapting to smaller screens by collapsing the menu or using a hamburger menu icon (although we will not implement a hamburger menu in this example to keep it focused purely on CSS).
* Use of CSS pseudo-classes and nesting for styling efficiency.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Multi-Level Navigation</title>
<style>
nav {
  background-color: #333;
  overflow: hidden;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

nav li {
  float: left;
}

nav a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav a:hover {
  background-color: #ddd;
  color: black;
}

nav ul ul {
  display: none; /* Hidden by default */
  position: absolute;
  background-color: #333;
}

nav li:hover > ul {
  display: block; /* Show sub-menu on hover */
}

/* Responsiveness (for smaller screens) */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
  }
  nav ul ul {
    position: static; /* Remove absolute positioning */
  }
}

</style>
</head>
<body>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a>
      <ul>
        <li><a href="#">Service 1</a></li>
        <li><a href="#">Service 2</a></li>
        <li><a href="#">Service 3</a></li>
      </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

</body>
</html>
```


**Explanation:**

* The main navigation is structured using nested unordered lists (`<ul>` and `<li>`). This is semantically correct and makes the structure clear.
* CSS floats are used to position the top-level menu items horizontally.
* The sub-menus are initially hidden using `display: none;` and then revealed using the `:hover` pseudo-class on the parent `li` element.  `position: absolute;` is key to making the submenus appear correctly positioned.
* The `@media` query handles responsiveness by removing the floats and absolute positioning for smaller screens, resulting in a stacked menu.


**Links to Resources to Learn More:**

* **MDN Web Docs CSS Guide:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) –  A comprehensive resource for all things CSS.
* **CSS Tricks:** [https://css-tricks.com/](https://css-tricks.com/) – A great website with tutorials and articles on CSS techniques.
* **W3Schools CSS Tutorial:** [https://www.w3schools.com/css/](https://www.w3schools.com/css/) – A beginner-friendly tutorial on CSS.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

