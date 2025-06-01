# 🐞 Creating a CSS-Only Pulsating Heart


This document details the creation of a pulsating heart animation using only CSS. No JavaScript is required.  This example utilizes standard CSS3 animations, making it widely compatible.


**Description of the Styling:**

This effect leverages the `animation` property in CSS to create a smooth, pulsating animation. We achieve the heart shape using a pseudo-element (`::before` and `::after`) and carefully positioned borders.  The animation subtly changes the scale and opacity of the heart, giving the impression of a heartbeat.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Pulsating Heart</title>
<style>
.heart {
  width: 100px;
  height: 100px;
  position: relative;
  margin: 50px auto;
}

.heart::before,
.heart::after {
  position: absolute;
  content: "";
  left: 50%;
  top: 0;
  transform: translateX(-50%);
  background-color: red;
  border-radius: 50%;
}

.heart::before {
  width: 60px;
  height: 60px;
  transform-origin: 50% 100%;
}

.heart::after {
  width: 50px;
  height: 50px;
  top: 20px;
  transform-origin: 50% 100%;
}

.heart {
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.1);
    opacity: 0.8;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}
</style>
</head>
<body>
<div class="heart"></div>
</body>
</html>
```


**Explanation:**

1. **Heart Structure:** The heart is created using a `div` with two pseudo-elements (`::before` and `::after`). These pseudo-elements are shaped and positioned to form the heart shape using borders and transforms.

2. **Animation:** The `@keyframes pulse` rule defines the animation.  It smoothly scales the heart up and down and slightly changes its opacity, creating the pulsating effect. The `animation` property on the `.heart` class applies this animation with a duration of 1 second, and repeats infinitely (`infinite`).

3. **Transform-origin:** The `transform-origin` property is crucial for controlling the animation's pivot point. Setting it to `50% 100%` ensures the scaling happens from the bottom of each pseudo-element, contributing to the natural pulsating look.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - Pseudo-elements:** [https://css-tricks.com/pseudo-elements/](https://css-tricks.com/pseudo-elements/)
* **Understanding `transform-origin`:** [Search for "CSS transform-origin" on your preferred search engine.]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

