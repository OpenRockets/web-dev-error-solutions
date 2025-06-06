# 🐞 Creating a Pure CSS Loading Spinner


This document details how to create a visually appealing loading spinner using only CSS.  No JavaScript is required! This technique leverages CSS animations and keyframes to achieve a smooth, rotating effect.  We'll be using standard CSS3, no frameworks like Tailwind are needed for this particular effect.


**Description of the Styling:**

The spinner is composed of eight equally spaced divs, each representing a segment of the circle.  We use the `::before` and `::after` pseudo-elements to create the visual effect of a rotating circle, leveraging transforms and animations for the smooth loading animation. The styling focuses on creating a clean, minimalist design with subtle color variations.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Loading Spinner</title>
<style>
.spinner {
  width: 80px;
  height: 80px;
  position: relative;
  animation: rotate 2s linear infinite;
}

.spinner div {
  position: absolute;
  width: 10px;
  height: 10px;
  background-color: #3498db;
  border-radius: 50%;
  animation: bounce 1s ease-in-out infinite;
}

.spinner div:nth-child(1) {
  top: 0;
  left: 35px;
  animation-delay: 0s;
}

.spinner div:nth-child(2) {
  top: 15px;
  left: 65px;
  animation-delay: 0.1s;
}

.spinner div:nth-child(3) {
  top: 45px;
  left: 65px;
  animation-delay: 0.2s;
}

.spinner div:nth-child(4) {
  top: 75px;
  left: 35px;
  animation-delay: 0.3s;
}

.spinner div:nth-child(5) {
  top: 75px;
  left: 5px;
  animation-delay: 0.4s;
}

.spinner div:nth-child(6) {
  top: 45px;
  left: 5px;
  animation-delay: 0.5s;
}

.spinner div:nth-child(7) {
  top: 15px;
  left: 5px;
  animation-delay: 0.6s;
}

.spinner div:nth-child(8) {
  top: 15px;
  left: 35px;
  animation-delay: 0.7s;
}


@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes bounce {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
}
</style>
</head>
<body>

<div class="spinner">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>

</body>
</html>
```

**Explanation:**

*   The `spinner` div acts as a container, setting the size and initiating the rotation animation.
*   Each individual `div` within the `spinner` represents a segment of the loading circle. Their positions are manually set using `top` and `left`.
*   `animation-delay` creates a staggered effect, making the animation more visually appealing.
*   `@keyframes rotate` defines the animation that rotates the entire spinner.
*   `@keyframes bounce` creates a subtle pulsing effect for each segment.


**Links to Resources to Learn More:**

*   **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
*   **CSS Keyframes:** [MDN Web Docs - @keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
*   **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

