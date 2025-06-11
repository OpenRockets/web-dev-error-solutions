# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using only CSS.  We'll achieve this effect using transformations and animations without any JavaScript. This example utilizes CSS3 properties.

**Description of the Styling:**

The cube is constructed using six divs, each representing a face.  These are positioned absolutely within a parent container.  `transform-style: preserve-3d;` on the parent is crucial; it ensures that child elements are rendered in 3D space.  Each face is rotated and translated to its correct position on the cube.  Keyframes animation rotates the cube around the Y-axis continuously.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
.cube {
  width: 200px;
  height: 200px;
  perspective: 800px; /* Adjust for perspective effect */
  transform-style: preserve-3d;
  animation: rotation 10s linear infinite;
}

.face {
  position: absolute;
  width: 100px;
  height: 100px;
  background-color: rgba(255,0,0,0.7); /*Example color, change as needed*/
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  color: white;
  backface-visibility: hidden; /* Prevents back faces from showing */
}

.front {
  transform: translateZ(50px);
}

.back {
  transform: translateZ(-50px) rotateY(180deg);
}

.top {
  transform: translateY(-50px) rotateX(90deg);
}

.bottom {
  transform: translateY(50px) rotateX(-90deg);
}

.left {
  transform: translateX(-50px) rotateY(-90deg);
}

.right {
  transform: translateX(50px) rotateY(90deg);
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
<body>

<div class="cube">
  <div class="face front">Front</div>
  <div class="face back">Back</div>
  <div class="face top">Top</div>
  <div class="face bottom">Bottom</div>
  <div class="face left">Left</div>
  <div class="face right">Right</div>
</div>

</body>
</html>
```

**Explanation:**

1. **`perspective`:**  This property on the `.cube` creates the 3D viewing perspective.  Adjust the value to change the depth effect.
2. **`transform-style: preserve-3d;`:** This is crucial. It tells the browser to render the child elements (`faces`) in 3D space.
3. **`transform` on each face:** Each face is translated and rotated to its correct position within the 3D space of the cube.
4. **`backface-visibility: hidden;`:**  This prevents the back faces of the cube from being visible when rotated, creating a more realistic look.
5. **`@keyframes rotation`:** This defines the animation that rotates the cube continuously.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** (Search for "CSS 3D Transforms" on CSS-Tricks for numerous tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

