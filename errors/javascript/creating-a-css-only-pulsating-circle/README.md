# 🐞 Creating a CSS-only Pulsating Circle


This document details how to create a pulsating circle effect using only CSS.  No JavaScript is required! This effect is achieved using CSS animations and keyframes.  We'll explore the code and the underlying principles.


**Description of the Styling:**

The styling creates a circle that smoothly expands and contracts, giving the appearance of a pulse. This is done using an animation that changes the `transform: scale()` property over a specified duration.  We'll also use some basic styling to control the color and initial size of the circle.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Pulsating Circle</title>
<style>
.pulsating-circle {
  width: 100px;
  height: 100px;
  background-color: #007bff; /* Blue color */
  border-radius: 50%;
  animation: pulse 1s infinite ease-in-out; /* Animation properties */
}

@keyframes pulse {
  0% {
    transform: scale(0.95);
  }
  50% {
    transform: scale(1);
  }
  100% {
    transform: scale(0.95);
  }
}
</style>
</head>
<body>

<div class="pulsating-circle"></div>

</body>
</html>
```


**Explanation:**

* **`.pulsating-circle`:** This class styles the div element that will be our circle.  We set the width, height, background color, and border-radius to create the circle shape.
* **`animation: pulse 1s infinite ease-in-out;`:** This line applies the animation named `pulse`.  `1s` sets the animation duration to 1 second, `infinite` makes it loop continuously, and `ease-in-out` provides a smooth acceleration and deceleration effect.
* **`@keyframes pulse { ... }`:** This defines the keyframes for the animation. Keyframes specify the style of the element at different points in the animation.
    * `0%` and `100%`:  The circle is scaled down slightly (`scale(0.95)`).
    * `50%`: The circle is at its full size (`scale(1)`).  This creates the expansion and contraction effect.

**Resources to Learn More:**

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **Keyframes:**  [MDN Web Docs - @keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

