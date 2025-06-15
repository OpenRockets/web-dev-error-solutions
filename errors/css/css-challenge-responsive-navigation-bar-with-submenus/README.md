# 🐞 CSS Challenge: Responsive Navigation Bar with Submenus


This challenge focuses on creating a responsive navigation bar with dropdown submenus using CSS.  The navigation bar should adapt smoothly to different screen sizes, ensuring a good user experience on both desktop and mobile devices. We'll use plain CSS for this example, focusing on fundamental concepts.


**Description of the Styling:**

The navigation bar will contain a logo on the left, a list of main menu items, and a toggle button for smaller screens.  When a main menu item is hovered over (or tapped on mobile), a submenu will appear with additional links.  The styling will emphasize clean aesthetics and smooth transitions.  The overall design will aim for a modern, minimalist look.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<style>
nav {
  background-color: #333;
  overflow: hidden;
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

.submenu {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

nav li:hover .submenu {
  display: block;
}

/* Mobile responsiveness */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
  }

  nav li a {
    display: block;
    text-align: left;
  }

  .submenu {
    position: static;
  }
}

/* Logo Styling */
.logo {
  float: left;
  padding: 14px 16px;
}

.logo img {
  height: 30px;
}
</style>
</head>
<body>

<nav>
  <div class="logo"><img src="logo.png" alt="Logo"></div>  <!-- Replace logo.png with your logo -->
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a>
      <ul class="submenu">
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

* The main navigation uses a simple unordered list (`<ul>`) with list items (`<li>`) for each menu item.
* Floats are used to position the menu items horizontally.
* The `submenu` class is hidden by default and uses absolute positioning to appear below its parent list item.  `display: block;` on hover makes it visible.
* Media queries handle the responsive behavior for smaller screens.  On smaller screens, the floats are removed, and the submenu becomes statically positioned, simplifying the layout.
* A logo is added for completeness.  Remember to replace `"logo.png"` with an actual logo image.


**Links to Resources to Learn More:**

* **MDN Web Docs CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  (Comprehensive CSS reference)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Great articles and tutorials on CSS)
* **W3Schools CSS Tutorial:** [https://www.w3schools.com/css/](https://www.w3schools.com/css/) (Beginner-friendly CSS tutorial)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

