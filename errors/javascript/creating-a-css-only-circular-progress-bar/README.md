# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This technique leverages CSS's `conic-gradient` function for a smooth and efficient solution.

**Description of the Styling:**

This progress bar uses a circle created with the `border-radius` property.  The filling of the circle is achieved with a `conic-gradient`, which allows us to create a gradient that sweeps around a circle.  The percentage of the circle filled is controlled by the `rotate` transform applied to the gradient.

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
    #4CAF50 0% 75%,
    #f0f0f0 75% 100%
  );
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: white;
}
.progress-ring.progress-75 {
  background: conic-gradient(
    #4CAF50 0% 75%,
    #f0f0f0 75% 100%
  );
}
.progress-ring.progress-50 {
  background: conic-gradient(
    #4CAF50 0% 50%,
    #f0f0f0 50% 100%
  );
}
.progress-ring.progress-25 {
  background: conic-gradient(
    #4CAF50 0% 25%,
    #f0f0f0 25% 100%
  );
}


</style>
</head>
<body>

<h1>CSS Only Circular Progress Bars</h1>

<div class="progress-ring progress-75"></div>
<div class="progress-ring progress-50"></div>
<div class="progress-ring progress-25"></div>

</body>
</html>
```

**Explanation:**

* **`conic-gradient()`:** This CSS function creates a conic gradient, perfect for circular shapes. The syntax `color1 percentage1, color2 percentage2` defines the colors and their respective stopping points.  In this example, `#4CAF50` (green) fills up to the specified percentage, and `#f0f0f0` (light gray) fills the rest.

* **`::before` pseudo-element:** This creates a white inner circle to make the progress bar visually appealing.

* **Classes `progress-75`, `progress-50`, `progress-25`:** These classes demonstrate how to easily change the progress by adjusting the percentage in the `conic-gradient`.  You can dynamically adjust this class to change the progress bar's value.

**Resources to Learn More:**

* [MDN Web Docs - conic-gradient()](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* [CSS-Tricks - conic-gradient()](https://css-tricks.com/conic-gradient/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

