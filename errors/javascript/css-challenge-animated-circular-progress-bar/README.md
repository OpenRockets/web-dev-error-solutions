# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using only CSS.  We'll achieve this effect using CSS animations and transformations to create a visually appealing and dynamic progress indicator.  No JavaScript is required.

## Description of the Styling

The progress bar will be a circle, partially filled with a vibrant color.  The fill will animate from 0% to a specified percentage (we'll use 75% in this example), creating a loading or progress visualization.  We'll style it with a clean and modern look, using only CSS.

## Full Code (CSS Only)

```css
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #f0f0f0; /* Light gray background */
  border: 5px solid #ddd; /* Light gray border */
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #4CAF50; /* Green fill color */
  clip-path: polygon(50% 50%, 0% 50%, 0% 0%); /* Initially half-filled */
  animation: progress-animation 2s linear forwards;
}

@keyframes progress-animation {
  to {
    clip-path: polygon(50% 50%, 0% 50%, 0% 0%, 75% 0%, 75% 100%, 0% 100%); /* Animate to 75% fill */
  }
}

/* Optional: Add text overlay */
.progress-ring span {
  position: absolute;
  font-size: 1.2em;
  color: #333;
  font-weight: bold;
}
```

To use this code, simply create a `div` with the class `progress-ring` and optionally add a `<span>` inside for text display (e.g., percentage complete):


```html
<div class="progress-ring">
  <span>75%</span>
</div>
```


## Explanation

* **`progress-ring` class:** This sets up the base circular structure using `border-radius`, dimensions, and positioning.
* **`::before` pseudo-element:** This creates the circular fill.  The `clip-path` property initially creates a triangle, then animates to a shape representing the desired progress percentage using the `polygon()` function.
* **`@keyframes progress-animation`:** Defines the animation, changing the `clip-path` from the initial triangle to a shape representing 75% filled circle over 2 seconds.  `linear` makes the animation move at a constant speed, and `forwards` makes the animation stay at the end state.


## Resources to Learn More

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS `clip-path`:** [MDN Web Docs - clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

