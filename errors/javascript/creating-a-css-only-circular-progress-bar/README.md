# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required!  This example utilizes CSS variables for easy customization.


**Description of the Styling:**

This technique leverages the `clip-path` property to create a circular segment representing the progress. We use a pseudo-element (`::before`) to create the circle, and a rotation transform to visually represent the progress percentage.  CSS variables control the size, color, and progress percentage.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  --size: 100px; /* Control the size of the progress ring */
  --progress: 75; /* Control the progress percentage (0-100) */
  --primary-color: #4CAF50; /* Primary color of the progress */
  --secondary-color: #e0e0e0; /* Secondary color (background) */

  width: var(--size);
  height: var(--size);
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: var(--size);
  height: var(--size);
  background-color: var(--secondary-color);
  border-radius: 50%;
}

.progress-ring::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: var(--size);
  height: var(--size);
  background-color: var(--primary-color);
  border-radius: 50%;
  clip-path: polygon(50% 50%, 100% 50%, 100% 0, 50% 0); /*Initial shape*/
  transform: rotate(calc(var(--progress) * 3.6deg)); /*Rotate based on progress*/
  transform-origin: 50% 50%;
}
</style>
</head>
<body>

<h1>CSS Circular Progress Bar</h1>
<div class="progress-ring"></div>

</body>
</html>
```


**Explanation:**

* **`--size`, `--progress`, `--primary-color`, `--secondary-color`:** These CSS variables allow for easy customization of the progress bar's appearance.
* **`.progress-ring::before`:** This creates the background circle using `border-radius: 50%`.
* **`.progress-ring::after`:** This creates the progress segment.  The `clip-path` initially defines a triangle. The `transform: rotate()`  rotates this triangle based on the `--progress` variable.  `calc(var(--progress) * 3.6deg)` converts the percentage to degrees (360 degrees in a circle).
* **`transform-origin: 50% 50%;`:** Sets the rotation origin to the center of the circle.


**Links to Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs on CSS Variables:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
* **CSS-Tricks (general CSS resource):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

