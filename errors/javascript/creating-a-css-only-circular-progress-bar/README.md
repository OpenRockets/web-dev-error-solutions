# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This technique leverages CSS's `clip-path` property and a pseudo-element to create a visually appealing and performant progress indicator.

**Description of the Styling:**

The progress bar is composed of two concentric circles. The outer circle acts as the background, while the inner circle represents the progress.  The `clip-path` property is used to create a circular "mask" on the inner circle, revealing only a portion based on the progress percentage.  This is achieved by dynamically adjusting the `clip-path`'s `circle()` function.  The styling includes customization options for colors, sizes, and stroke widths.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.circular-progress {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  position: relative;
}

.circular-progress::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background-color: #f0f0f0; /* Background color */
  z-index: 1; /* Ensure it's behind the progress */
}

.circular-progress::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background-color: #4CAF50; /* Progress color */
  z-index: 2; /* On top of the background */
  clip-path: circle(50% at 50% 50%); /* Adjust percentage here for progress */
}


.progress-75 .circular-progress::after {
  clip-path: circle(75% at 50% 50%);
}

.progress-50 .circular-progress::after {
  clip-path: circle(50% at 50% 50%);
}

.progress-25 .circular-progress::after {
  clip-path: circle(25% at 50% 50%);
}

</style>
</head>
<body>

<h1>CSS Only Circular Progress Bar</h1>

<div class="circular-progress progress-75"></div>
<div class="circular-progress progress-50"></div>
<div class="circular-progress progress-25"></div>

</body>
</html>
```

**Explanation:**

*   The `.circular-progress` class sets up the basic structure: a square div with rounded corners to form a circle.
*   The `::before` pseudo-element creates the background circle.
*   The `::after` pseudo-element creates the progress circle.  Its `clip-path` is dynamically adjusted to show the desired percentage.  The example shows 75%, 50%, and 25% progress examples with separate classes.  You would need to change the `clip-path: circle(X% at 50% 50%);`  to adjust the percentage.  The `at 50% 50%` centers the circle.

**Links to Resources to Learn More:**

*   [MDN Web Docs on `clip-path`](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
*   [CSS-Tricks on `clip-path`](https://css-tricks.com/clipping-masking-css/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

