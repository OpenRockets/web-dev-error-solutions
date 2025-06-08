# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This example utilizes CSS3 properties for its functionality.

**Description of the Styling:**

This technique leverages the `clip-path` property to create a circular mask that reveals a portion of a larger circle.  By manipulating the `clip-path`'s `circle()` function with a dynamically calculated radius, we simulate the progress bar's movement.  The background circle provides the track, while a foreground circle, masked by the `clip-path`, represents the progress.  The percentage is visually displayed using a pseudo-element.


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
  position: relative;
}

.progress-ring__circle {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #ddd; /* Track color */
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring__circle::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #4CAF50; /* Progress color */
  clip-path: circle(50% at 50% 50%); /* Initial clip-path */
  transform: rotate(-90deg); /* Start at top */
  transition: clip-path 0.5s ease; /* Smooth animation */
}

.progress-ring--progress-75 .progress-ring__circle::before {
  clip-path: circle(75% at 50% 50%);
}

.progress-ring__percentage {
  position: absolute;
  font-size: 2em;
  color: white;
}
</style>
</head>
<body>

<div class="progress-ring progress-ring--progress-75">
  <div class="progress-ring__circle">
    <div class="progress-ring__percentage">75%</div>
  </div>
</div>


</body>
</html>
```

**Explanation:**

* **`progress-ring`**: This class sets the overall size and shape.
* **`progress-ring__circle`**: This creates the background circle (track).  The `::before` pseudo-element creates the foreground circle (progress).
* **`clip-path: circle(50% at 50% 50%);`**: This creates the circular mask. The percentage controls the radius, effectively determining how much of the circle is visible.  The `at` coordinates specify the center.
* **`transform: rotate(-90deg);`**: This rotates the circle to start at the top.
* **`.progress-ring--progress-75`**: This class demonstrates how to dynamically change the progress by adjusting the `clip-path` radius.  You would replace this with JavaScript or server-side code to dynamically adjust the percentage.


**Links to Resources to Learn More:**

* **MDN Web Docs - `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS-Tricks - `clip-path` examples:** [https://css-tricks.com/clipping-masking-css/](https://css-tricks.com/clipping-masking-css/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

