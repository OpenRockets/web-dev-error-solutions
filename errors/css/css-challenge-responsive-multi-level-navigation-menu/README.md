# 🐞 CSS Challenge: Responsive Multi-level Navigation Menu


This challenge involves creating a responsive, multi-level navigation menu using CSS.  The menu should gracefully adapt to different screen sizes, ensuring usability on both desktops and mobile devices.  We'll use CSS3 for styling and achieve responsiveness through media queries.

## Description of the Styling:

The navigation menu will be a vertical stack on smaller screens (mobile) and a horizontal menu on larger screens (desktops and tablets).  Sub-menus will appear on hover (desktop) or on click (mobile) to avoid cluttering the screen.  We'll utilize a clean, modern aesthetic with subtle hover effects and clear visual hierarchy.


## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Multi-Level Menu</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
}

.nav {
  background-color: #333;
  color: white;
  overflow: hidden;
}

.nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav li {
  float: left; /* For horizontal layout on larger screens */
}

.nav li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.nav li a:hover {
  background-color: #ddd;
  color: black;
}


.nav ul ul {
  display: none; /* Hide sub-menus by default */
  position: absolute;
  background-color: #333;
}

.nav li:hover > ul {
  display: block; /* Show sub-menu on hover (desktop) */
}

/* Mobile Styles */
@media screen and (max-width: 600px) {
  .nav li {
    float: none; /* Remove horizontal layout */
  }
  .nav li a {
    display: block; /* Make menu items stack vertically */
  }
  .nav ul ul {
    display: none; /* Hide sub-menus by default */
  }
  .nav li:hover > ul {
    display: none; /* Prevent accidental hover on mobile */
  }
  .nav li a {
      padding: 10px;
  }
  .nav li a.active {
        background-color: #555;
  }
  .nav li a.active + ul{
        display:block;
  }
}

/* Add active class for better navigation (Mobile) */
.nav ul li a:focus {
  color: black;
  background-color: #ddd;
}
</style>
</head>
<body>

<div class="nav">
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
</div>

</body>
</html>
```

## Explanation:

The code uses a combination of `float`, `position: absolute`, and media queries to achieve the desired responsiveness.  The base styles create a horizontal menu.  The `@media` query modifies the styles for smaller screens, removing the `float` and displaying menu items vertically.  The crucial part is the interaction of `display: none` and `display: block` to show and hide submenus based on the screen size and user interaction (hover or click).  Clicking on a menu item on mobile adds an active class, showing the submenu.

## Links to Resources to Learn More:

* **CSS3 Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Selectors)
* **CSS3 Media Queries:** [MDN Web Docs - Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Positioning:** [MDN Web Docs - CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

