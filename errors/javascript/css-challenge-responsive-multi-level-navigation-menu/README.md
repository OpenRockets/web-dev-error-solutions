# 🐞 CSS Challenge: Responsive Multi-Level Navigation Menu


This challenge involves creating a responsive multi-level navigation menu using CSS.  The menu should collapse on smaller screens and expand smoothly on hover or click. We'll achieve this using CSS3 and will illustrate a clean, accessible approach.  No JavaScript is needed.

**Description of the Styling:**

The navigation menu will have a clean, modern look.  The main navigation items will be displayed horizontally.  Sub-menus will appear on hover (or on click for smaller screens) and will be positioned to avoid overlapping the main menu items.  We'll use transitions for smooth animations.  The design will be responsive, adapting seamlessly to various screen sizes.  We’ll also focus on semantic HTML for accessibility.


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
  list-style: none;
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
  display: none;
  position: absolute;
  background-color: #333;
}

nav li:hover > ul {
  display: block;
}


/* Responsive Styles */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
  }
  nav ul ul {
    position: static;
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

* **Basic Structure:** The HTML uses nested unordered lists (`<ul>`) to create the multi-level structure.
* **CSS Positioning:**  `float: left` is used for horizontal arrangement of main menu items.  `position: absolute` for sub-menus allows precise positioning relative to the parent. `display: none;` hides sub-menus initially.
* **Hover Effect:** `li:hover > ul` targets the sub-menu and displays it on hover of the parent list item.
* **Responsive Design:** The `@media` query adapts the menu for smaller screens by removing the `float` and changing the sub-menu position to `static`. This makes the menu items stack vertically.

**Links to Resources to Learn More:**

* **CSS3 Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Responsive Web Design:** [Responsive Web Design Basics](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
* **CSS Selectors:** [Understanding CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

