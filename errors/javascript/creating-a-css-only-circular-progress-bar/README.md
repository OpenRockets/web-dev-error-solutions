# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript required! This technique leverages CSS's `conic-gradient` function for a clean and efficient solution.  This example uses plain CSS, but could easily be adapted to a framework like Tailwind CSS by replacing the inline styles with Tailwind classes.


**Description of the Styling:**

The circular progress bar is created using a single `<div>` element.  The `conic-gradient` function generates the circular gradient, with the color changing based on the percentage complete.  The `mask` property is used to create a circular clipping mask, revealing only a portion of the gradient based on the progress.  Border and other styling elements add visual polish.


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
  border: 10px solid #f0f0f0; /* Light grey border */
  box-sizing: border-box; /* Include border in size calculation */
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
  background: conic-gradient(#4CAF50 75%, #f0f0f0 75%); /* 75% progress */
  mask: radial-gradient(farthest-side, #000 95%, transparent 100%);
  mask-type:luminance;
}

.progress-ring.progress-80::before {
  background: conic-gradient(#4CAF50 80%, #f0f0f0 80%); /* 80% progress */
}

.progress-ring.progress-50::before {
  background: conic-gradient(#4CAF50 50%, #f0f0f0 50%); /* 50% progress */
}

.progress-ring.progress-25::before {
  background: conic-gradient(#4CAF50 25%, #f0f0f0 25%); /* 25% progress */
}
</style>
</head>
<body>

<h1>CSS Circular Progress Bars</h1>

<div class="progress-ring progress-75"></div>
<div class="progress-ring progress-80"></div>
<div class="progress-ring progress-50"></div>
<div class="progress-ring progress-25"></div>

</body>
</html>
```


**Explanation:**

* **`conic-gradient()`:** This function creates a circular gradient. The first color (`#4CAF50` - green in this case) represents the filled portion, and the second (`#f0f0f0` - light grey) represents the empty portion.  The percentage value determines the size of the filled section.

* **`mask: radial-gradient(...)`:** This creates a circular mask that hides the parts of the gradient outside the circle. The `farthest-side` keyword makes sure the circle fills the entire `div`.

* **`mask-type: luminance;`:** This ensures that the mask works correctly with the gradient.

* **Classes for different progress levels:**  The `.progress-75`, `.progress-80`, `.progress-50`, `.progress-25` classes demonstrate how easily you can adjust the progress percentage by changing the conic-gradient values.


**Links to Resources to Learn More:**

* **MDN Web Docs - `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient()](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient())
* **MDN Web Docs - `mask` property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/mask](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)
* **CSS-Tricks (general CSS tutorials):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

