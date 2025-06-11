# 🐞 CSS Challenge:  Tessellating Hexagons


This challenge involves creating a visually appealing tessellation of hexagons using CSS. We'll achieve this using only CSS, focusing on the `::before` and `::after` pseudo-elements and transforms to create the hexagonal shape and replicate it to form the tessellation.  This example uses plain CSS; adapting it to Tailwind CSS would involve replacing the inline styles with Tailwind classes.


**Description of the Styling:**

The core idea is to create a single hexagon using a square element and its pseudo-elements.  We then use transforms (rotation and translation) to position multiple copies of this hexagon to create the tessellation effect.  The colors and size can be easily adjusted to achieve different visual effects.


**Full Code:**

```css
.hexagon-container {
  width: 500px; /* Adjust for desired overall width */
  height: auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.hexagon {
  position: relative;
  width: 100px;
  height: 86.6px; /* Height based on width and sqrt(3)/2 */
  margin: 28.866px 0; /* Margin to create spacing between hexagons */
  background-color: #f0f0f0; /* Hexagon color */
  transform: rotate(30deg);
}

.hexagon::before,
.hexagon::after {
  content: "";
  position: absolute;
  background-color: inherit;
  width: 100px;
  height: 86.6px;
  transform: rotate(60deg);
}

.hexagon::before {
  left: -50px;
  transform-origin: 100% 50%;
}

.hexagon::after {
  right: -50px;
  transform-origin: 0% 50%;
}

/* Example for arranging multiple hexagons (adjust as needed) */
.hexagon-container .hexagon:nth-child(2n+1) {
  margin-left: 50px; /* Adjust spacing */
}
```

**Explanation:**

1. **`.hexagon-container`:** This sets up the container to hold the hexagons, using flexbox for easy arrangement.
2. **`.hexagon`:** This is the base hexagon. The height is calculated based on the width and the trigonometric ratio (sqrt(3)/2) to maintain the correct hexagonal shape.  The `transform: rotate(30deg);` rotates the square to create the initial hexagonal shape.
3. **`.hexagon::before` and `.hexagon::after`:** These pseudo-elements create the top and bottom halves of the hexagon by using rotated squares. The `transform-origin` is crucial for proper positioning.
4. **Margins and Arrangement:** Margins are used to separate hexagons, and the `nth-child` selector helps to adjust the horizontal placement. You might need to adjust these values depending on your desired arrangement and hexagon size.


**Links to Resources to Learn More:**

* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-elements:** [MDN Web Docs - CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **Flexbox Layout:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

