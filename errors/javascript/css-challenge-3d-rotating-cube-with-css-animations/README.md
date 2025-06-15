# 🐞 CSS Challenge:  3D Rotating Cube with CSS Animations


This challenge involves creating a 3D rotating cube using only CSS.  We'll leverage CSS transforms and animations to achieve the effect without relying on JavaScript.  This example uses standard CSS; adapting it to Tailwind would primarily involve replacing the CSS classes with their Tailwind equivalents.

**Description of the Styling:**

The cube is constructed using six divs, each representing a face.  These divs are absolutely positioned within a parent container.  `transform-style: preserve-3d;` is crucial on the parent to ensure that the 3D transformations are correctly applied to the child elements.  Each face is rotated and translated to its correct position in 3D space.  The `animation` property applies a continuous rotation, creating the 3D effect.  We'll use linear gradients for simple coloring of the faces.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
.cube {
  width: 100px;
  height: 100px;
  position: relative;
  transform-style: preserve-3d;
  animation: rotate 8s linear infinite;
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  color: white;
}

.face.front {
  background-color: lightblue;
  transform: translateZ(50px);
}

.face.back {
  background-color: lightgreen;
  transform: translateZ(-50px) rotateY(180deg);
}

.face.right {
  background-color: lightcoral;
  transform: translateX(50px) rotateY(90deg);
}

.face.left {
  background-color: lightyellow;
  transform: translateX(-50px) rotateY(-90deg);
}

.face.top {
  background-color: lightpink;
  transform: translateY(-50px) rotateX(90deg);
}

.face.bottom {
  background-color: lightgray;
  transform: translateY(50px) rotateX(-90deg);
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
  <div class="face front">Front</div>
  <div class="face back">Back</div>
  <div class="face right">Right</div>
  <div class="face left">Left</div>
  <div class="face top">Top</div>
  <div class="face bottom">Bottom</div>
</div>

</body>
</html>
```

**Explanation:**

* **`transform-style: preserve-3d;`**: This is applied to the parent `.cube` element. It's essential for rendering the child elements in 3D space. Without this, the cube would appear flat.

* **`translateZ()`**: This function moves the faces along the z-axis, creating depth. Positive values move the face towards the viewer, while negative values move it away.

* **`rotateY()` and `rotateX()`**: These functions rotate the faces around the y-axis (vertical) and x-axis (horizontal) respectively.  This positions the faces correctly to form a cube.

* **`@keyframes rotate`**: This defines the animation that rotates the cube continuously around the y-axis.

* **Face Classes:** Each face has a class (e.g., `.front`, `.back`) that allows for individual styling and positioning.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks on 3D Transforms:** [Search "CSS 3D Transforms" on css-tricks.com](https://css-tricks.com/)  (Many tutorials exist on this site)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

