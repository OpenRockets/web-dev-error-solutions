# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using only CSS. We'll leverage CSS transforms and animations to achieve this effect.  No JavaScript is required.


## Description of the Styling

The cube will be composed of six square divs, each representing a face.  These faces will be positioned and rotated using `transform: rotateX`, `rotateY`, and `translateZ` to create the 3D illusion.  An animation will continuously rotate the cube along the Y-axis.  We'll use simple colors for each face to enhance visibility.

## Full Code (CSS Only)

```css
.cube {
  width: 100px;
  height: 100px;
  position: relative;
  transform-style: preserve-3d; /* Essential for 3D rendering */
  animation: rotate 8s linear infinite; /* Animate the rotation */
}

.face {
  position: absolute;
  width: 100px;
  height: 100px;
  opacity: 0.8; /*Slight transparency for better viewing*/
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  font-weight: bold;
  backface-visibility: hidden; /* Prevents faces from showing through */
}

.front {
  background: #f00;
  color: white;
  transform: translateZ(50px);
}

.back {
  background: #0f0;
  color: white;
  transform: translateZ(-50px) rotateY(180deg);
}

.right {
  background: #00f;
  color: white;
  transform: rotateY(90deg) translateZ(50px);
}

.left {
  background: #ff0;
  color: black;
  transform: rotateY(-90deg) translateZ(50px);
}

.top {
  background: #0ff;
  color: black;
  transform: rotateX(90deg) translateZ(50px);
}

.bottom {
  background: #f0f;
  color: black;
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

/*HTML Structure (Example):*/
<div class="cube">
  <div class="face front">Front</div>
  <div class="face back">Back</div>
  <div class="face right">Right</div>
  <div class="face left">Left</div>
  <div class="face top">Top</div>
  <div class="face bottom">Bottom</div>
</div>
```

## Explanation

* **`transform-style: preserve-3d;`**: This is crucial. It tells the browser to render the children of the `.cube` element in 3D space.
* **`translateZ()`**: This moves the faces along the z-axis, creating depth.
* **`rotateX()` and `rotateY()`**: These rotate the faces around the x and y axes, positioning them correctly.
* **`backface-visibility: hidden;`**: This prevents the back faces from being visible when they are facing away from the viewer, improving the visual effect.
* **`@keyframes rotate`**: This defines the animation that rotates the cube continuously.


## Resources to Learn More

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks on 3D Transforms:** [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/) (Search for 3D examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

