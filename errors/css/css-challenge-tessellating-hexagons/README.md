# 🐞 CSS Challenge:  Tessellating Hexagons


This challenge involves creating a visually appealing tessellation of hexagons using CSS.  We'll leverage CSS Grid for layout and some clever transformations to achieve the hexagonal shape. This example uses plain CSS; adapting it to Tailwind would involve replacing the CSS classes with their Tailwind equivalents.

**Description of the Styling:**

The goal is to create a grid of hexagons that seamlessly tile together. Each hexagon will be a `div` element styled to appear as a hexagon using transforms and background color.  We'll use CSS Grid to arrange these hexagons in a neat, repeating pattern.  The overall effect should be a visually engaging, geometric design.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Hexagon Tessellation</title>
<style>
body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.container {
  display: grid;
  grid-template-columns: repeat(6, 1fr); /* Adjust for more/fewer columns */
  grid-gap: 0; /* No gap between hexagons */
}

.hexagon {
  width: 100px;
  height: 57.735px; /* sqrt(3)/2 * width */
  background-color: #4CAF50;
  margin: 28.8675px 0; /* height / 2 */
  position: relative;
  transform: rotate(30deg);
}

.hexagon::before,
.hexagon::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: inherit;
  transform: rotate(60deg);
}

.hexagon::before {
  transform: rotate(60deg) translateY(-100%);
}

.hexagon::after {
  transform: rotate(-60deg) translateY(100%);
}


/* Add variations for different colors (optional) */
.hexagon:nth-child(2n) { background-color: #2196F3; }
.hexagon:nth-child(3n) { background-color: #FF9800; }

</style>
</head>
<body>
<div class="container">
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
  <!-- Add more hexagons as needed -->
</div>
</body>
</html>
```

**Explanation:**

1. **Grid Layout:** The `container` uses CSS Grid to arrange the hexagons in rows and columns.  `grid-template-columns: repeat(6, 1fr)` creates six equal-width columns.  Adjust this value to change the number of hexagons per row.

2. **Hexagon Shape:**  Each `.hexagon` is a `div` with a specific `width` and `height`.  The height is calculated as `sqrt(3)/2 * width` to maintain the correct proportions. The `transform: rotate(30deg)` rotates the rectangle, and the `::before` and `::after` pseudo-elements create the top and bottom points of the hexagon.

3. **Positioning and Margins:** The margins are carefully calculated to ensure the hexagons seamlessly connect without gaps.

4. **Color Variations (Optional):**  The `:nth-child` selector is used to add different background colors to hexagons, creating more visual interest.


**Links to Resources to Learn More:**

* **CSS Grid:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

