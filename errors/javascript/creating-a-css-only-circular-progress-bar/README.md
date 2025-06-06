# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This utilizes a combination of CSS `clip-path`, `transform`, and `animation` to achieve the effect. We'll focus on a simple, visually appealing design, but the principles can be easily adapted for more complex variations.


## Description of the Styling

This technique creates a circular progress bar by using a circle as a base and then "clipping" a portion of it away to reveal a background color, creating the progress effect.  The `clip-path` property is crucial here.  We'll use an animation to dynamically control the visible portion of the circle, simulating progress. The animation rotates the circle's clipping path, revealing more or less of the underlying color.


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
  background-color: #f0f0f0; /* Background color of the entire ring */
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
  background-color: #4CAF50; /* Progress color */
  clip-path: circle(50% at 50% 50%); /* Initial clip path */
  animation: progress 3s linear forwards; /* Animation for progress */
}

@keyframes progress {
  0% {
    clip-path: circle(0% at 50% 50%);
  }
  100% {
    clip-path: circle(50% at 50% 50%);
  }
}

</style>
</head>
<body>

<h1>CSS Circular Progress Bar</h1>
<div class="progress-ring"></div>

</body>
</html>
```

To adjust the percentage of progress, modify the `circle()` value in the `@keyframes progress` rule.  For example, changing `100%` to `circle(75% at 50% 50%)` in the final frame of the animation would only show 75% progress.  You can also adjust the animation duration (`3s`) to control the speed.

## Explanation

* **`progress-ring`:** This is the container for our circular progress bar.  It sets the size, border radius, and background color.
* **`::before` pseudo-element:** This creates the circular progress indicator on top of the background.  It's positioned absolutely within the parent and uses `translate` for centering.
* **`clip-path: circle()`:** This is the key to creating the circular effect.  It defines a circular clipping region.  The percentages specify the circle's radius and its center point.
* **`animation: progress 3s linear forwards;`:** This applies the `progress` animation, making the circle appear to fill up over 3 seconds.  `linear` ensures a constant speed, and `forwards` keeps the final state after the animation completes.
* **`@keyframes progress`:** This defines the animation itself.  It starts with a circle of 0% radius (invisible) and animates to a circle with a 50% radius (half-filled).  Modify the `100%` value to control the final progress level.



## Resources to Learn More

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs on `animation`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS Tricks (general CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

