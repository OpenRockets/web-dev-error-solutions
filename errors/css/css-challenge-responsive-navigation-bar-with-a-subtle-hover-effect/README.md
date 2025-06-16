# 🐞 CSS Challenge:  Responsive Navigation Bar with a Subtle Hover Effect


This challenge focuses on creating a responsive navigation bar using CSS.  The navigation bar should adapt smoothly to different screen sizes and include a subtle hover effect on the menu items. We'll be using plain CSS3 for this, avoiding any CSS frameworks like Tailwind for clarity.

**Description of the Styling:**

The navigation bar will be positioned at the top of the page and have a fixed width.  On larger screens, the menu items will be displayed inline, while on smaller screens, they'll collapse into a hamburger menu icon. The hover effect will subtly change the background color of the menu item on mouse-over.  The overall design aims for a clean and modern aesthetic.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<style>
body {
  margin: 0;
  font-family: sans-serif;
}

nav {
  background-color: #333;
  color: white;
  overflow: hidden;
  position: fixed;
  width: 100%;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

nav li {
  float: left;
}

nav li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav li a:hover {
  background-color: #ddd;
  color: black;
}

/* Responsive design - when the screen is less than 600px wide, hide all list items except the first one */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
  }

  nav li a {
    display: block;
    text-align: left;
  }
}
</style>
</head>
<body>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<p>This is some sample content below the navigation bar.</p>

</body>
</html>
```

**Explanation:**

* **Basic Structure:**  The HTML uses an unordered list (`<ul>`) to create the menu items.  Each list item (`<li>`) contains a link (`<a>`).
* **Styling:** The CSS uses `float: left;` to arrange the menu items horizontally.  The `@media` query handles responsive design, changing the layout for smaller screens.  The `:hover` pseudo-class creates the hover effect.
* **Responsiveness:** The `@media screen and (max-width: 600px)` rule ensures that on screens narrower than 600px, the menu items stack vertically, making the navigation usable on mobile devices.

**Links to Resources to Learn More:**

* **CSS Basics:** [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Responsive Web Design:** [MDN Web Docs - Responsive Web Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_design)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

