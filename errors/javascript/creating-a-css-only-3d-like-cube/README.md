# 🐞 Creating a CSS-only 3D-like Cube


This document details the creation of a three-dimensional cube effect using only CSS.  No JavaScript or external libraries are required.  We'll leverage CSS transforms and box-shadow to achieve this illusion of depth.

**Description of the Styling:**

The cube is constructed using six divs, each representing a face.  These divs are positioned absolutely within a parent container.  CSS transforms (`rotateX`, `rotateY`, `translateZ`) are used to create the three-dimensional effect and position each face correctly.  Box-shadow adds depth and realism.  We'll use simple color variations to distinguish the faces.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS 3D Cube</title>
<style>
.container {
  width: 200px;
  height: 200px;
  perspective: 800px; /* Adjust for perspective effect */
  position: relative;
}

.cube {
  width: 100px;
  height: 100px;
  position: absolute;
  transform-style: preserve-3d; /* Crucial for 3D transforms */
  transition: transform 0.5s ease; /* Add smooth transition */
}

.cube:hover {
    transform: rotateX(360deg) rotateY(360deg); /* Example hover animation */
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: lightblue;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
  color: white;
  box-shadow: 0 0 10px rgba(0,0,0,0.5); /* Add a subtle shadow */
}

.face.front {
  background-color: lightcoral;
  transform: translateZ(50px);
}

.face.back {
  background-color: lightgreen;
  transform: rotateY(180deg) translateZ(50px);
}

.face.right {
  background-color: lightgoldenrodyellow;
  transform: rotateY(90deg) translateZ(50px);
}

.face.left {
  background-color: lightsalmon;
  transform: rotateY(-90deg) translateZ(50px);
}

.face.top {
  background-color: lightpink;
  transform: rotateX(90deg) translateZ(50px);
}

.face.bottom {
  background-color: lightgray;
  transform: rotateX(-90deg) translateZ(50px);
}
</style>
</head>
<body>

<div class="container">
  <div class="cube">
    <div class="face front">Front</div>
    <div class="face back">Back</div>
    <div class="face right">Right</div>
    <div class="face left">Left</div>
    <div class="face top">Top</div>
    <div class="face bottom">Bottom</div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:** This property on the container creates the 3D viewing space.  Adjust the value to change the perspective.
* **`transform-style: preserve-3d;`:** This is crucial. It tells the browser to render the children in 3D space.
* **`rotateX`, `rotateY`, `translateZ`:** These transform functions are used to position and orient each face of the cube.  `translateZ` moves the faces along the z-axis, creating the depth.
* **`box-shadow`:** Adds subtle shadows to enhance the 3D illusion.
* **Hover animation**: A simple rotation is added on hover for demonstration.



**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks on 3D Transforms:** [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

