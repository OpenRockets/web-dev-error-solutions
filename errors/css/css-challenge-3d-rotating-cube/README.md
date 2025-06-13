# 🐞 CSS Challenge:  3D Rotating Cube


This challenge involves creating a 3D rotating cube using CSS3 transforms and animations.  The cube will have six distinct faces, each with a different color, and it will continuously rotate on its Y-axis.  We'll achieve this using a combination of `transform-style: preserve-3d;`, `transform: rotateY()`, and keyframes for smooth animation.  While we could use any CSS framework, this example will leverage plain CSS for better understanding of the fundamentals.


**Description of the Styling:**

The cube will be constructed using six divs, each representing a face. These divs will be positioned absolutely within a parent container.  Each face will have a unique background color.  Using `transform` properties, we'll position each face to create the 3D effect. The `transform-style: preserve-3d;` on the parent container is crucial for ensuring that the 3D transformations are applied correctly to the children.  Finally, a CSS animation will continuously rotate the cube.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>3D Rotating Cube</title>
<style>
.container {
  width: 200px;
  height: 200px;
  perspective: 800px; /* Adjust for perspective effect */
  transform-style: preserve-3d;
  animation: rotate 10s linear infinite; /* Animate rotation */
}

.face {
  position: absolute;
  width: 100px;
  height: 100px;
  border: 1px solid black;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  backface-visibility: hidden; /* Prevents faces from appearing flat */
}

.face.front {
  background-color: red;
  transform: translateZ(50px);
}

.face.back {
  background-color: blue;
  transform: translateZ(-50px) rotateY(180deg);
}

.face.right {
  background-color: green;
  transform: translateX(50px) rotateY(90deg);
}

.face.left {
  background-color: yellow;
  transform: translateX(-50px) rotateY(-90deg);
}

.face.top {
  background-color: purple;
  transform: translateY(-50px) rotateX(90deg);
}

.face.bottom {
  background-color: orange;
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
<div class="container">
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

* **`perspective`:** This property creates the 3D perspective effect.  Adjust the value to change the strength of the perspective.
* **`transform-style: preserve-3d;`:** This is crucial. It tells the browser to treat the children of the container as 3D elements.
* **`transform: translateZ()`:** This moves the faces along the z-axis to create depth.
* **`transform: rotateY()`:** This rotates the faces around the y-axis.  We use this in conjunction with `translateX()` to position the sides.
* **`backface-visibility: hidden;`:** This prevents the back faces from being visible when they are facing away from the viewer.
* **`@keyframes rotate`:** This defines the animation, rotating the cube 360 degrees over 10 seconds.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks on 3D Transforms:** [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

