# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript required! This uses standard CSS3 properties and avoids any external libraries.

**Description of the Styling:**

This technique leverages CSS's `clip-path` property to create a circular mask on a wider circle. By manipulating the `rotate()` transform and the `clip-path` circle's size, we simulate a progress bar that fills up a circular track. The `background` property creates the color of the progress bar.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Circular Progress Bar</title>
<style>
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #f0f0f0; /* Track background color */
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #4CAF50; /* Progress bar color */
  clip-path: circle(50% at 50% 50%); /* Initial clip path */
  animation: progress-bar 2s linear forwards; /* Animate the progress bar */
}

@keyframes progress-bar {
  100% {
    clip-path: circle(50% at 50% 0%); /* Final clip path at 100% */
    transform: translate(-50%, -50%) rotate(360deg); /* Rotate for full circle */
  }
}

</style>
</head>
<body>

<h1>Circular Progress Bar</h1>
<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

*   **`progress-ring`**: This is the main container, setting the size and basic shape of the progress bar.
*   **`progress-ring::before`**: This pseudo-element creates the actual progress bar using `content: ""`.  It's positioned absolutely within the container.
*   **`clip-path: circle(50% at 50% 50%)`**: This initially creates a full circle.  The `at 50% 50%` centers the circle.
*   **`animation: progress-bar 2s linear forwards`**: This applies the `progress-bar` animation over 2 seconds with a linear speed and makes it stay at the end.
*   **`@keyframes progress-bar`**: This defines the animation, changing the `clip-path` to create the progress effect and rotating the element for a complete circle visualization.  You can change the `circle()` value to adjust the percentage of progress.  The rotation makes it visually appealing.


**Links to Resources to Learn More:**

*   **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
*   **CSS-Tricks on Animations:** [https://css-tricks.com/snippets/css/keyframe-animation-syntax/](https://css-tricks.com/snippets/css/keyframe-animation-syntax/)
*   **Understanding `transform: rotate()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

