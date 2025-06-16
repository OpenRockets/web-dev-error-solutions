# 🐞 CSS Challenge:  Tessellating Hexagon Grid


This challenge involves creating a grid of hexagons that tessellate perfectly (meaning they fit together without gaps). We'll use CSS Grid for layout and some clever transformations to achieve the hexagonal shape.  This example uses pure CSS, but could easily be adapted to use a CSS framework like Tailwind CSS.

## Description of the Styling

The goal is to create a visually appealing grid of hexagons.  Each hexagon should be the same size and uniformly spaced. The styling will focus on creating the hexagon shape using rotations and transforms, then arranging them using CSS Grid. We'll add some basic styling for color and border to make the hexagons stand out.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Hexagon Grid</title>
<style>
.hexagon-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr); /* Adjust for number of columns */
  grid-auto-rows: 100px; /* Adjust hexagon height */
  width: 600px; /* Adjust grid width */
  margin: 50px auto;
}

.hexagon {
  width: 100%;
  height: 100%;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
  position: relative; /*Needed for the ::before pseudo-element*/
}

.hexagon::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.1); /*optional inner shadow*/
  transform: rotate(30deg);
  z-index:-1;
}

/*Offsetting even rows to create tessellation*/
.hexagon-grid > div:nth-child(even) {
  margin-left: 50%; /*Half the width of the hexagon*/
}

.hexagon-grid > div:nth-child(even)::before {
    left: -50%; /*Adjusting the inner shadow*/
}
</style>
</head>
<body>

<div class="hexagon-grid">
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
  <div class="hexagon"></div>
</div>

</body>
</html>
```

## Explanation

1. **CSS Grid:** The `.hexagon-grid` class uses CSS Grid to create the overall grid layout. `grid-template-columns` defines the number of columns, and `grid-auto-rows` sets the height of each row.


2. **Hexagon Shape:** The `.hexagon` class uses the `clip-path` property with a polygon shape to create the hexagon.


3. **Tessellation:** The `nth-child(even)` selector is used to offset every other row, ensuring perfect tessellation.  The margin-left is half of a hexagon's width.

4. **Inner Shadow (Optional):** The `::before` pseudo-element adds a subtle inner shadow for visual depth. This part could be removed if not needed.

## Links to Resources to Learn More

* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Clip-Path:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

