# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This technique leverages CSS's `conic-gradient` function and transforms to achieve a visually appealing and responsive progress indicator.


**Description of the Styling:**

This circular progress bar uses a combination of techniques to create the visual effect:

* **`conic-gradient`:** This CSS function is central to creating the circular progress. It allows us to define a gradient that sweeps around a circle.  We use this to create the colored progress segment.
* **`transform: rotate()`:** We dynamically rotate the gradient based on the percentage of progress.  This makes the colored portion of the circle grow proportionally.
* **`mask`:**  A circular mask is used to clip the gradient into a perfect circle, preventing it from overflowing.


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

.progress-ring__circle {
  width: 130px;
  height: 130px;
  border-radius: 50%;
  background: conic-gradient(
    #4CAF50 0deg, /* Green */
    #4CAF50 var(--progress, 0deg), /* Variable progress percentage */
    #f0f0f0 var(--progress, 0deg)
  );
  mask: url(#mask);
  mask-size: 100%;
}

.progress-ring__text {
    position: absolute;
    font-size: 14px;
}

</style>
</head>
<body>

<svg width="0" height="0" style="display:none;">
    <defs>
        <mask id="mask">
            <circle cx="50%" cy="50%" r="50%" fill="white"/>
        </mask>
    </defs>
</svg>

<div class="progress-ring">
  <div class="progress-ring__circle" style="--progress: 75deg;"></div>
    <span class="progress-ring__text">75%</span>
</div>

</body>
</html>
```

**Explanation:**

1.  **HTML Structure:**  The HTML sets up a simple `div` with class `progress-ring` to contain the progress bar. Inside, another `div` with class `progress-ring__circle` represents the circular progress itself. We also added a `svg` to define our mask to clip the circle, and a `span` to display the percentage.

2.  **CSS Styling:**
    *   The `.progress-ring` styles the outer container, giving it a circular shape and a light gray background.
    *   The `.progress-ring__circle` is where the magic happens.  `conic-gradient` creates the circular gradient. `var(--progress)` is a CSS custom property that allows you to dynamically control the progress percentage by setting it in the `style` attribute.  The mask creates the clean circular cut.
    *   The `mask` element using an `svg` defines a circle that masks our conic gradient.

3. **Dynamic Progress:**  The `style="--progress: 75deg;"` attribute in the `.progress-ring__circle` dynamically sets the progress.  To change the percentage, simply adjust the degrees (360 degrees is 100%).  To make it data-driven, you'd replace this `style` attribute with a dynamic value from your data source.


**Links to Resources to Learn More:**

* **MDN Web Docs - `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **MDN Web Docs - `mask`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/mask](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)
* **CSS Tricks (various articles on gradients and masking):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

