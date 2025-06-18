# 🐞 CSS Challenge:  Animated Hamburger Menu


This challenge involves creating an animated hamburger menu using pure CSS.  The menu will transition from a classic three-line hamburger icon to an "X" shape when clicked, revealing a navigation list. We'll leverage CSS transitions and transforms for the animation effect.  This example uses plain CSS3; a Tailwind CSS version would simply involve applying Tailwind classes to the existing structure.


## Description of the Styling

The hamburger menu consists of three horizontal bars. On click, these bars rotate and translate to form an "X" shape. Simultaneously, a navigation list slides in from the left.  The styling focuses on creating a smooth, visually appealing animation. The color scheme is intentionally kept simple for clarity.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Hamburger Menu</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
}

.hamburger-menu {
  position: relative;
  width: 30px;
  height: 24px;
  cursor: pointer;
  margin: 20px;
}

.bar {
  width: 100%;
  height: 4px;
  background-color: #333;
  margin: 6px 0;
  transition: transform 0.3s ease-in-out;
  background-color: black;
}

.hamburger-menu.active .bar:nth-child(1) {
  transform: rotate(45deg) translate(8px, 8px);
}

.hamburger-menu.active .bar:nth-child(2) {
  opacity: 0;
}

.hamburger-menu.active .bar:nth-child(3) {
  transform: rotate(-45deg) translate(8px, -8px);
}


.nav-list {
  position: absolute;
  top: 0;
  left: -200px; /* Initially hidden */
  width: 200px;
  height: 100%;
  background-color: #f0f0f0;
  transition: left 0.3s ease-in-out;
  list-style: none;
  padding: 20px;
}

.hamburger-menu.active ~ .nav-list {
  left: 0; /* Revealed on click */
}

.nav-list li {
  margin-bottom: 10px;
}

.nav-list a {
  text-decoration: none;
  color: #333;
}
</style>
</head>
<body>

<div class="hamburger-menu" onclick="toggleMenu()">
  <div class="bar"></div>
  <div class="bar"></div>
  <div class="bar"></div>
</div>

<ul class="nav-list">
  <li><a href="#">Home</a></li>
  <li><a href="#">About</a></li>
  <li><a href="#">Services</a></li>
  <li><a href="#">Contact</a></li>
</ul>

<script>
function toggleMenu() {
  document.querySelector('.hamburger-menu').classList.toggle('active');
}
</script>

</body>
</html>
```


## Explanation

1. **HTML Structure:** The HTML sets up a `div` with the class `hamburger-menu` containing three `div` elements representing the bars.  A `<ul>` element with the class `nav-list` holds the navigation links.

2. **CSS Styling:** The CSS styles the hamburger menu initially and defines the transformations (rotation and translation) applied to the bars when the `active` class is added. It also handles the sliding animation of the navigation list using the `left` property and transitions.

3. **JavaScript Functionality:** The JavaScript function `toggleMenu()` adds or removes the `active` class from the `hamburger-menu` element when clicked, triggering the animation.


## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Selectors:**  [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

