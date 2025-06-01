# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This technique leverages the `clip-path` property and some clever calculations to achieve a visually appealing and dynamic progress indicator.

**Description of the Styling:**

This circular progress bar is built using a single SVG element.  The `clip-path` property is used to dynamically "clip" a circle, revealing only a portion representing the progress percentage.  We use CSS variables to easily adjust the size, colors, and progress value.

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
    background-color: #f0f0f0; /* Light grey background */
    position: relative;
  }

  .progress-ring__circle {
    width: 100%;
    height: 100%;
    clip-path: circle(50% at 50% 50%); /*Creates a circle*/
    background-color: #4CAF50; /* Green progress color */
    position: absolute;
    transform: rotate(-90deg); /* Start at the top */
    --progress: 75; /* Adjust this value for progress */
    animation: progress 2s linear forwards; /* Animated progress */
  }

  .progress-ring__circle::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    background: inherit;
    clip-path: circle(50% at 50% 50%) rotate(calc(var(--progress) * 3.6deg)); /* dynamic progress rotation*/
    /*animation: progress 2s linear forwards; uncomment for animated progress*/
  }


  @keyframes progress {
    to {
      clip-path: circle(50% at 50% 50%) rotate(calc(var(--progress) * 3.6deg));
    }
  }
</style>
</head>
<body>

<div class="progress-ring">
  <div class="progress-ring__circle"></div>
</div>

</body>
</html>
```

**Explanation:**

* **`progress-ring`:** This div acts as a container, setting the size and basic shape of the progress bar.
* **`progress-ring__circle`:** This div creates the circular background.  The `clip-path: circle(...)` creates the circular shape.  `transform: rotate(-90deg);` starts the progress at the top.  The `--progress` CSS variable controls the percentage complete. `animation` provides basic animation (uncomment it to enable.)
* **`progress-ring__circle::before`:** This pseudo-element is crucial. It uses `clip-path` and `rotate` to create the dynamic progress arc.  The calculation `calc(var(--progress) * 3.6deg)` converts the percentage (0-100) into degrees (0-360).
* **`@keyframes progress`:** This defines the animation that smoothly updates the progress bar.

**Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Tricks on Circular Progress Bars:** (Search for "CSS circular progress bar" on CSS Tricks for various approaches)

By adjusting the `--progress` variable in the CSS, you can easily change the progress level displayed. You can also customize the colors and sizes to match your design.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

