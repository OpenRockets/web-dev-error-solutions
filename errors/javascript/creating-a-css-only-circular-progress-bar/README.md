# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This utilizes CSS gradients and the `clip-path` property for a clean and efficient solution.  This example will be styled using plain CSS, but the concepts can be easily adapted to frameworks like Tailwind CSS.

**Description of the Styling:**

The progress bar is created using a circle. A semi-circle representing the progress is overlaid on top.  The semi-circle's size and visibility are controlled via CSS variables, making it easily customizable. The `clip-path` property cuts the circle into a semi-circle, creating the progress bar effect.  We use a linear gradient to add color to the progress.


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
  background: conic-gradient(
    #ddd 0%,
    #ddd calc(var(--progress) * 1%),
    #4CAF50 calc(var(--progress) * 1%),
    #4CAF50 100%
  );
  clip-path: inset(0 round 0 0); /* This is the important part! Adjust 0 for the inset amount */
  position: relative;
}

.circular-progress::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: white;
  z-index: 1; /* Ensure it's on top of the progress */
}

.circular-progress-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px; /* Adjust as needed */
}
</style>
</head>
<body>

<div class="circular-progress-container">
  <div class="circular-progress" style="--progress: 0.75;"></div> </div>

</body>
</html>
```

**Explanation:**

* **`conic-gradient`:** This creates a radial gradient that starts from the top and goes clockwise.  We use two colors (`#ddd` and `#4CAF50`) to represent the empty and filled portions of the circle, respectively.  `calc(var(--progress) * 1%)` dynamically calculates the percentage of the circle to fill based on the `--progress` CSS variable.
* **`clip-path: inset(0 round 0 0);`:** This is the key to creating the semi-circle.  The `inset()` function creates an inset shape. `round` creates the rounded corners. Adjust the values to modify the shape or start position.
* **CSS Variables (`--progress`):** This allows you to easily change the percentage of the progress bar by simply adjusting the value within the `style` attribute of the `.circular-progress` div.  The value should be between 0 and 1 (representing 0% to 100%).
* **`::before` Pseudo-element:** This creates a white circle on top to give the appearance of a clear center.

**Resources to Learn More:**

* **CSS Gradients:** [MDN Web Docs - CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* **CSS Clip-path:** [MDN Web Docs - CSS clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Variables:** [MDN Web Docs - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

