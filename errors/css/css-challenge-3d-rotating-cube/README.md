# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a rotating 3D cube using only CSS.  We'll leverage CSS transforms to achieve the 3D effect and animations for the rotation.  This example utilizes plain CSS3, but similar effects could be achieved with CSS frameworks like Tailwind CSS by leveraging their utility classes for transformations and animations.


**Description of the Styling:**

The cube is constructed using six divs, each representing a face.  These divs are positioned absolutely within a parent container.  `transform-style: preserve-3d;` on the parent is crucial; it ensures that child elements are rendered in 3D space.  Individual face divs are rotated using `transform: rotateX()`, `rotateY()`, and `translateZ()` to position them correctly in a cube formation.  The `animation` property applies a continuous rotation.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
body {
  perspective: 800px; /* Adjust for perspective effect */
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.cube {
  width: 200px;
  height: 200px;
  transform-style: preserve-3d;
  animation: rotate 8s linear infinite;
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(255,0,0,0.7); /*Example Color, Change as needed */
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 3em;
  color: white;
}

.face:nth-child(1) {
  transform: translateZ(100px);
}

.face:nth-child(2) {
  transform: rotateY(90deg) translateZ(100px);
}

.face:nth-child(3) {
  transform: rotateY(180deg) translateZ(100px);
}

.face:nth-child(4) {
  transform: rotateY(-90deg) translateZ(100px);
}

.face:nth-child(5) {
  transform: rotateX(90deg) translateZ(100px);
}

.face:nth-child(6) {
  transform: rotateX(-90deg) translateZ(100px);
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
    <div class="face">1</div>
    <div class="face">2</div>
    <div class="face">3</div>
    <div class="face">4</div>
    <div class="face">5</div>
    <div class="face">6</div>
  </div>
</body>
</html>
```


**Explanation:**

* **`perspective`:** This property on the `body` creates the 3D perspective.  Adjust the value to change the viewing angle.
* **`transform-style: preserve-3d;`:** This is essential; it ensures that the child elements (.face) are positioned in 3D space.
* **`transform` on `.face` elements:** These are crucial for positioning each face of the cube correctly using rotations and translations along the Z-axis.
* **`@keyframes rotate`:** This defines the animation, creating a continuous rotation around the Y-axis.


**Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** (Search for "3D Transforms" on CSS-Tricks for numerous tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

