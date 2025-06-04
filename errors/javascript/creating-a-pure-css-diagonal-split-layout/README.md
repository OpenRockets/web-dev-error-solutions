# 🐞 Creating a Pure CSS Diagonal Split Layout


This document details how to create a visually appealing diagonal split layout using only CSS.  We'll achieve this effect without relying on images or JavaScript, showcasing the power and flexibility of CSS. This example uses plain CSS; adapting it to Tailwind CSS is straightforward by replacing the inline styles with corresponding Tailwind classes.


**Description of the Styling:**

The layout consists of two divs, one positioned on top of the other.  The top div uses a linear gradient background with a diagonal line created by the `linear-gradient` function.  The bottom div is positioned absolutely to cover the remaining portion of the screen.  Using `clip-path` on the top div allows for precise control over the diagonal split, creating a clean and sharp division.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Diagonal Split Layout</title>
<style>
body {
  margin: 0;
}

.container {
  width: 100vw;
  height: 100vh;
  overflow: hidden; /* Prevents content from overflowing */
}

.top {
  position: relative;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom right, #f06d06, #f06d06); /*Orange color*/
  clip-path: polygon(0 0, 100% 0, 100% 75%, 0% 100%); /* Adjust percentage for angle */
}

.bottom {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #282c34; /* Dark background color */
}
</style>
</head>
<body>
<div class="container">
  <div class="top"></div>
  <div class="bottom"></div>
</div>
</body>
</html>
```

**Explanation:**

* **`body { margin: 0; }`**: Removes default body margins for a full-screen effect.
* **`.container`**:  Sets up a full viewport container. `overflow: hidden` is crucial to keep the elements within the container's bounds.
* **`.top`**:  This div is the top, orange section.  The `linear-gradient` creates the orange background.  The `clip-path: polygon(...)` defines the shape. The coordinates (0 0, 100% 0, 100% 75%, 0% 100%) represent the vertices of the polygon, creating the diagonal split.  You can adjust the percentage (75% in this case) to change the angle of the split.
* **`.bottom`**: This div is positioned absolutely within the container, covering the area below the diagonal cut.


**Links to Resources to Learn More:**

* **MDN Web Docs on `linear-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS-Tricks (general CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

