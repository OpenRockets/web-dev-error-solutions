# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required!  This technique leverages the `clip-path` property for precise control over the shape and `animation` for the progress effect.

**Description of the Styling:**

The styling relies on a circular shape created with `border-radius: 50%;`.  A pseudo-element (`::before`) is used to create the visible progress bar segment.  The `clip-path` property, combined with a rotating animation, cuts away a portion of the circle, revealing only the percentage completed.  The percentage is controlled by a CSS custom property (`--progress`).

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.circular-progress {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #f0f0f0;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.circular-progress::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #4CAF50;
  clip-path: polygon(50% 50%, 50% 0%, 100% 0%, 100% 50%, 75% 50%); /* Initial clip-path */
  animation: progress 2s linear forwards; /* Adjust duration as needed */
}

@keyframes progress {
  to {
    clip-path: polygon(50% 50%, 50% 0%, 100% 0%, 100% 50%, calc(50% + var(--progress) * 50%) 50%);
  }
}

.circular-progress-container {
  --progress: 0.75; /* Adjust this value (0-1) to control progress */
}
</style>
</head>
<body>

<div class="circular-progress-container">
  <div class="circular-progress"></div>
</div>

</body>
</html>
```

**Explanation:**

1. **`circular-progress`:** This class styles the main container, creating the basic circle.
2. **`circular-progress::before`:** This pseudo-element creates the progress bar segment. The initial `clip-path` creates a small segment.
3. **`@keyframes progress`:** This defines the animation.  The `clip-path` is dynamically updated using `calc()` and the `--progress` custom property.  `var(--progress)` represents the percentage (0 to 1).  The calculation expands the visible portion of the circle accordingly.
4. **`--progress`:** This custom property in `circular-progress-container` controls the percentage of the progress bar. Change its value to alter the progress visually.

**Links to Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs on `animation`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks on `clip-path`:** [https://css-tricks.com/clipping-masking-css/](https://css-tricks.com/clipping-masking-css/) (search for clip-path examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

