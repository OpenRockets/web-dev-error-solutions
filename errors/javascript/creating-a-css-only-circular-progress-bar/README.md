# 🐞 Creating a CSS-only Circular Progress Bar


This document describes how to create a circular progress bar using only CSS.  This avoids the need for JavaScript, making it a lightweight and efficient solution for simple progress indicators.  The technique utilizes the `clip-path` property to mask a circle, creating the visual effect of a filling progress bar.


**Description of the Styling:**

This method uses a single circular element, styled as a background ring.  We then use a pseudo-element (`::before`) to create a "filling" segment on top.  The `clip-path` property, combined with a `rotate` transform, dynamically controls the visible portion of the fill, simulating the progress.


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
  background-color: #f0f0f0; /* Background color of the ring */
  border: 5px solid #ccc; /* Border of the ring */
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #4CAF50; /* Color of the progress fill */
  clip-path: circle(50% at 50% 50%); /* Initial clip-path */
  transform-origin: 50% 50%; /* Center of rotation */
  transform: rotate(0deg); /* Initial rotation */
  transition: transform 0.5s ease; /* Smooth transition */
}

.progress-ring.progress-75::before {
  transform: rotate(270deg); /* Rotate to 75% progress */
}

.progress-ring.progress-50::before {
  transform: rotate(180deg); /* Rotate to 50% progress */
}

.progress-ring.progress-25::before {
  transform: rotate(90deg); /* Rotate to 25% progress */
}
</style>
</head>
<body>

<h1>CSS Circular Progress Bar</h1>

<div class="progress-ring progress-75"></div>
<div class="progress-ring progress-50"></div>
<div class="progress-ring progress-25"></div>
<div class="progress-ring"></div>


</body>
</html>
```


**Explanation:**

* The `.progress-ring` class styles the base circular element.
* The `::before` pseudo-element creates the filling segment.
* `clip-path: circle(50% at 50% 50%);` creates a circular clip-path centered on the element.
* `transform: rotate(xdeg);` rotates the fill segment.  A full circle (360deg) represents 100% progress.  We calculate the rotation angle based on the percentage.  For example, 75% progress corresponds to `(75/100) * 360 = 270deg`.
* The `transition` property ensures a smooth animation as the progress changes.
* The different `.progress-x` classes demonstrate how to control the progress. You can easily adjust the class name and rotation angle to display different progress levels.


**External References:**

* [MDN Web Docs - clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* [MDN Web Docs - transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

