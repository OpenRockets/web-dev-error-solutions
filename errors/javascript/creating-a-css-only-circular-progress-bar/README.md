# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  This avoids the need for JavaScript, making it lightweight and efficient.  We'll leverage CSS's `conic-gradient` function for a clean and simple solution.


## Description of the Styling

The circular progress bar is achieved using a combination of techniques:

* **`conic-gradient`:** This CSS function creates a gradient that sweeps around a circle. We use this to create the visual progress bar itself. The start and end angles define the filled portion of the circle.
* **`clip-path`:**  We use `clip-path: circle()` to create a circular shape for the progress bar.
* **Pseudo-elements:**  Pseudo-elements (`::before` and `::after`) are used to create the circle background and the progress indicator.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  --progress: 75; /* Adjust this value to change the progress */
  width: 150px;
  height: 150px;
  border-radius: 50%;
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  background: conic-gradient(
    #e6e6e6,
    #e6e6e6 calc(var(--progress) * 1%),
    #4caf50 calc(var(--progress) * 1%),
    #4caf50
  );
  clip-path: circle(50% at 50% 50%); /*Keeps the gradient circular*/
}

.progress-ring::after {
  content: attr(data-progress) "%";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 16px;
  font-weight: bold;
}
</style>
</head>
<body>

<div class="progress-ring" data-progress="75"></div>

</body>
</html>
```


## Explanation

1. **The `progress-ring` class:** This sets up the basic dimensions, shape (circle), and relative positioning for the container.
2. **`::before` pseudo-element:** This creates the circular background and the colored progress section using `conic-gradient`. The `calc(var(--progress) * 1%)` expression dynamically calculates the filled portion of the circle based on the `--progress` custom property.  The `#e6e6e6` is a light gray for the background, and `#4caf50` is a green for the progress.
3. **`::after` pseudo-element:** This adds the percentage value as text to the center of the progress ring.


## Links to Resources to Learn More

* **MDN Web Docs on `conic-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Tricks on Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/) (a general resource on CSS gradients, including conic gradients)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

