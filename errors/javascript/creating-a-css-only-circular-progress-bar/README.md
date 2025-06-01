# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  This avoids the need for JavaScript, keeping the code lightweight and efficient. We'll leverage CSS variables and the `conic-gradient` function for a clean and modern look.

## Description of the Styling

The circular progress bar is created using a single `<div>` element.  The styling uses a `conic-gradient` to create the circular progress.  The percentage of the circle filled is controlled by a CSS variable, allowing for easy dynamic updates (though we'll demonstrate a static example here).  A subtle shadow adds depth.

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
  background: conic-gradient(
    #f0f0f0 0deg,
    #f0f0f0 calc(var(--progress) * 1%),
    #4CAF50 calc(var(--progress) * 1%),
    #4CAF50 360deg
  );
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

## Explanation

* **`--progress` variable:** This CSS variable holds the percentage of the circle to be filled.  Change this value to adjust the progress.
* **`conic-gradient`:** This function creates a gradient that radiates from the center.  The values define the colors and their starting/ending angles.  We use `calc(var(--progress) * 1%)` to calculate the angle based on the `--progress` variable.
* **`box-shadow`:** This adds a subtle shadow to give the progress bar more depth and visual appeal.

## Links to Resources to Learn More

* **MDN Web Docs on `conic-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks on Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/)  (While not specifically about `conic-gradient`, this provides a broad understanding of CSS gradients)
* **Understanding CSS Variables (Custom Properties):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

