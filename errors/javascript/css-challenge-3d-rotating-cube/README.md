# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using CSS transforms and animations.  We'll achieve this effect without any JavaScript, relying solely on CSS3 properties.  The cube will have six distinct faces, each with a different color, and will smoothly rotate continuously.


## Styling Description

The cube is constructed using six divs, each representing a face. These divs are positioned absolutely within a parent container.  CSS transforms (`rotateX`, `rotateY`, `translateZ`) are used to position and orient each face in 3D space.  A CSS animation creates the continuous rotation effect.  We'll use a simple color scheme for each face for clarity.


## Full Code (CSS Only)

```css
.container {
  width: 200px;
  height: 200px;
  perspective: 800px; /* Adjust for perspective effect */
  position: relative;
  margin: 50px auto;
}

.cube {
  width: 100%;
  height: 100%;
  position: absolute;
  transform-style: preserve-3d; /* Essential for 3D effect */
  animation: rotate 8s linear infinite; /* Animate rotation */
}

.face {
  position: absolute;
  width: 100px;
  height: 100px;
  line-height: 100px; /* Center text vertically */
  text-align: center;
  font-size: 2em;
  font-weight: bold;
  backface-visibility: hidden; /* Prevents faces from appearing flipped */
}

.front {
  background-color: #f00;
  transform: translateZ(50px);
}

.back {
  background-color: #0f0;
  transform: translateZ(-50px) rotateY(180deg);
}

.right {
  background-color: #00f;
  transform: rotateY(90deg) translateZ(50px);
}

.left {
  background-color: #ff0;
  transform: rotateY(-90deg) translateZ(50px);
}

.top {
  background-color: #0ff;
  transform: rotateX(90deg) translateZ(50px);
}

.bottom {
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

/*HTML Structure (example)*/
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
```

## Explanation

* **`perspective`:** This property on the container creates the 3D perspective.  Adjusting this value changes how the cube appears to recede into the distance.
* **`transform-style: preserve-3d;`:** This is crucial. It tells the browser to render the children elements in 3D space.
* **`backface-visibility: hidden;`:**  This prevents the back faces of the cube from being visible when they are facing away from the viewer.
* **`transform`:** Each face uses `transform` to position itself correctly within the 3D space.  `translateZ` moves the face along the Z-axis (depth), while `rotateX` and `rotateY` rotate it around the X and Y axes.
* **`@keyframes rotate`:** This defines the animation, smoothly rotating the cube around the Y-axis.


## Resources to Learn More

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** [Search "3D Transforms" on css-tricks.com for various tutorials]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

