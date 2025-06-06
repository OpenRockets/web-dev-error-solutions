# 🐞 Creating a CSS-Only 3D Rotating Cube


This document details the creation of a 3D rotating cube using only CSS. No JavaScript is required! This effect leverages CSS transforms and animations to create a visually appealing and interactive element.

**Description of the Styling:**

This styling uses six divs to represent the faces of a cube.  Absolute positioning and `transform: rotateX`, `rotateY`, and `translateZ` are used to arrange them in three-dimensional space.  A CSS animation smoothly rotates the cube along the Y-axis.  We use Tailwind CSS for rapid styling.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS 3D Rotating Cube</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<style>
.cube {
  width: 200px;
  height: 200px;
  position: relative;
  transform-style: preserve-3d; /* Essential for 3D transformations */
  animation: rotation 10s linear infinite; /* Animate the rotation */
}

.cube > div {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: #f0f0f0;
  opacity: 0.8; /*Slightly transparent to show depth*/
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  color: white;
}

.front {
  transform: translateZ(100px);
  background-color: #4CAF50; /*Green*/
}

.back {
  transform: translateZ(-100px) rotateY(180deg);
  background-color: #f44336; /*Red*/
}

.right {
  transform: rotateY(90deg) translateZ(100px);
  background-color: #2196F3; /*Blue*/
}

.left {
  transform: rotateY(-90deg) translateZ(100px);
  background-color: #FF9800; /*Orange*/
}

.top {
  transform: rotateX(90deg) translateZ(100px);
  background-color: #9C27B0; /*Purple*/
}

.bottom {
  transform: rotateX(-90deg) translateZ(100px);
  background-color: #00BCD4; /*Cyan*/
}


@keyframes rotation {
  from {
    transform: rotateY(0deg);
  }
  to {
    transform: rotateY(360deg);
  }
}
</style>
</head>
<body class="bg-gray-200 flex justify-center items-center h-screen">
<div class="cube">
  <div class="front">Front</div>
  <div class="back">Back</div>
  <div class="right">Right</div>
  <div class="left">Left</div>
  <div class="top">Top</div>
  <div class="bottom">Bottom</div>
</div>
</body>
</html>
```

**Explanation:**

1. **`transform-style: preserve-3d;`:** This is crucial. It tells the browser to render the children elements in 3D space, allowing the rotations to work correctly.

2. **`translateZ()`:** This moves the faces along the z-axis, creating depth.  Positive values move the face towards the viewer, negative values away.

3. **`rotateX()` and `rotateY()`:** These rotate the faces around the x and y axes, respectively.

4. **`@keyframes rotation`:** This defines the animation, smoothly rotating the cube around the y-axis.

5. **Tailwind CSS:**  Tailwind provides utility classes for quick styling of the body and background.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

