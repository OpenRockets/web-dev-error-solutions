# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This utilizes a combination of CSS `clip-path`, `transform`, and animations to achieve the effect.  We'll be using standard CSS, not a framework like Tailwind.

**Description of the Styling:**

The progress bar is created using a single circular element.  We use a `clip-path` to create the circular shape and a background color.  An inner element with a different color is then rotated using a CSS animation to represent the progress.  The percentage is displayed using a pseudo-element (`::before`).

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
  content: "75%"; /* Percentage to display. Update this as needed. */
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 18px;
  font-weight: bold;
}

.progress-ring .progress-bar {
  position: absolute;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  clip-path: circle(50% at 50% 50%); /* Creates the circle */
  background-color: #4CAF50; /* Green progress bar */
  animation: progress-animation 2s linear forwards; /* Animation */
}

@keyframes progress-animation {
  to {
    transform: rotate(270deg); /* Rotate 270 degrees for 75% progress (Adjust for different percentages) */
  }
}
</style>
</head>
<body>

<div class="progress-ring">
  <div class="progress-bar"></div>
</div>

</body>
</html>
```

**Explanation:**

1. **`progress-ring`:** This is the main container, setting the size and background color of the entire progress bar.
2. **`::before`:** This pseudo-element creates the percentage text in the center.
3. **`progress-bar`:** This is the inner element that represents the progress.  The `clip-path` makes it circular.
4. **`progress-animation`:** This keyframes animation rotates the `progress-bar` element.  The `270deg` rotation is calculated as 75% of 360 degrees (full circle).  Adjust this value to change the percentage shown.  `linear` ensures a constant speed. `forwards` keeps the animation at its final state.

**To change the percentage:**

- Modify the content of `progress-ring::before` to update the percentage displayed.
- Adjust the `transform: rotate(...)` value in the `progress-animation` keyframes.  The formula is: `(percentage / 100) * 360` degrees.  For example, for 50% progress, you'd use `180deg`.


**Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **Understanding CSS Transforms:** Numerous tutorials available on sites like freeCodeCamp, Codecademy, etc., by searching "CSS transforms".


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

