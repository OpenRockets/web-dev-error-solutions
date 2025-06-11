# 🐞 CSS Challenge:  3D Rotating Cube with CSS Animations


This challenge involves creating a 3D rotating cube using only CSS.  We'll leverage CSS3 transforms and animations to achieve the effect.  No JavaScript is required!  This example uses standard CSS, but could easily be adapted to use Tailwind CSS classes for styling.


**Description of the Styling:**

The cube will be composed of six square divs, each representing a face.  These divs will be positioned absolutely within a parent container.  CSS transforms (rotateX, rotateY, and translateZ) will be used to create the 3D effect and animation.  We'll apply different background colors to each face for visual distinction.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
body {
  perspective: 1000px; /* Creates the 3D perspective */
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.cube {
  width: 200px;
  height: 200px;
  transform-style: preserve-3d; /* Essential for 3D rendering */
  animation: rotate 8s linear infinite; /* Animate the rotation */
}

.cube div {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.9; /* add some slight translucency */
}

.front {
  background-color: #ff5722;
  transform: translateZ(100px);
}

.back {
  background-color: #2196f3;
  transform: translateZ(-100px) rotateY(180deg);
}

.top {
  background-color: #4CAF50;
  transform: translateY(-100px) rotateX(90deg);
}

.bottom {
  background-color: #f44336;
  transform: translateY(100px) rotateX(-90deg);
}

.left {
  background-color: #9C27B0;
  transform: translateX(-100px) rotateY(-90deg);
}

.right {
  background-color: #FFEB3B;
  transform: translateX(100px) rotateY(90deg);
}

@keyframes rotate {
  from {
    transform: rotateY(0deg);
  }
  to {
    transform: rotateY(360deg);
  }
}
</style>
</head>
<body>
<div class="cube">
  <div class="front"></div>
  <div class="back"></div>
  <div class="top"></div>
  <div class="bottom"></div>
  <div class="left"></div>
  <div class="right"></div>
</div>
</body>
</html>
```


**Explanation:**

* **`perspective`:**  This property on the `body` creates the 3D viewing perspective.  Adjust this value to change the depth effect.
* **`transform-style: preserve-3d;`:**  Crucial for the cube's 3D rendering; it ensures child elements are rendered in 3D space.
* **`translateZ()`:** Moves elements along the z-axis (depth).  Positive values move elements towards the viewer.
* **`rotateX()` and `rotateY()`:** Rotate elements around the x and y axes.
* **`@keyframes rotate`:** Defines the animation, smoothly rotating the cube around the y-axis.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

