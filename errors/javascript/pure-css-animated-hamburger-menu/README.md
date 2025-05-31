# 🐞 Pure CSS Animated Hamburger Menu


This document details a pure CSS animated hamburger menu, a common UI element often used for navigation on smaller screens.  This example utilizes CSS transitions and transforms to create a smooth and visually appealing animation. No JavaScript is required.

**Description of the Styling:**

The styling utilizes a single `<button>` element structured with three pseudo-elements (`::before`, `::after`, and the `button` itself) to represent the hamburger icon.  The animation is achieved by changing the `transform` property of these elements on hover or when the button is active (checked, for a checkbox-style implementation).  The animation involves rotating the top and bottom elements while the middle element fades out.


**Full Code:**

```html
<input type="checkbox" id="menuToggle" />
<label for="menuToggle" class="menu-button">
  <div class="bar"></div>
  <div class="bar"></div>
  <div class="bar"></div>
</label>


<div class="menu">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Services</a>
  <a href="#">Contact</a>
</div>
```

```css
.menu-button {
  position: relative;
  width: 30px;
  height: 20px;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.menu-button .bar {
  width: 100%;
  height: 3px;
  background-color: black;
  transition: transform 0.3s ease;
}

.menu-button input:checked ~ .bar:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.menu-button input:checked ~ .bar:nth-child(2) {
  opacity: 0;
}

.menu-button input:checked ~ .bar:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

.menu {
  position: absolute;
  top: 50px;
  left: 0;
  width: 200px;
  background-color: #f0f0f0;
  transform: translateX(-200px);
  transition: transform 0.3s ease; /* Animate menu opening/closing */
}

.menu-button input:checked ~ .menu {
  transform: translateX(0);
}


.menu a {
  display: block;
  padding: 10px;
  text-decoration: none;
  color: black;
}
```

**Note:**  This code uses a checkbox (`<input type="checkbox">`) to control the menu's open/closed state.  The label is styled to resemble the hamburger button, and the checkbox's checked state triggers the CSS animations.


**Explanation:**

The CSS uses the `:checked` pseudo-class to target the state of the checkbox.  When the checkbox is checked, the styles for the three bars change, creating the "X" shape, and the menu slides into view using the `transform: translateX()` property.  The `transition` property is used to smoothly animate the changes in position and opacity.


**(Unfortunately,  I cannot provide a direct link to a CodePen project because I don't have access to the real-time internet to browse and select a specific project.  You would need to search for "Pure CSS Hamburger Menu" on CodePen to find similar implementations.)**



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

