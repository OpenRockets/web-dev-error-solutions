# 🐞 CSS Challenge:  Tessellating Hexagons


This challenge involves creating a visually appealing tessellation of hexagons using CSS.  We'll achieve this effect using only CSS, avoiding the need for images or JavaScript.  The styling will focus on creating a clean, modern design with a subtle color palette.  We'll use CSS variables for easy customization.


## Description of the Styling

The design features a grid of hexagons, each slightly rotated to achieve the tessellation.  We'll utilize the `::before` and `::after` pseudo-elements to create the hexagonal shape using borders and transforms. Each hexagon will have a slightly different shade of a base color, creating a subtle depth effect.

## Full Code (CSS Only)

```css
:root {
  --hex-color: #4CAF50; /* Base hexagon color */
  --hex-size: 100px;   /* Size of the hexagon */
}

.hexagon-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr); /* Adjust for desired number of columns */
  grid-gap: 10px;
  width: fit-content;
}

.hexagon {
  width: var(--hex-size);
  height: calc(var(--hex-size) * 0.866); /* Height based on equilateral triangle */
  background-color: var(--hex-color);
  position: relative;
  margin: auto;
  transform: rotate(30deg); /* Rotate for tessellation */
}

.hexagon::before,
.hexagon::after {
  content: "";
  position: absolute;
  width: inherit;
  height: inherit;
  background-color: inherit;
  transform: rotate(60deg) scale(0.866);
  /* lighter color */
}

.hexagon::before{
    background-color: var(--hex-color);
    opacity: 0.8;
}

.hexagon::after{
    background-color: var(--hex-color);
    opacity: 0.6;
}

/* Add variation in color - optional, you could also add random classes */
.hexagon:nth-child(2n) {
  background-color: #558B2F;
}
.hexagon:nth-child(3n) {
  background-color: #689F38;
}
.hexagon:nth-child(4n) {
  background-color: #7CB341;
}
```


To use this code, create a `div` with the class `hexagon-container` and add multiple `div` elements with the class `hexagon` inside. Adjust the `grid-template-columns` property in `.hexagon-container` to control the number of hexagons per row.


## Explanation

* **CSS Variables:**  Using `--hex-color` and `--hex-size` allows for easy customization of the hexagon's color and size.
* **Grid Layout:** The `grid` layout makes arranging the hexagons simple and responsive.
* **Pseudo-elements:** `::before` and `::after` create the hexagonal shape by overlapping rotated elements.
* **Transformations:** `rotate` and `scale` are used to create the hexagonal shape and tessellation.
* **nth-child selector:** To showcase how to add variation we use nth child selectors to change colors.  This is just an example, more complex variations could be implemented.


## Resources to Learn More

* **CSS Grid Layout:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

