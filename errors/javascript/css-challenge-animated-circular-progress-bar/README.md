# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using pure CSS.  The bar will fill up gradually, simulating progress. We'll utilize CSS variables and animations for a clean and efficient solution.  No JavaScript will be required.


## Description of the Styling

The progress bar will be a circle with a thicker ring representing the track. The inner ring will fill up to represent the percentage of progress.  The animation will smoothly fill this inner ring from 0% to a specified value (e.g., 75%).  We'll use CSS variables to easily control the color, size, and progress percentage.

## Full Code (CSS Only)

```css
:root {
  --progress-color: #007bff; /* Progress bar color */
  --track-color: #e0e0e0;  /* Track color */
  --progress-width: 10px; /* Width of the progress and track */
  --size: 100px;          /* Size of the circle */
  --progress-percentage: 75%; /* Percentage of progress */
}

.progress-ring {
  width: var(--size);
  height: var(--size);
  position: relative;
  display: inline-block;
}

.progress-ring svg {
  transform: rotate(-90deg); /* Start at the top */
}

.progress-ring circle {
  stroke-width: var(--progress-width);
  stroke-linecap: round;
  fill: transparent;
  stroke-dasharray: calc(2 * 3.14159 * var(--size) / 2); /* Circumference */
}

.progress-ring .progress-track {
  stroke: var(--track-color);
}

.progress-ring .progress-bar {
  stroke: var(--progress-color);
  stroke-dashoffset: calc(100% - var(--progress-percentage));
  animation: fill-progress 2s linear forwards;
}

@keyframes fill-progress {
  from {
    stroke-dashoffset: calc(100% - var(--progress-percentage));
  }
  to {
    stroke-dashoffset: 0;
  }
}


/* Example usage: */
<div class="progress-ring">
  <svg width="100" height="100">
    <circle class="progress-track" cx="50" cy="50" r="45"></circle>
    <circle class="progress-bar" cx="50" cy="50" r="45"></circle>
  </svg>
</div>

```

You'll need to embed this CSS within `<style>` tags or a linked stylesheet.  The provided HTML snippet demonstrates how to use the CSS.

## Explanation

* **CSS Variables:**  Using `var(--variable-name)` allows for easy customization of colors, sizes, and progress percentage.
* **SVG for the Circle:** An SVG `<circle>` element is used to create the circular shape.  This is more efficient than trying to approximate a circle using borders or other techniques.
* **`stroke-dasharray` and `stroke-dashoffset`:** These properties are key to creating the progress bar effect. `stroke-dasharray` sets the total length of the dash (the circumference), and `stroke-dashoffset` controls how much of the dash is hidden.
* **Animation:** The `@keyframes` rule smoothly animates the `stroke-dashoffset` property, creating the filling effect.  `linear` ensures a consistent animation speed. `forwards` makes the animation stay at its final state.

## Links to Resources to Learn More

* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **MDN Web Docs - SVG `<circle>` element:** [https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle)
* **Understanding `stroke-dasharray` and `stroke-dashoffset`:** Search for tutorials on these CSS properties; many visual explanations are available.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

