# 🐞 Creating a Pure CSS3 Animated Loading Spinner


This document details the creation of a simple, yet visually appealing loading spinner using only CSS3. No JavaScript is required. This effect leverages CSS animations and keyframes to create a smooth, rotating effect.


**Description of the Styling:**

The spinner is a square containing four circles, each with a slightly different rotation offset.  The `@keyframes` animation rotates the circles continuously.  We use `border-radius` to create the circular shapes and `box-shadow` to add depth and a subtle glow.  The styling focuses on creating a clean, minimalist design that’s easy to customize.

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
  margin: 50px auto;
}
.loader div {
  position: absolute;
  width: 16px;
  height: 16px;
  background: #007bff;
  border-radius: 50%;
  animation: animate 1s linear infinite;
}
.loader div:nth-child(1) {
  top: 0;
  left: 0;
  animation-delay: 0s;
}
.loader div:nth-child(2) {
  top: 0;
  right: 0;
  animation-delay: 0.25s;
}
.loader div:nth-child(3) {
  bottom: 0;
  right: 0;
  animation-delay: 0.5s;
}
.loader div:nth-child(4) {
  bottom: 0;
  left: 0;
  animation-delay: 0.75s;
}
@keyframes animate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
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

* **`.loader`:** This class sets the overall dimensions and positioning of the spinner.
* **`.loader div`:** This styles each individual circle, setting its size, background color, and shape.
* **`:nth-child`:** This pseudo-class allows us to individually style each of the four circles, giving them different animation delays to create the rotating effect.
* **`@keyframes animate`:** This defines the animation, smoothly rotating the circles by 360 degrees over one second.
* **`animation-delay`:**  This property in each `div` creates the staggered rotation.


**Links to Resources to Learn More:**

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS Keyframes:** [MDN Web Docs - CSS Keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

