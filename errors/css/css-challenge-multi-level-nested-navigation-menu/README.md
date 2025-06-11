# 🐞 CSS Challenge:  Multi-level Nested Navigation Menu


This challenge involves creating a multi-level nested navigation menu using CSS.  The goal is to create a visually appealing and user-friendly menu that expands and collapses sub-menus on hover. We'll use plain CSS for this example, focusing on fundamental CSS concepts.


**Description of the Styling:**

The navigation menu will be a vertical list.  Top-level menu items will be displayed horizontally.  When a top-level item is hovered, its submenu will slide down smoothly.  Sub-submenus (and further levels) will appear similarly when their parent is hovered. The styling will employ a clean and modern aesthetic, using subtle animations for a better user experience.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Navigation Menu</title>
<style>
body {
  font-family: sans-serif;
}

.nav {
  background-color: #f0f0f0;
  padding: 10px;
}

.nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav li {
  position: relative; /* Needed for absolute positioning of submenus */
}

.nav a {
  display: block;
  padding: 10px;
  text-decoration: none;
  color: #333;
}

.nav a:hover {
  background-color: #ddd;
}

.nav ul ul {
  position: absolute;
  left: 100%; /* Position submenu to the right of parent */
  top: 0;
  display: none; /* Hidden by default */
  background-color: #f0f0f0;
}

.nav li:hover > ul { /* Show submenu on hover */
  display: block;
}


/* Optional: Add transitions for smooth animations */
.nav ul ul {
  transition: all 0.3s ease;
}

</style>
</head>
<body>

<div class="nav">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a>
      <ul>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Our Mission</a>
          <ul>
            <li><a href="#">Vision</a></li>
            <li><a href="#">Values</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</div>

</body>
</html>
```


**Explanation:**

The code uses nested unordered lists (`<ul>`) to structure the menu.  CSS is used to style the lists, remove the default bullet points, and position the submenus absolutely. The `:hover` pseudo-class is crucial for showing the submenus on hover.  The `transition` property adds smooth animations.  The `position: relative` on parent list items is essential for the absolute positioning of submenus to work correctly.


**Links to Resources to Learn More:**

* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  (Comprehensive resource on all aspects of CSS)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Great blog and resource for CSS techniques)
* **FreeCodeCamp (CSS tutorials):** [https://www.freecodecamp.org/learn/responsive-web-design/](https://www.freecodecamp.org/learn/responsive-web-design/) (Interactive CSS lessons)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

