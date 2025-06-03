# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS. No JavaScript is required.  We'll achieve this effect using the `clip-path` property and some clever calculations. This example uses plain CSS, but the concepts are easily adaptable to frameworks like Tailwind CSS.

**Description of the Styling:**

The progress bar is created using a circle (`border-radius: 50%`) with a background color.  A pseudo-element (`::before`) is used to create the progress indicator. This pseudo-element is also a circle, but its visible portion is controlled using the `clip-path` property.  We'll use a `circle()` shape for the `clip-path`, dynamically adjusting its radius to simulate the progress.  The percentage of completion is controlled via a custom property (`--progress`).


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  --progress: 75; /* Adjust this value to change the progress (0-100) */
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #f0f0f0; /* Background color of the circle */
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
  background-color: #4CAF50; /* Color of the progress indicator */
  clip-path: circle(calc(var(--progress) / 100 * 100%) at 50% 50%);
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

* **`--progress` Variable:** This custom property sets the percentage of completion. Change its value (between 0 and 100) to alter the progress bar's fill.
* **`clip-path: circle(calc(var(--progress) / 100 * 100%) at 50% 50%);`:** This is the core of the effect.  `circle()` creates a circular clip-path. `calc(var(--progress) / 100 * 100%)` calculates the radius of the circle based on the `--progress` variable.  When `--progress` is 75, the radius becomes 75%, revealing 75% of the background circle. `at 50% 50%` centers the circle.
* **`translate(-50%, -50%)`:** This centers the pseudo-element within its parent.


**Resources to Learn More:**

* **MDN Web Docs - `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Tricks - Clip Paths:** [https://css-tricks.com/clipping-masking-css/](https://css-tricks.com/clipping-masking-css/) (This offers a broader understanding of clipping and masking in CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

