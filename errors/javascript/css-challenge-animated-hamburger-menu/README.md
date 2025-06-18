# 🐞 CSS Challenge:  Animated Hamburger Menu


This challenge involves creating an animated hamburger menu using pure CSS.  The menu will transition from a stacked hamburger icon to an "X" when clicked, revealing a navigation list. We'll utilize CSS transitions and transforms to achieve the animation effect.  No JavaScript is required.


## Description of the Styling:

The hamburger menu will consist of three horizontal bars. On click, the top and bottom bars will rotate 45 degrees, moving diagonally to create the "X" shape.  Simultaneously, a navigation list will slide in from the left (or right, depending on your preference). The styling will be clean and modern, aiming for a smooth user experience.


## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Hamburger Menu</title>
<style>
body {
  background-color: #f0f0f0;
  font-family: sans-serif;
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
  height: 3px;
  background-color: #333;
  margin-bottom: 5px;
  transition: transform 0.3s ease-in-out;
  transform-origin: center;
}

.hamburger-menu.active .bar:nth-child(1) {
  transform: rotate(45deg) translate(7px, 7px);
}

.hamburger-menu.active .bar:nth-child(2) {
  opacity: 0;
}

.hamburger-menu.active .bar:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -7px);
}

.nav-list {
  position: absolute;
  top: 0;
  left: -200px; /* Initially off-screen */
  width: 200px;
  background-color: #fff;
  padding: 20px;
  transition: left 0.3s ease-in-out;
  list-style: none;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
}

.hamburger-menu.active ~ .nav-list {
  left: 0; /* Slide in on activation */
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

<div class="hamburger-menu" onclick="this.classList.toggle('active')">
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

</body>
</html>
```


## Explanation:

1.  **HTML Structure:**  The HTML sets up a `div` with the class `hamburger-menu` containing three `div` elements representing the bars.  A navigation list (`ul`) follows.

2.  **CSS Styling:** The CSS styles the bars, giving them a basic appearance and applying transitions for smooth animation. The `transform-origin: center;` is crucial for the rotation effect.

3.  **CSS Transitions and Transforms:**  The key animation is achieved using the `.active` class. When the hamburger menu is clicked, `this.classList.toggle('active')` adds or removes the `active` class. This class then triggers the CSS transitions and transforms, rotating the bars and sliding in the navigation list. The `translate` function helps position the rotated bars correctly.

4.  **Adjacent Sibling Selector (`~`):**  The `~` selector targets the `.nav-list` element only when it's a sibling of the `.hamburger-menu` and the `.hamburger-menu` has the `.active` class.  This ensures the navigation list only animates when the hamburger menu is clicked.

## Links to Resources to Learn More:

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

