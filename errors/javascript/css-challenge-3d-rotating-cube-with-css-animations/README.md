# 🐞 CSS Challenge:  3D Rotating Cube with CSS Animations


This challenge involves creating a 3D rotating cube using only CSS.  We'll leverage CSS transforms and animations to achieve the effect.  This example uses pure CSS; no JavaScript is required.


## Description of the Styling

The goal is to create a cube that appears to rotate smoothly on its vertical axis.  We'll achieve this by using six divs, each representing a face of the cube, positioned and rotated appropriately using `transform: rotateX()` and `transform: rotateY()`.  CSS animations will handle the continuous rotation. The cube will have distinct colors for each face to clearly illustrate the 3D effect.


## Full Code


```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
body {
  perspective: 800px; /* Creates the 3D perspective */
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.cube {
  width: 200px;
  height: 200px;
  transform-style: preserve-3d; /* Essential for 3D transforms */
  animation: rotate 8s linear infinite; /* Animate the rotation */
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.8; /*add some transparency*/
  background-size: cover;
  backface-visibility: hidden; /* Prevents faces from showing through */
}

.front {
  background-color: #f00;
  transform: translateZ(100px);
}

.back {
  background-color: #0f0;
  transform: translateZ(-100px) rotateY(180deg);
}

.top {
  background-color: #00f;
  transform: translateY(-100px) rotateX(90deg);
}

.bottom {
  background-color: #ff0;
  transform: translateY(100px) rotateX(-90deg);
}

.left {
  background-color: #0ff;
  transform: translateX(-100px) rotateY(-90deg);
}

.right {
  background-color: #f0f;
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
  <div class="face front"></div>
  <div class="face back"></div>
  <div class="face top"></div>
  <div class="face bottom"></div>
  <div class="face left"></div>
  <div class="face right"></div>
</div>
</body>
</html>
```


## Explanation

* **`perspective`:** This property on the `body` creates the 3D viewing space.  Adjusting this value changes the perspective.
* **`transform-style: preserve-3d;`:** This is crucial. It ensures that child elements (the faces) are rendered in 3D space.
* **`translateZ()`:**  Moves the faces along the z-axis to create depth.
* **`rotateX()` and `rotateY()`:** Rotate the faces around the x and y axes to create the cube's shape.
* **`backface-visibility: hidden;`:**  Prevents the back faces from being visible when the front faces are in front.
* **`@keyframes rotate`:** This defines the animation that smoothly rotates the cube.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** [Search "3D Transforms" on CSS-Tricks for numerous tutorials]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

