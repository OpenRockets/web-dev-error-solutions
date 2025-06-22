# 🐞 CSS Challenge:  3D Rotating Cube with CSS Animations


This challenge involves creating a 3D rotating cube using only CSS.  We'll achieve the 3D effect using transforms and animations, creating a visually appealing and interactive element. We will use standard CSS3 properties for this challenge, showcasing techniques applicable to a wide range of projects.


**Description of the Styling:**

The cube will consist of six square divs, each representing a face. These faces will be positioned and rotated using CSS `transform` properties to create the 3D effect.  A CSS animation will then continuously rotate the cube around its Y-axis.  Each face will have a different background color for clear visual distinction.


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
  perspective: 800px; /* Creates the 3D perspective */
  margin: 50px auto;
}

.cube {
  width: 100%;
  height: 100%;
  transform-style: preserve-3d; /* Essential for 3D transformations */
  animation: rotate 8s linear infinite; /* Continuous rotation */
}

.face {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Prevents back faces from showing */
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  color: white;
}

.face-front { background-color: #f00; }
.face-right { background-color: #0f0; transform: rotateY(90deg) translateZ(100px); }
.face-back { background-color: #00f; transform: rotateY(180deg) translateZ(100px); }
.face-left { background-color: #ff0; transform: rotateY(-90deg) translateZ(100px); }
.face-top { background-color: #0ff; transform: rotateX(90deg) translateZ(100px); }
.face-bottom { background-color: #f0f; transform: rotateX(-90deg) translateZ(100px); }


@keyframes rotate {
  from { transform: rotateY(0deg); }
  to { transform: rotateY(360deg); }
}
</style>
</head>
<body>

<div class="container">
  <div class="cube">
    <div class="face face-front">Front</div>
    <div class="face face-right">Right</div>
    <div class="face face-back">Back</div>
    <div class="face face-left">Left</div>
    <div class="face face-top">Top</div>
    <div class="face face-bottom">Bottom</div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:** This property on the container creates the 3D viewing space.
* **`transform-style: preserve-3d;`:** This is crucial; it ensures that child elements are rendered in 3D space.
* **`backface-visibility: hidden;`:** This hides the back of each face, preventing visual artifacts.
* **`rotateY` and `translateZ`:** These are used to position and rotate each face to form the cube.  `translateZ` moves the faces along the z-axis, creating depth.
* **`@keyframes rotate`:** This defines the animation, smoothly rotating the cube around its Y-axis.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS-Tricks - 3D Transforms:** (Search "CSS-Tricks 3D Transforms" on Google for relevant tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

