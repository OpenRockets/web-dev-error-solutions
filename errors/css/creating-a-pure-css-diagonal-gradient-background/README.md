# 🐞 Creating a Pure CSS Diagonal Gradient Background


This document details how to create a diagonal gradient background using only CSS.  This technique avoids the use of images and offers flexibility in customizing the gradient colors and angle. We'll use pure CSS3, no frameworks like Tailwind involved.


**Description of the Styling:**

This CSS creates a diagonal linear gradient spanning the entire width and height of an element. The `linear-gradient()` function is used to define the gradient, specifying the direction (in this case, `to bottom right`) and the colors involved.  We'll use two colors for simplicity, but you can add more for a more complex gradient. The background is applied to a `div` element for demonstration purposes. You can adapt it to any element.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Diagonal Gradient</title>
<style>
body {
  margin: 0; /* Remove default body margins */
}

.diagonal-gradient {
  width: 100vw;
  height: 100vh; /* Make it full viewport */
  background: linear-gradient(to bottom right, #f06d06, #ffb74d); /* Customize colors here */
}
</style>
</head>
<body>
<div class="diagonal-gradient"></div>
</body>
</html>
```


**Explanation:**

* **`body { margin: 0; }`**: This removes default body margins to ensure the background covers the entire viewport.
* **`.diagonal-gradient { width: 100vw; height: 100vh; }`**: This sets the width and height of the div to 100% of the viewport width and height, respectively, using `vw` (viewport width) and `vh` (viewport height) units. This makes sure the gradient fills the entire screen.
* **`background: linear-gradient(to bottom right, #f06d06, #ffb74d);`**: This is the core of the effect.  `linear-gradient()` creates a linear gradient.  `to bottom right` specifies the direction of the gradient. You can change this to `to top right`, `to bottom left`, `to top left`, or specify an angle in degrees (e.g., `45deg`).  `#f06d06` and `#ffb74d` are hexadecimal color codes; you can replace these with any colors you prefer.  More colors can be added, separated by commas.


**Links to Resources to Learn More:**

* **MDN Web Docs - `linear-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)  (Comprehensive documentation on CSS gradients)
* **CSS-Tricks - Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/) (A good tutorial on CSS gradients with various examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

