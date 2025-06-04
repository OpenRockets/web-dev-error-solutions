# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  We'll leverage CSS3's `clip-path` and `transform` properties to achieve this effect without the need for JavaScript. This example demonstrates a simple, customizable approach.


**Description of the Styling:**

The circular progress bar is built using two concentric circles: one acting as the background track and the other as the progress indicator. The progress indicator's arc is dynamically controlled using the `clip-path` property, which "clips" the circle to reveal only the desired portion representing the progress percentage.  We use CSS variables for easy customization of colors, sizes, and progress.

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
    position: relative;
  }

  .circular-progress .circle-bg {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 5px solid #ccc; /* Background track */
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .circular-progress .circle-progress {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    clip-path: circle(50% at 50% 50%); /* Initial clip */
    border: 5px solid #4CAF50; /* Progress color */
    position: absolute;
    transform: rotate(-90deg); /* Start at the top */
    --progress: 75; /* Adjust percentage here */
  }

  .circular-progress .circle-progress::before {
    content: var(--progress) "%";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  /* Animate the progress */
  .circular-progress.animated .circle-progress {
    animation: progress-animation 2s linear forwards;
  }

  @keyframes progress-animation {
    to {
      clip-path: circle(calc(var(--progress) * 3.6deg + 50%) at 50% 50%);
    }
  }
</style>
</head>
<body>

<div class="circular-progress animated">
  <div class="circle-bg"></div>
  <div class="circle-progress"></div>
</div>

</body>
</html>
```

**Explanation:**

* **`clip-path: circle(50% at 50% 50%);`**: This creates a circle.  The `circle()` function defines the clipping region.  `50%` represents a radius of 50% of the element's size, centered at `50% 50%`.
* **`transform: rotate(-90deg);`**:  This rotates the progress circle to start from the top.
* **`--progress: 75;`**: This CSS variable controls the percentage of the circle to fill.  The animation calculates the clip-path using this variable.
* **`@keyframes progress-animation`**: This defines the animation that smoothly changes the `clip-path` to represent the progress. Note the calculation `calc(var(--progress) * 3.6deg + 50%)`.  360 degrees divided by 100 is 3.6 degrees per percent. We add 50% to account for the initial rotation.
* **The `animated` class**: Add this class to the parent to trigger the animation


**Links to Resources to Learn More:**

* **CSS `clip-path`:** [MDN Web Docs - clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Variables (Custom Properties):** [MDN Web Docs - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

