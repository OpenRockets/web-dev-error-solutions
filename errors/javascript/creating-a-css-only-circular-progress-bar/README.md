# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This example leverages CSS gradients and transforms to achieve the effect.  We'll build a visually appealing progress bar that can easily be customized to fit different design needs.


## Description of the Styling

This circular progress bar utilizes a combination of techniques:

* **`clip-path`:**  This CSS property is used to create the circular shape by clipping a portion of the underlying element.
* **`background-image` (linear-gradient):** A linear gradient creates the visual representation of the progress bar's fill. We'll dynamically adjust the size of this gradient to control the progress percentage.
* **`transform: rotate()`:**  This rotates the clipped element, giving the impression of a filling circle.


## Full Code

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
  background-color: #f0f0f0; /* Background color of the ring */
  position: relative;
  display: inline-block;
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
  clip-path: circle(50% at 50% 50%); /* Creates the circular clip */
  background-image: linear-gradient(to right, #4CAF50 0%, #4CAF50 75%, #fff 75%); /* Dynamic fill */
  background-size: 200% 200%; /* Adjusts the fill size */
  background-position: 0% 50%; /* Starts the fill at 0 degree */
  transform-origin: 50% 50%; /* Correct rotation center */
  transform: rotate(225deg); /* Example 75% progress (270deg * 0.75) */
  background-size: 150px 150px; /* Adjust to ring size. */
}

/* Customize Percentage Text (optional) */
.progress-ring .percentage {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 2em;
  font-weight: bold;
  color: #333;
}

</style>
</head>
<body>

<div class="progress-ring">
  <span class="percentage">75%</span>
</div>

</body>
</html>
```

To change the progress percentage, adjust the `transform: rotate()` value in the `::before` pseudo-element.  A full circle is 360 degrees;  75% progress would be `rotate(270deg)` (360 * 0.75).

## Explanation

1. **The `progress-ring` div:** This acts as the container, establishing the size and shape of the progress bar.

2. **The `::before` pseudo-element:** This creates the visual progress.

    * The `clip-path` creates the circular shape.
    * The `linear-gradient` defines the progress fill color.  The gradient's size is adjusted with `background-size` to allow for a smooth animation. This part is crucial for filling. 
    * `transform: rotate()` rotates the filled segment to show progress.

3. **Customization:** The `background-image` can be easily altered to change the fill color, and the percentage text can be customized.


## Resources to Learn More

* **MDN Web Docs - `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs - `linear-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* **MDN Web Docs - `transform`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

