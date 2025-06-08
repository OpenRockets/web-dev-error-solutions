# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This technique leverages CSS gradients and the `clip-path` property for a smooth and visually appealing effect.  We'll be using standard CSS3 properties, no frameworks like Tailwind are necessary for this example.

**Description of the Styling:**

The circular progress bar is created using a single `div` element.  We style this `div` to be a circle using `border-radius: 50%`.  A `linear-gradient` is used to create a colored arc representing the progress. The `clip-path` property, combined with a rotated `conic-gradient`, masks the gradient to reveal only the desired portion of the circle, simulating the progress.  We use variables for easy customization of the progress percentage and colors.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
:root {
  --progress: 75; /* Adjust progress percentage here (0-100) */
  --primary-color: #4CAF50; /* Primary color of the progress bar */
  --secondary-color: #eee; /* Background color of the circle */
}

.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: var(--secondary-color);
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background: conic-gradient(
    var(--primary-color) calc(var(--progress) * 1%),
    #eee 0
  );
  clip-path: polygon(
    50% 50%,
    100% 50%,
    calc(100% - var(--progress) * 0.01 * 100%) 50%,
    50% 0
  );
  transform: rotate(-90deg);
}

.progress-ring::after {
    content: var(--progress) "%";
    position: absolute;
    font-size: 1.2rem;
    color: var(--primary-color);
}
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

* **`--progress` variable:** Controls the percentage of the circle filled.  Change this value to adjust the progress.
* **`conic-gradient`:** Creates a gradient that sweeps around the circle.  The first color (`var(--primary-color)`) fills the percentage specified by `--progress`.
* **`clip-path`:**  This is crucial. It creates a polygon that cuts off part of the circular gradient, revealing only the portion representing the progress.  The polygon's vertices are dynamically calculated based on the `--progress` variable.
* **`transform: rotate(-90deg)`:** Rotates the gradient so that 0% progress starts at the top, creating a more conventional circular progress bar look.

**Links to Resources to Learn More:**

* **MDN Web Docs - `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs - `conic-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS-Tricks (various articles on CSS gradients and shapes):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

