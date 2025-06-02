# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required! This example utilizes pure CSS and leverages the `conic-gradient` function for a smooth, visually appealing result.

**Description of the Styling:**

This technique uses a combination of a circle created with `border-radius` and a `conic-gradient` to represent the progress. The `conic-gradient` allows us to create a gradient that starts at a specific angle and sweeps across a specified portion of the circle, representing the percentage of completion. We use a pseudo-element (`::before`) to create the progress indicator on top of the base circle.  Styling is kept concise for clarity, but could easily be customized with colors, fonts, and sizes.

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
  background-color: #f0f0f0; /* Light gray background */
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: conic-gradient(#4CAF50 75%, #e0e0e0 75%); /* Green progress, gray background */
  mask: conic-gradient(#fff 0%, #fff 75%, transparent 75%); /* Creates the circular cut-out */
  mask-type:luminosity;
  transform: rotate(calc(var(--progress) * 3.6deg));
}

/* Example usage with variable progress */
.progress-ring--75 {
  --progress: 75;
}
</style>
</head>
<body>

<h1>Circular Progress: 75%</h1>
<div class="progress-ring progress-ring--75">
  <span>75%</span>
</div>

<h1>Circular Progress: 25%</h1>
<div class="progress-ring progress-ring--25">
  <span>25%</span>
</div>

</body>
</html>
```

**Explanation:**

* **`progress-ring`:** This class styles the base circle.  `border-radius: 50%` creates the circular shape.
* **`::before` pseudo-element:** This creates the progress indicator.
    * `conic-gradient`: This creates the circular gradient.  The first color is the progress color, and the second color is the background. The percentage value determines the extent of the progress.
    * `mask` and `mask-type`: This is crucial for creating the clean cut-out effect, ensuring only the specified portion of the gradient shows. We use the same conic gradient for the mask to determine the progress arc; this will cut off the background.
    * `transform: rotate`: This rotates the gradient based on the `--progress` custom property, effectively setting the progress visually.  3.6deg is 1% of 360 degrees.
* **Custom Property `--progress`:** This CSS custom property allows easy adjustment of the progress percentage.

**Links to Resources to Learn More:**

* **MDN Web Docs on `conic-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks on gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/)
* **Understanding CSS Custom Properties (Variables):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

