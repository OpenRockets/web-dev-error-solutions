# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using only CSS.  We'll utilize CSS transforms and animations to achieve the effect. No JavaScript will be required.


## Description of the Styling:

The cube will be composed of six square divs, each representing a face.  These faces will be positioned and rotated in 3D space to create the cube illusion.  CSS animations will provide the continuous rotation. We'll use a simple color scheme for clarity, but you can customize it easily.  The rotation will be around the Y-axis (spinning vertically).

## Full Code (CSS Only):

```css
.container {
  width: 200px;
  height: 200px;
  perspective: 800px; /* Adjust for perspective effect */
  position: relative; /* Needed for absolute positioning of cube faces */
}

.cube {
  width: 100px;
  height: 100px;
  position: absolute;
  transform-style: preserve-3d; /* Essential for 3D transforms */
  animation: rotate 10s linear infinite; /* Animation settings */
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.8; /* Slightly transparent for better depth perception */
  background-size: cover;
  border: 1px solid #ddd; /* Optional border for better visibility */
}

.face.front {
  background-color: #f00;
  transform: translateZ(50px);
}

.face.back {
  background-color: #0f0;
  transform: translateZ(-50px) rotateY(180deg);
}

.face.right {
  background-color: #00f;
  transform: rotateY(90deg) translateZ(50px);
}

.face.left {
  background-color: #ff0;
  transform: rotateY(-90deg) translateZ(50px);
}

.face.top {
  background-color: #0ff;
  transform: rotateX(90deg) translateZ(50px);
}

.face.bottom {
  background-color: #f0f;
  transform: rotateX(-90deg) translateZ(50px);
}


@keyframes rotate {
  from {
    transform: rotateY(0deg);
  }
  to {
    transform: rotateY(360deg);
  }
}

/* HTML Structure (Example):*/
<div class="container">
  <div class="cube">
    <div class="face front"></div>
    <div class="face back"></div>
    <div class="face right"></div>
    <div class="face left"></div>
    <div class="face top"></div>
    <div class="face bottom"></div>
  </div>
</div>
```


## Explanation:

1. **`container`**: Sets the perspective and contains the cube. `perspective` creates the 3D effect.
2. **`cube`**: Contains the faces and applies the rotation animation. `transform-style: preserve-3d` is crucial for correct 3D rendering.
3. **`face`**: Styles each face of the cube.
4. **`.face.front`, `.face.back`, etc.**:  Positions each face using `transform: translateZ()` and `rotateY()`.  `translateZ()` moves the face along the z-axis (depth), and `rotateY()` rotates it around the y-axis.
5. **`@keyframes rotate`**: Defines the animation that rotates the cube continuously.

## Resources to Learn More:

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:**  (Search "CSS-Tricks 3D transforms" for relevant tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

