# 🐞 Creating a Pure CSS Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This example utilizes CSS3 properties for its functionality.

**Description of the Styling:**

This technique leverages the `clip-path` property to create a circular mask that reveals a portion of an underlying circle.  By manipulating the `rotate` transform and the `clip-path`'s arc, we control the visible portion of the circle, simulating progress.  We'll also use some basic styling for aesthetics.

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
  background-color: #4CAF50; /* Green progress color */
  clip-path: circle(50% at 50% 50%); /*initial clip-path */
  animation: progress-animation 3s linear forwards;
}

@keyframes progress-animation {
  0% {
    clip-path: circle(0% at 50% 50%);
  }
  100% {
    clip-path: circle(50% at 50% 50%);  /* adjust 50% to change progress percentage */
    clip-path: circle(75% at 50% 50%); /* 75% progress */
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

**Explanation:**

1. **`progress-ring`:** This is the container for the progress bar. It's a square div given a circular shape using `border-radius`.

2. **`progress-ring::before`:** This pseudo-element creates the circular progress indicator.  It's positioned absolutely within the container and uses `transform: translate(-50%, -50%)` to center itself.

3. **`clip-path: circle(50% at 50% 50%);`:** This is the core of the effect.  `circle()` creates a circular clipping region. The first value (50%) defines the radius (50% of the element's width/height), and the `at` keyword specifies the center of the circle.  The animation changes this radius.

4. **`animation: progress-animation 3s linear forwards;`:** This applies a CSS animation named `progress-animation` that takes 3 seconds, uses linear timing, and runs once (`forwards` keeps the final state).

5. **`@keyframes progress-animation`:** This defines the animation.  The `clip-path`'s radius changes from 0% to 75% (adjust this value to change the progress percentage) over the 3-second duration.


**Links to Resources to Learn More:**

* **MDN Web Docs - `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS-Tricks - `clip-path` examples:** [https://css-tricks.com/almanac/properties/c/clip-path/](https://css-tricks.com/almanac/properties/c/clip-path/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

