# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  This avoids the need for JavaScript, making it lightweight and efficient. We'll use CSS3 properties to achieve the circular shape and animation.


**Description of the Styling:**

This technique uses a combination of `border-radius`, `transform`, and `animation` properties to create a visually appealing circular progress bar. A pseudo-element (`::before`) is used to create the animated progress ring.  The percentage of completion is controlled by a CSS variable, allowing for easy modification.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #f0f0f0; /* Light gray background */
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 10px solid transparent; /* Adjust border width as needed */
  border-top-color: #007bff; /* Blue progress color */
  animation: progress-bar 2s linear forwards;
}

/* Adjust percentage via CSS variable */
:root {
    --progress-percentage: 75; /* Percentage complete (0-100) */
}

@keyframes progress-bar {
  to {
    transform: rotate(calc(var(--progress-percentage) * 3.6deg));
  }
}

</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

* **`.progress-ring`:** This class sets the basic dimensions, shape, and background of the circular progress bar.  `position: relative` is crucial for positioning the pseudo-element.

* **`.progress-ring::before`:** This pseudo-element creates the circular progress ring.  `border-radius: 50%` makes it circular.  `border-top-color` sets the color of the progress bar.  The `animation` property applies the `progress-bar` animation.

* **`:root { --progress-percentage: 75; }`:**  This sets a CSS variable to control the progress percentage.  Changing this value will dynamically adjust the progress bar.

* **`@keyframes progress-bar`:** This defines the animation.  `transform: rotate()` rotates the border, creating the progress effect. `calc(var(--progress-percentage) * 3.6deg)` calculates the rotation angle based on the percentage (360 degrees / 100% = 3.6 degrees per percentage point).  `linear` ensures a smooth animation. `forwards` keeps the animation at its final state.


**Links to Resources to Learn More:**

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Variables (Custom Properties):** [MDN Web Docs - CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
* **Understanding `calc()` in CSS:** [MDN Web Docs - calc()](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

