# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using only CSS.  We'll achieve the 3D effect through transforms and cleverly positioned pseudo-elements.  No JavaScript is required! This example uses CSS3 properties.

## Description of the Styling:

The cube will be composed of six square faces, each a different color.  These faces will be arranged to give the illusion of a cube rotating smoothly on a central axis.  The rotation will be achieved using CSS animations. We'll utilize `transform: rotateX`, `rotateY`, and `transform-style: preserve-3d` to achieve the 3D perspective.

## Full Code:

```css
.cube {
  width: 100px;
  height: 100px;
  position: relative;
  transform-style: preserve-3d;
  animation: rotate 8s linear infinite;
}

.cube div {
  position: absolute;
  width: 100px;
  height: 100px;
  background-color: #f00; /* Default red */
  opacity: 0.8;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 30px;
  color: white;
}

.cube .front {
  background-color: #f00;
  transform: translateZ(50px);
}

.cube .back {
  background-color: #00f;
  transform: translateZ(-50px) rotateY(180deg);
}

.cube .right {
  background-color: #0f0;
  transform: rotateY(90deg) translateZ(50px);
}

.cube .left {
  background-color: #ff0;
  transform: rotateY(-90deg) translateZ(50px);
}

.cube .top {
  background-color: #0ff;
  transform: rotateX(90deg) translateZ(50px);
}

.cube .bottom {
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

```

And the HTML:

```html
<div class="cube">
  <div class="front">Front</div>
  <div class="back">Back</div>
  <div class="right">Right</div>
  <div class="left">Left</div>
  <div class="top">Top</div>
  <div class="bottom">Bottom</div>
</div>
```


## Explanation:

* **`transform-style: preserve-3d;`**: This is crucial. It tells the browser to render the child elements in 3D space.
* **`translateZ()`**: This moves the faces along the z-axis, creating depth.
* **`rotateX()` and `rotateY()`**: These rotate the faces around the x and y axes, creating the cube structure.
* **`@keyframes rotate`**: This defines the animation, smoothly rotating the cube around the y-axis.

## Links to Resources to Learn More:

* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **3D Transformations Tutorial:**  [Search for "CSS 3D Transformations Tutorial" on your preferred search engine for numerous tutorials.]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

