# 🐞 CSS Challenge:  The Pulsating Heart


This challenge focuses on creating a simple, pulsating heart using only CSS.  We'll leverage CSS animations to achieve the effect. No JavaScript required!

**Description of the Styling:**

The goal is to design a heart shape that smoothly changes its size over time, creating a pulsating animation. We'll achieve this using a pseudo-element (`::before` and `::after`) to create the heart shape and then apply a CSS animation to control the size changes. The animation will involve a smooth scaling up and down of the heart. We’ll use a simple red color for the heart.


**Full Code (CSS Only):**

```css
.heart {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid red;
  position: relative;
  animation: pulse 1s infinite ease-in-out;
}

.heart::before {
  content: "";
  position: absolute;
  left: -25px;
  top: -50px;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid red;
  transform: rotate(180deg); /* Mirror for other half of heart */
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
```

**HTML (to use the CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Pulsating Heart</title>
<style>
/* Insert the CSS code here */
</style>
</head>
<body>
  <div class="heart"></div>
</body>
</html>
```

**Explanation:**

* **`.heart`:** This class creates the basic heart shape using borders. The `border-left` and `border-right` create the sides, while `border-bottom` forms the bottom curve.
* **`.heart::before`:** This pseudo-element creates the mirrored top half of the heart, completing the shape.  `transform: rotate(180deg);` flips the bottom half to create the upper half.
* **`@keyframes pulse`:** This defines the animation, smoothly scaling the heart between 100% and 110% of its original size. `infinite` makes the animation loop continuously, and `ease-in-out` provides a smooth transition.

**Resources to Learn More:**

* **CSS Animations:**  [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

