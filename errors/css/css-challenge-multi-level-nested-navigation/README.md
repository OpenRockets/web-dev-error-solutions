# 🐞 CSS Challenge:  Multi-level Nested Navigation


This challenge involves creating a multi-level nested navigation menu using only CSS.  The goal is to achieve a clean, visually appealing, and easily expandable menu structure that works responsively across different screen sizes. We'll use CSS3 for styling, focusing on techniques like pseudo-elements, list styles, and transitions.


## Description of the Styling

The navigation will be a vertically stacked, multi-level menu.  Each menu item will have a dropdown arrow to indicate expandable sub-menus.  Sub-menus will slide out smoothly on hover.  The design will aim for a modern and minimalist aesthetic, utilizing subtle hover effects and clean typography.  We'll prioritize semantic HTML for accessibility.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Navigation</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
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
  position: relative;
  margin-bottom: 5px;
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
  left: 100%;
  top: 0;
  display: none;
  background-color: #f0f0f0;
  border: 1px solid #ddd;
}

.nav li:hover > ul {
  display: block;
}

.nav li::before {
  content: "\25BC"; /* Unicode for a downward-pointing triangle */
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  transition: transform 0.3s ease;
}

.nav li:hover::before {
  transform: translateY(-50%) rotate(90deg); /* Rotate on hover */
}

/* Responsive adjustments (example) */
@media (max-width: 768px) {
  .nav ul ul {
    left: 0;
    width: 100%;
  }
}
</style>
</head>
<body>

<nav class="nav">
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


## Explanation

The code utilizes nested unordered lists (`<ul>`) to create the menu structure.  CSS is used to style the lists, removing default list markers, positioning sub-menus absolutely, and using `display: none` to hide them initially.  The `:hover` pseudo-class shows the sub-menus on hover.  The `::before` pseudo-element adds the dropdown arrow, and its transformation on hover provides visual feedback.  Media queries are used to adjust the layout for smaller screens, making the sub-menus stack vertically.


## Links to Resources to Learn More

* **CSS Pseudo-classes and Pseudo-elements:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) and [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Transitions:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Positioning:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **Responsive Web Design:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

