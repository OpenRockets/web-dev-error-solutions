# 🐞 CSS Challenge:  Animated Hamburger Menu


This challenge involves creating an animated hamburger menu using pure CSS.  The menu will transform from three horizontal lines to an "X" shape upon clicking, simulating a toggle effect commonly used for navigation. We'll leverage CSS transitions and transforms to achieve the animation.  While this could be done with JavaScript, the challenge focuses on a pure CSS solution.

**Description of the Styling:**

The hamburger menu will consist of three divs representing the lines.  We'll use absolute positioning to place these lines within a container.  The animation will involve rotating the lines and slightly changing their position to create the "X" effect.  We'll use CSS transitions for a smooth animation.  We will also style the active state of the menu (when it's in "X" form).


**Full Code (CSS only):**

```css
.hamburger-menu {
  width: 30px;
  height: 24px;
  position: relative;
  cursor: pointer;
}

.hamburger-menu .line {
  width: 100%;
  height: 3px;
  background-color: #333;
  position: absolute;
  transition: all 0.3s ease;
}

.hamburger-menu .line:nth-child(1) {
  top: 0;
}

.hamburger-menu .line:nth-child(2) {
  top: 50%;
  transform: translateY(-50%);
}

.hamburger-menu .line:nth-child(3) {
  bottom: 0;
}


.hamburger-menu.active .line:nth-child(1) {
  transform: rotate(45deg) translate(7px, 7px);
}

.hamburger-menu.active .line:nth-child(2) {
  opacity: 0;
}

.hamburger-menu.active .line:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -7px);
}

/* Optional: Add some styling for the menu content */
.menu-content {
    display: none; /* Hidden by default */
}

.hamburger-menu.active ~ .menu-content {
  display: block; /* Show menu content when hamburger is active */
}
```

**HTML (required to use the CSS):**

```html
<div class="hamburger-menu" onclick="this.classList.toggle('active')">
  <div class="line"></div>
  <div class="line"></div>
  <div class="line"></div>
</div>
<div class="menu-content">
  <!-- Your menu items here -->
  <ul>
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
  </ul>
</div>
```


**Explanation:**

* **`.hamburger-menu`**: This class styles the overall container.
* **`.hamburger-menu .line`**: Styles each of the three lines.  `transition: all 0.3s ease;` is crucial for the animation.
* **`:nth-child`**:  Selects each line individually for positioning.
* **`.hamburger-menu.active`**:  This styles the menu when the `active` class is added (on click).  The transforms rotate and translate the lines to form the "X".  The opacity change for the middle line makes it disappear smoothly.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (various CSS tutorials):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

