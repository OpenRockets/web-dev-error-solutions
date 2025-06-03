# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This technique leverages the `clip-path` property and a pseudo-element to achieve a visually appealing and efficient progress indicator.

**Description of the Styling:**

The circular progress bar is created using a single `div` element.  A pseudo-element (`::before`) is used to create the circular track.  The `clip-path` property is used to dynamically "clip" a portion of the circular track, representing the progress.  We'll use variables for easy customization of the progress bar's appearance (color, size, etc.).

**Full Code:**

```html
<div class="progress-ring" data-progress="75">
  <span class="progress-value">75%</span>
</div>
```

```css
:root {
  --progress-ring-size: 150px;
  --progress-ring-color: #4CAF50;
  --progress-ring-track-color: #e0e0e0;
  --progress-ring-width: 10px;
}

.progress-ring {
  width: var(--progress-ring-size);
  height: var(--progress-ring-size);
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: var(--progress-ring-size);
  height: var(--progress-ring-size);
  background-color: var(--progress-ring-track-color);
  border-radius: 50%;
}

.progress-ring::after {
  content: "";
  position: absolute;
  width: var(--progress-ring-size);
  height: var(--progress-ring-size);
  background-color: var(--progress-ring-color);
  border-radius: 50%;
  clip-path: polygon(50% 50%, 50% 0%, 100% 0%, 100% 50%); /* Initial clip path */
  transform: rotate(-90deg); /* Start at top */
  transition: transform 0.5s ease; /* Smooth transition */
}

.progress-ring[data-progress]::after {
  --progress: calc(var(--progress) * 3.6deg); /* Convert percentage to degrees */
  transform: rotate(calc(var(--progress, 0deg) - 90deg)); /* Rotate based on progress */
}

.progress-value {
  position: absolute;
  z-index: 1;
  font-size: 1.2em;
  font-weight: bold;
  color: #333;
}

```

**Explanation:**

1. **Variables:**  The `:root` selector defines CSS custom properties (variables) for easy customization of the progress bar's size, colors, and width.

2. **`::before` Pseudo-element:** Creates the background circle (track).

3. **`::after` Pseudo-element:** Creates the filled portion of the progress bar.  The `clip-path` initially defines a triangle. The `transform: rotate()` rotates this triangle to create the circular fill effect.

4. **`data-progress` Attribute:** The HTML `data-progress` attribute is used to dynamically set the progress percentage.

5. **Calculation of Rotation:**  The CSS calculates the rotation angle based on the `data-progress` attribute. 360 degrees represent 100%, so we use `calc(var(--progress) * 3.6deg)` to convert the percentage to degrees.


**Links to Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Tricks on Pseudo-elements:** [https://css-tricks.com/pseudo-elements/](https://css-tricks.com/pseudo-elements/)
* **Understanding CSS Variables (Custom Properties):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

