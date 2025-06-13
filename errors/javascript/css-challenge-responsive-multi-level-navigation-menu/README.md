# 🐞 CSS Challenge:  Responsive Multi-level Navigation Menu


This challenge focuses on creating a responsive multi-level navigation menu using CSS.  The menu should collapse into a hamburger menu on smaller screens and smoothly expand on hover.  We'll be using CSS Grid and Flexbox for layout and styling.  This example avoids JavaScript for simplicity, relying purely on CSS.

## Description of the Styling

The navigation menu consists of a main container with a logo on the left and navigation links on the right.  On larger screens (above 768px), the menu items are displayed horizontally. On smaller screens, the menu collapses into a hamburger icon. Clicking or hovering this icon reveals the nested menu items.  Sub-menus appear on hover, maintaining a clean and intuitive user experience. The styling emphasizes a modern, clean aesthetic.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Multi-Level Navigation</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
}

nav {
  background-color: #333;
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

.logo {
  font-size: 24px;
  font-weight: bold;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

li {
  margin-left: 20px;
}

a {
  color: #fff;
  text-decoration: none;
}

/* Hamburger Menu Styling */
.hamburger {
  display: none; /* Hidden on larger screens */
  cursor: pointer;
}

.hamburger span {
  display: block;
  width: 25px;
  height: 3px;
  margin: 5px;
  background-color: #fff;
  transition: all 0.3s ease;
}

.hamburger.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}


/* Responsive Styling */
@media (max-width: 768px) {
  nav ul {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background-color: #333;
    flex-direction: column;
  }

  nav ul li {
    margin: 0;
    width: 100%;
  }

  nav ul a{
    display:block;
    padding: 10px;
    text-align: center;
  }

  nav ul.active{
    display: flex;
  }

  .hamburger {
    display: block;
  }

  .logo {
    margin-right: auto;
  }
}

/* Submenu Styling */
.submenu {
  display: none;
  position: absolute;
  left: 100%;
  top: 0;
  background-color: #444;
}

li:hover > .submenu {
  display: block;
}
</style>
</head>
<body>

<nav>
  <div class="logo">My Website</div>
  <div class="hamburger" onclick="toggleMenu()">
    <span></span>
    <span></span>
    <span></span>
  </div>
  <ul id="nav-menu">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a>
      <ul class="submenu">
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Our Mission</a></li>
      </ul>
    </li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<script>
function toggleMenu() {
  const menu = document.getElementById('nav-menu');
  const hamburger = document.querySelector('.hamburger');
  menu.classList.toggle('active');
  hamburger.classList.toggle('active');
}
</script>

</body>
</html>
```

## Explanation

The code utilizes CSS for responsiveness.  The `@media` query handles the behavior below 768px, hiding the main navigation and revealing the hamburger menu.  The hamburger menu uses CSS transitions for a smooth animation.  The `submenu` class is hidden by default and revealed on hover using the `:hover` pseudo-class.  JavaScript is used only for a simple toggle to manage the visibility of the mobile menu.

## Links to Resources to Learn More

* **CSS Grid Layout:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* **CSS Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **CSS Responsive Design:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

