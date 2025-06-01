# 🐞 Creating a CSS-only Animated Loading Spinner


This document details the creation of a simple, yet visually appealing loading spinner using only CSS. No JavaScript is required!  This utilizes CSS animations and keyframes to achieve the effect.

**Description of the Styling:**

The spinner is a circle composed of four smaller circles arranged around its center.  The animation rotates these smaller circles continuously, creating the illusion of loading. We use CSS variables (custom properties) for easy customization of colors and size.


**Full Code:**

```css
/* CSS Variables for customization */
:root {
  --spinner-size: 100px;
  --spinner-color: #007bff; /* Blue */
}

.loader {
  width: var(--spinner-size);
  height: var(--spinner-size);
  position: relative;
  animation: rotate 2s linear infinite;
}

.loader div {
  position: absolute;
  width: 20%;
  height: 20%;
  background-color: var(--spinner-color);
  border-radius: 50%;
  animation: bounce 1s ease-in-out infinite;
}

.loader div:nth-child(1) {
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  animation-delay: 0s;
}

.loader div:nth-child(2) {
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  animation-delay: 0.25s;
}

.loader div:nth-child(3) {
  top: 50%;
  right: 0;
  transform: translateY(-50%);
  animation-delay: 0.5s;
}

.loader div:nth-child(4) {
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  animation-delay: 0.75s;
}

/* Animations */
@keyframes rotate {
  100% {
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
```

**Explanation:**

* **`--spinner-size` and `--spinner-color`:** These CSS variables allow for easy customization of the spinner's size and color.  Simply change the values in the `:root` selector.
* **`.loader`:** This class styles the overall container, setting its size and initiating the rotation animation.
* **`.loader div`:** This styles each of the four smaller circles within the spinner.  The `:nth-child` selector is used to apply unique animation delays to each circle, creating the staggered effect.
* **`@keyframes rotate`:** This keyframes animation rotates the entire spinner.
* **`@keyframes bounce`:** This keyframes animation creates a subtle pulsating effect for each individual circle.


**Links to Resources to Learn More:**

* **CSS Animations:**  [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Keyframes:** [MDN Web Docs - @keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
* **CSS Variables:** [MDN Web Docs - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

