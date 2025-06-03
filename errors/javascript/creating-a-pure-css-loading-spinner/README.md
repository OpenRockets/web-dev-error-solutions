# 🐞 Creating a Pure CSS Loading Spinner


This document details the creation of a loading spinner using only CSS.  No JavaScript is required.  This example uses CSS3 animations and transforms to achieve the effect.

**Description of the Styling:**

The spinner is a square containing four circular elements. These elements rotate around their center point using CSS animations.  The key is utilizing the `@keyframes` rule to define the animation, and `animation` property to apply it to the elements.  We use `transform: rotate()` to control the rotation, and `animation-timing-function` for a smooth rotation.  We'll use border-radius to make them into circles.  The position absolute positioning allows for independent rotation of the elements within the parent container.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Loading Spinner</title>
<style>
.loader {
  width: 80px;
  height: 80px;
  position: relative;
}
.loader div {
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #007bff; /* Adjust color as needed */
  animation: loader 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
}
.loader div:nth-child(1) {
  top: 0;
  left: 0;
  animation-delay: -0.4s;
}
.loader div:nth-child(2) {
  top: 0;
  right: 0;
  animation-delay: -0.3s;
}
.loader div:nth-child(3) {
  bottom: 0;
  right: 0;
  animation-delay: -0.2s;
}
.loader div:nth-child(4) {
  bottom: 0;
  left: 0;
  animation-delay: -0.1s;
}
@keyframes loader {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  100% {
    transform: scale(0);
    opacity: 0;
  }
}
</style>
</head>
<body>

<div class="loader">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

</body>
</html>
```

**Explanation:**

* **`.loader`:** This class sets the size and relative positioning for the spinner container.
* **`.loader div`:** Styles the individual circular elements.  `position: absolute` allows each circle to be positioned independently within the container.
* **`:nth-child` selectors:**  These select each of the four circles individually, allowing for staggered animation delays.
* **`@keyframes loader`:** This defines the animation. The circles scale down and fade out over the animation duration.
* **`animation` property:** This applies the animation to the div elements, setting the duration, timing function and iteration count (`infinite`).
* **`animation-delay`:** This creates the staggered effect of the rotation.

**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **MDN Web Docs on `transform` property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks on Animations:** [https://css-tricks.com/almanac/properties/a/animation/](https://css-tricks.com/almanac/properties/a/animation/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

