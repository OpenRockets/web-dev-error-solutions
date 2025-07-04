# 🐞 CSS Challenge:  Multi-Level Nested Navigation Menu


This challenge focuses on creating a multi-level nested navigation menu using CSS.  We'll build a responsive menu that expands and collapses sub-menus on hover.  While this could be achieved with JavaScript, we'll focus on a pure CSS solution for learning purposes. This example uses plain CSS, but could easily be adapted to Tailwind CSS by replacing the CSS classes with their Tailwind equivalents.


## Description of the Styling

The navigation menu will have a clean, modern look.  The top-level items will be displayed horizontally.  On hover, a sub-menu will slide down from the corresponding parent item.  Sub-menus will be indented and will themselves support further nesting.  The styling will aim for a consistent appearance across different screen sizes, adapting gracefully to smaller screens.  We'll utilize CSS transitions for smooth animations.


## Full Code

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

nav li {
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

nav ul ul {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #fff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

nav li:hover > ul {
  display: block;
}

nav ul ul li {
  display: block; /* Makes sub-menu items stack vertically */
}

nav ul ul a {
  padding-left: 30px; /* Indents sub-menu items */
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
        <li><a href="#">Contact Us</a></li>
      </ul>
    </li>
    <li><a href="#">Services</a>
      <ul>
        <li><a href="#">Web Design</a>
          <ul>
            <li><a href="#">WordPress</a></li>
            <li><a href="#">Shopify</a></li>
          </ul>
        </li>
        <li><a href="#">Web Development</a></li>
      </ul>
    </li>
    <li><a href="#">Blog</a></li>
  </ul>
</nav>

</body>
</html>
```


## Explanation

* **`nav ul`:** This sets up the basic unordered list structure for the navigation.  `list-style: none;` removes the default bullet points.
* **`nav li`:** Each list item (`<li>`) is set to `inline-block` to position them horizontally.  `position: relative;` is crucial for positioning the sub-menus absolutely within their parent items.
* **`nav a`:** Styles the links.
* **`nav ul ul`:** This styles the nested unordered lists (sub-menus).  `display: none;` initially hides them, `position: absolute;` allows for precise positioning, and `box-shadow;` adds a subtle shadow effect.
* **`nav li:hover > ul`:** This is the key to the hover effect.  When a list item is hovered, its direct child `ul` (the sub-menu) is displayed using `display: block;`.
* **Indentation and Vertical Stacking:**  `display: block;` on sub-menu list items (`nav ul ul li`) and  `padding-left` on sub-menu links create the visual indentation and vertical stacking within the sub-menus.


## Links to Resources to Learn More

* **MDN Web Docs - CSS:  [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)** (Comprehensive CSS reference)
* **CSS-Tricks: [https://css-tricks.com/](https://css-tricks.com/)** (Great blog and tutorials on CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

