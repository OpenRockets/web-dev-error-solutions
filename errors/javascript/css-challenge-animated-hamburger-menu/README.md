# 🐞 CSS Challenge:  Animated Hamburger Menu


This challenge involves creating an animated hamburger menu using pure CSS.  The menu will transform from three horizontal bars into an "X" shape upon clicking, mimicking a toggle effect commonly used for navigation.  We'll achieve this using CSS transitions and pseudo-elements. This example uses plain CSS3, but could easily be adapted to use a CSS framework like Tailwind.


**Description of the Styling:**

The core of the styling involves a simple container with three pseudo-elements (`::before`, `::after`, and the element itself) representing the hamburger lines.  On hover and active states, we use CSS transforms to rotate these elements, creating the "X" shape.  We also add transitions for a smooth animation.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Hamburger Menu</title>
<style>
.hamburger {
  width: 30px;
  height: 24px;
  position: relative;
  cursor: pointer;
  margin: 20px;
}

.hamburger, .hamburger::before, .hamburger::after {
  background-color: #333;
  transition: all 0.3s ease;
}

.hamburger::before, .hamburger::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  left: 0;
}

.hamburger::before {
  top: -8px;
}

.hamburger::after {
  bottom: -8px;
}

.hamburger.active::before {
  transform: rotate(45deg) translate(6px, 6px);
}

.hamburger.active::after {
  transform: rotate(-45deg) translate(6px, -6px);
}

.hamburger.active {
  background-color: transparent;
}
</style>
</head>
<body>

<div class="hamburger" onclick="this.classList.toggle('active')"></div>

</body>
</html>
```


**Explanation:**

* **`.hamburger`**: This class styles the main container.  `position: relative` is crucial for absolute positioning of the pseudo-elements.
* **`.hamburger::before`, `.hamburger::after`**: These create the top and bottom lines of the hamburger.  Absolute positioning allows precise placement relative to the parent.
* **`transition`**: This property ensures smooth animation when the `transform` property changes.
* **`.hamburger.active`**: This class is added on click (via JavaScript) and modifies the `transform` property of the pseudo-elements, creating the "X" shape. The background color is also changed to improve the visual effect.
* **`onclick="this.classList.toggle('active')"`**: This simple JavaScript snippet toggles the `active` class on the hamburger element when clicked.



**Links to Resources to Learn More:**

* **CSS Transitions:**  [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-elements:** [MDN Web Docs - CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

