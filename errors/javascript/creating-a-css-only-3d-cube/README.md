# 🐞 Creating a CSS-only 3D Cube


This document details how to create a three-dimensional cube using only CSS.  No JavaScript is required. This effect leverages CSS transforms (`rotateX`, `rotateY`) and multiple pseudo-elements to build the illusion of depth.

**Description of the Styling:**

The cube is constructed using a single `div` element as the base, and six pseudo-elements (`::before` and `::after` nested to create a total of six faces). Each face is styled individually with a different background color to distinguish them.  CSS transforms are then applied to rotate these faces into a three-dimensional arrangement.  The perspective property is crucial in creating the sense of depth.


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
  perspective: 150px; /* Adjust for perspective strength */
  margin: 50px auto;
}

.cube, .cube::before, .cube::after {
  background-color: #ddd; /* Base color */
  display: block;
}

.cube::before, .cube::after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
}

.cube::before {
  transform: translateZ(-50px) rotateX(90deg);
  background-color: lightblue; /* Top Face */
}

.cube::after {
  transform: translateZ(50px) rotateX(180deg) rotateY(180deg);
  background-color: lightgreen; /* Bottom Face */
}

.cube:before::before, .cube:before::after, .cube:after::before, .cube:after::after {
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    transform-style: preserve-3d;
    background-color: #ddd;
}


/*Side Faces*/

.cube::before::before {
  transform: translateZ(-50px) rotateY(90deg);
  background-color: lightcoral; /* Right Face */
}

.cube::before::after {
  transform: translateZ(-50px) rotateY(-90deg);
  background-color: lightyellow; /* Left Face */
}

.cube::after::before {
  transform: translateZ(50px) rotateY(90deg);
  background-color: lightpink; /* Right Face Bottom */
}

.cube::after::after {
  transform: translateZ(50px) rotateY(-90deg);
  background-color: lightcyan; /* Left Face Bottom */
}



.cube::before::before, .cube::before::after, .cube::after::before, .cube::after::after {
    background-size: 100% 100%;
}
</style>
</head>
<body>

<div class="cube"></div>

</body>
</html>
```

**Explanation:**

1. **`perspective`:** This property on the main `.cube` element creates the 3D viewing space.  Adjust the value (in pixels) to change the perspective strength.

2. **`transform-style: preserve-3d;`:** This crucial property ensures that the transformations on child elements are applied in 3D space.

3. **`translateZ()`:** This moves the pseudo-elements along the z-axis (into and out of the screen), creating the depth.

4. **`rotateX()` and `rotateY()`:** These rotate the elements around the x and y axes, creating the cube's faces.

5. **Nested Pseudo-elements:** We use nested pseudo-elements to efficiently create the cube's six faces. The careful arrangement of rotations and translations is key to achieve the desired effect.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Tricks on 3D Transforms:** (Search for "CSS 3D Transforms" on CSS Tricks website)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

