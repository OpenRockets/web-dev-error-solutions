# 🐞 Creating a CSS-only 3D Cube


This document details the creation of a 3D cube using only CSS.  No JavaScript or other external libraries are required. This effect leverages CSS transforms and pseudo-elements to create the illusion of depth and three-dimensionality.

**Description of the Styling:**

The cube is constructed using a single `div` element as the base.  Six pseudo-elements (`::before` and `::after` for each face) are used to represent the cube's faces.  CSS transforms ( `rotateX`, `rotateY`, `translateZ`) are applied to position and rotate these faces to create the 3D effect.  Appropriate background colors and shadows are added to enhance realism.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS 3D Cube</title>
<style>
.cube {
  width: 100px;
  height: 100px;
  position: relative;
  transform-style: preserve-3d; /* Essential for 3D effect */
  animation: rotate 10s linear infinite;
}

.cube::before,
.cube::after,
.cube:before::before,
.cube:before::after,
.cube:after::before,
.cube:after::after {
  position: absolute;
  content: '';
  width: 100px;
  height: 100px;
  background-color: rgba(255,0,0,0.8); /* Example Color - Change as needed */
  opacity: 0.8;
  
}


.cube::before {
  transform: rotateX(90deg) translateZ(50px);
  background-color: rgba(0,255,0,0.8);
}

.cube::after {
  transform: rotateY(90deg) translateZ(50px);
  background-color: rgba(0,0,255,0.8);
}

.cube:before::before{
    transform: translateZ(50px);
    background-color: rgba(255,255,0,0.8);
}

.cube:before::after{
    transform: rotateY(180deg) translateZ(50px);
    background-color: rgba(255,0,255,0.8);
}

.cube:after::before{
    transform: rotateX(-90deg) translateZ(50px);
    background-color: rgba(0,255,255,0.8);
}

.cube:after::after{
    transform: rotateY(180deg) rotateX(-90deg) translateZ(50px);
    background-color: rgba(128,0,128,0.8);
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

<div class="cube"></div>

</body>
</html>
```


**Explanation:**

1. **`transform-style: preserve-3d;`:** This is crucial. It ensures that the children of the `.cube` element are rendered in 3D space.

2. **`transform: rotateX(90deg) translateZ(50px);` (and similar):** These transforms manipulate the position and orientation of each face. `rotateX` and `rotateY` rotate around the X and Y axes respectively. `translateZ` moves the element along the Z-axis (depth).  The `50px` value determines the cube's depth.  Adjust this value to change the cube's size.

3. **`@keyframes rotate`:** This creates an animation that smoothly rotates the cube.


**Links to Resources to Learn More:**

* [MDN Web Docs on CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [Understanding 3D Transforms](https://css-tricks.com/almanac/properties/t/transform/)
* [CSS Tricks](https://css-tricks.com/) (A great resource for CSS techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

