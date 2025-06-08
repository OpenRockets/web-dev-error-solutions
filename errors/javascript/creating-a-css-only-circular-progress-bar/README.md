# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS. No JavaScript is required. This example utilizes CSS variables (custom properties) for easy customization.

**Description of the Styling:**

The progress bar is created using two concentric circles. The outer circle acts as the background, while the inner circle represents the progress.  The inner circle's arc length is dynamically controlled using the `stroke-dasharray` and `stroke-dashoffset` properties.  CSS variables allow us to easily change the size, colors, and progress percentage.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
  .progress-ring {
    --size: 100; /* Size of the circle */
    --stroke-width: 10; /* Width of the circle stroke */
    --progress: 75; /* Percentage progress (0-100) */
    --color: #007bff; /* Color of the progress */

    width: var(--size);
    height: var(--size);
    position: relative;
  }

  .progress-ring svg {
    transform: rotate(-90deg); /* Start at the top */
  }

  .progress-ring circle {
    stroke-width: var(--stroke-width);
    stroke-linecap: round; /* Rounded ends */
    fill: transparent;
    cx: 50%;
    cy: 50%;
    r: calc((var(--size) - var(--stroke-width)) / 2);
  }

  .progress-ring .progress-background {
    stroke: #ccc; /* Background color */
  }

  .progress-ring .progress-foreground {
    stroke: var(--color);
    stroke-dasharray: calc(2 * 3.14159 * ((var(--size) - var(--stroke-width)) / 2));
    stroke-dashoffset: calc(2 * 3.14159 * ((var(--size) - var(--stroke-width)) / 2) * (1 - var(--progress) / 100));
  }
</style>
</head>
<body>

<div class="progress-ring">
  <svg width="100%" height="100%">
    <circle class="progress-background" r="45" />
    <circle class="progress-foreground" r="45" />
  </svg>
</div>

</body>
</html>
```

**Explanation:**

* **CSS Variables:**  The use of `--size`, `--stroke-width`, `--progress`, and `--color` makes it incredibly easy to customize the appearance of the progress bar.  Simply change the values of these variables to adjust the size, colors, and percentage.

* **`stroke-dasharray` and `stroke-dashoffset`:** These are the key CSS properties that create the progress effect. `stroke-dasharray` sets the total length of the dash, which is calculated as the circumference of the circle. `stroke-dashoffset` controls how much of the dash is hidden, effectively revealing the progress arc.

* **`transform: rotate(-90deg)`:** This rotates the SVG circle so that the progress starts at the top, rather than the right side.

* **`stroke-linecap: round`:** This creates smoothly rounded ends for the progress arc.

**Links to Resources to Learn More:**

* **MDN Web Docs on SVG:** [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
* **MDN Web Docs on CSS Variables:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
* **Understanding `stroke-dasharray` and `stroke-dashoffset`:** [Search for tutorials on these properties on sites like CSS-Tricks or YouTube.]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

