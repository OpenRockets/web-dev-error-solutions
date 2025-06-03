# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required! This uses a combination of CSS `radial-gradient`, `mask-image`, and `transform` to achieve a smooth, animated effect.

**Description of the Styling:**

This technique leverages a `radial-gradient` to create a circle. A `mask-image` is then applied, using a similar `radial-gradient` but with a smaller size, to create the "progress" portion.  By animating the `transform: rotate()` property of the mask, we achieve the circular progress animation.

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
  background: conic-gradient(
    #e74c3c 0%,
    #e74c3c 70%,
    #f1f1f1 70%,
    #f1f1f1 100%
  );
  mask: radial-gradient(circle 50% at 50% 50%, rgba(0,0,0,1) 70%, rgba(0,0,0,0) 70.5%);
  mask-type:luminance;
  animation: progress 2s linear infinite;
}

@keyframes progress {
  to {
    transform: rotate(360deg);
  }
}
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

* **`conic-gradient`:** This creates the base circular background.  `#e74c3c` is the color of the progress and `#f1f1f1` is the background color. The percentages define the proportion of each color.
* **`mask: radial-gradient(...)`:** This creates a circular mask that reveals only a portion of the underlying `conic-gradient`. The `rgba(0,0,0,1)` creates the opaque portion (covering the progress), and `rgba(0,0,0,0)` creates the transparent portion (revealing the background). The `70%` value controls the progress level (70% complete in this example).  `mask-type: luminance` ensures the mask works correctly.
* **`animation: progress 2s linear infinite;`:** This applies a CSS animation named "progress" which rotates the mask over 2 seconds continuously.  Adjust the `2s` value to control the animation speed.


**Links to Resources to Learn More:**

* **MDN Web Docs - `conic-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **MDN Web Docs - `mask-image`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image](https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image)
* **CSS-Tricks - Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

