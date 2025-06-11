# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using only CSS.  We'll achieve this effect using CSS animations and transforms to create a visually appealing and dynamic progress indicator.  This example uses only CSS and no JavaScript.

## Description of the Styling

The progress bar will be a circle with a colored segment representing the progress.  The segment will animate to fill the circle, simulating a loading or progress indicator. We'll achieve the circular shape using the `border-radius` property and the animated segment using a rotated pseudo-element (`::before`).  The animation will be smooth and visually engaging.


## Full Code (CSS Only)

```css
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  border: 10px solid #ddd; /* Light grey border */
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 5px;
  left: 5px;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 10px solid #4CAF50; /* Green progress color */
  border-right-color: transparent; /* Make the progress segment transparent */
  transform: rotate(0deg);
  animation: progress-animation 2s linear forwards; /* Animate over 2 seconds */
}

@keyframes progress-animation {
  to {
    transform: rotate(360deg); /* Rotate 360 degrees to complete the circle */
  }
}

/* Example to control progress: */
.progress-ring.progress-75::before {
    animation: progress-animation 2s linear forwards 0.75s; /* Adjust animation delay to simulate 75% progress */
}
```

To change the percentage simply adjust the `animation-delay` property in the class `.progress-75`.

You can use a class like `.progress-75` (or similar `.progress-x` where 'x' is the percentage) with the respective adjusted animation delay to easily control the progress visually.


## Explanation

* **`.progress-ring`**: This class styles the main circle, setting its dimensions, border-radius, and border.  `position: relative;` is crucial for absolute positioning of the pseudo-element.

* **`.progress-ring::before`**: This pseudo-element creates the animated progress segment.  `border-right-color: transparent;` makes only the left part of the border visible, creating the progress segment.  The `transform: rotate()` property and the `progress-animation` keyframes animate the rotation of this segment.

* **`@keyframes progress-animation`**: This defines the animation, smoothly rotating the segment to complete the circle. `linear` ensures a constant speed. `forwards` keeps the final state at the end of the animation.

* **`progress-75` Class**: Demonstrates controlling the progress by adjusting the `animation-delay` property.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
* **MDN Web Docs - `transform` property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks - Animations:** [https://css-tricks.com/almanac/properties/a/animation/](https://css-tricks.com/almanac/properties/a/animation/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

