# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This example uses CSS variables for easy customization.

**Description of the Styling:**

This technique leverages the `clip-path` property with a circle to create the progress bar's arc.  A background circle provides the track, while a foreground circle, clipped using `clip-path`, shows the progress.  CSS variables control the size, colors, and progress percentage.

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
    background-color: #f0f0f0; /* Track color */
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
    background-color: #4CAF50; /* Progress color */
    clip-path: circle(50% at 50% 50%); /* initially a full circle */
    --progress: 75; /* Adjust this to change progress % */
    animation: progress 2s linear forwards; 
  }

  @keyframes progress {
    to {
      clip-path: circle(50% at 50% calc(50% - var(--progress) * 1%));
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

* **`.progress-ring`:** This sets up the base container with a circular shape and background color.
* **`.progress-ring::before`:** A pseudo-element is created to represent the progress bar.  `transform: translate(-50%, -50%)` centers it within the parent.
* **`clip-path: circle(...)`:** This is the key element. It creates a circular clipping region. The `at` keyword specifies the center point, and the calculation `calc(50% - var(--progress) * 1%)` dynamically adjusts the circle's radius based on the `--progress` CSS variable.  The animation smoothly changes this over time.
* **`--progress`:** This CSS variable controls the percentage of the circle that is visible.  Change its value to alter the progress displayed.
* **`@keyframes progress`:**  This animation smoothly changes the `clip-path` over 2 seconds, creating a visual progress effect.

**Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS-Tricks on `clip-path`:** [https://css-tricks.com/almanac/properties/c/clip-path/](https://css-tricks.com/almanac/properties/c/clip-path/)
* **Understanding CSS Variables (Custom Properties):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

