# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using only CSS.  We'll leverage CSS transforms and animations to achieve this effect without any JavaScript.  This example uses plain CSS, but could easily be adapted to Tailwind CSS by replacing the inline styles with Tailwind classes.

**Description of the Styling:**

The cube is constructed using six divs, each representing a face.  These divs are positioned absolutely within a parent container.  `transform: rotateX`, `transform: rotateY`, and `transform: rotateZ` are used to create the 3D effect.  CSS animations are applied to continuously rotate the cube along the Y-axis.  Different colours are assigned to each face for visual clarity.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
body {
  perspective: 1000px; /* Necessary for 3D effect */
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.cube {
  width: 200px;
  height: 200px;
  position: relative;
  transform-style: preserve-3d; /* Essential for 3D rendering */
  animation: rotate 10s linear infinite;
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 3em;
  color: white;
  backface-visibility: hidden; /* Prevents faces from showing through */
}

.front { background-color: #007bff; transform: translateZ(100px); }
.back { background-color: #28a745; transform: translateZ(-100px) rotateY(180deg); }
.right { background-color: #dc3545; transform: translateX(100px) rotateY(90deg); }
.left { background-color: #ffc107; transform: translateX(-100px) rotateY(-90deg); }
.top { background-color: #17a2b8; transform: translateY(-100px) rotateX(90deg); }
.bottom { background-color: #6c757d; transform: translateY(100px) rotateX(-90deg); }

@keyframes rotate {
  from { transform: rotateY(0deg); }
  to { transform: rotateY(360deg); }
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

* **`perspective`:** This property on the `body` creates the 3D viewing space.
* **`transform-style: preserve-3d;`:** This is crucial; it ensures that child elements are rendered in 3D space.
* **`translateZ`:** Moves elements along the Z-axis (depth).
* **`rotateX`, `rotateY`, `rotateZ`:** Rotate elements around the respective axes.
* **`backface-visibility: hidden;`:** Prevents the back faces from being visible when rotated.
* **`@keyframes rotate`:** Defines the animation that rotates the cube continuously.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

