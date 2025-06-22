# 🐞 CSS Challenge: Responsive Hamburger Menu


This challenge focuses on creating a responsive hamburger menu using pure CSS.  The menu should be a simple three-line icon that expands to reveal a navigation list on click.  The styling should be clean and modern, adapting seamlessly to different screen sizes. We'll be using CSS3 for this implementation.

**Description of the Styling:**

The hamburger menu will be a square button containing three horizontal lines. On smaller screens (e.g., mobile), the menu will be visible. When clicked, the three lines will transform into an "X" shape, and the navigation list will slide in from the left.  On larger screens (e.g., desktop), the navigation list will be visible by default, and the hamburger menu will be hidden.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Hamburger Menu</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
}

.menu-button {
  display: none; /* Hidden by default on larger screens */
  cursor: pointer;
  position: absolute;
  top: 20px;
  left: 20px;
  z-index: 1;
}

.menu-button span {
  display: block;
  width: 30px;
  height: 3px;
  background-color: black;
  margin: 5px 0;
  transition: transform 0.4s ease;
}

.menu-button.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.menu-button.active span:nth-child(2) {
  opacity: 0;
}

.menu-button.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

.nav-list {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.8);
  transform: translateX(-100%); /* Initially off-screen */
  transition: transform 0.4s ease;
  opacity: 0;
  z-index: 0;
}

.nav-list.active {
  transform: translateX(0); /* Slide in from the left */
  opacity: 1;
}

.nav-list ul {
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;
}

.nav-list li {
  margin: 20px 0;
}

.nav-list a {
  display: block;
  color: white;
  text-decoration: none;
  font-size: 20px;
}

@media (min-width: 768px) {
  .menu-button {
    display: none;
  }
  .nav-list {
    position: static;
    background-color: transparent;
    transform: translateX(0);
    opacity: 1;
    width: auto;
    height: auto;
    text-align: center;
  }
}
</style>
</head>
<body>

<div class="menu-button" onclick="toggleMenu()">
  <span></span>
  <span></span>
  <span></span>
</div>

<div class="nav-list" id="nav-list">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</div>

<script>
function toggleMenu() {
  const menuButton = document.querySelector('.menu-button');
  const navList = document.getElementById('nav-list');
  menuButton.classList.toggle('active');
  navList.classList.toggle('active');
}
</script>

</body>
</html>
```

**Explanation:**

*   The HTML sets up a hamburger menu button and a navigation list.
*   The CSS styles the button, creating the three lines and the transition effect.  Media queries are used for responsiveness.
*   JavaScript adds interactivity, toggling the classes to show/hide the menu.


**Links to Resources to Learn More:**

*   [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
*   [CSS-Tricks](https://css-tricks.com/)
*   [freeCodeCamp - Responsive Web Design](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

