# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using CSS.  We'll achieve this using only CSS, without relying on JavaScript. The goal is to create a visually appealing and smoothly animated progress indicator.  This solution utilizes CSS variables and animations for flexibility and control.


## Styling Description

The progress bar is a circle with a thicker ring representing the progress track.  The inner part of the ring fills progressively to indicate the percentage complete.  The animation smoothly fills the circle from 0% to a specified value.  We'll use CSS variables to easily adjust the size, colors, and percentage complete.


## Full Code (CSS Only)

```css
:root {
  --progress-size: 150px;
  --progress-background: #e0e0e0;
  --progress-color: #4CAF50;
  --progress-percentage: 75; /* Adjust this value to change the progress */
}

.progress-container {
  width: var(--progress-size);
  height: var(--progress-size);
  position: relative;
}

.progress-ring {
  width: var(--progress-size);
  height: var(--progress-size);
  border-radius: 50%;
  border: 10px solid var(--progress-background);
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: var(--progress-size);
  height: var(--progress-size);
  border-radius: 50%;
  border: 10px solid var(--progress-color);
  border-right-color: transparent; /* Hide the right side of the circle initially*/
  transform: rotate(-90deg); /* Start at 0% position */
  animation: progress-animation var(--progress-duration) linear forwards;
}


@keyframes progress-animation {
  to {
    transform: rotate(calc(360deg * var(--progress-percentage) / 100 - 90deg));
  }
}

/* Set animation duration based on percentage */
:root {
  --progress-duration: 2s; /* Adjust as needed */
}
```

**To use this code:**

1. Create an HTML file (e.g., `index.html`).
2. Add a `<div>` with the class `progress-container` in the `<body>` of your HTML file.
3. Include the CSS code in a `<style>` tag within the `<head>` or in a separate CSS file linked to your HTML.

The progress bar will appear within the `progress-container` div.


## Explanation

* **CSS Variables:**  Using `:root` allows for easy customization of colors, size, and percentage.
* **`::before` Pseudo-element:** Creates the inner circle that fills up.
* **`border-right-color: transparent;`:**  This cleverly hides the part of the circular border that isn't yet "filled," creating the effect of a partially filled circle.
* **`transform: rotate();`:**  Rotates the inner circle to simulate the filling effect.
* **`@keyframes progress-animation`:**  Defines the animation that rotates the inner circle over time.  `linear` ensures a smooth animation. `forwards` keeps the animation at its final state.
* **`calc()`:**  Dynamically calculates the rotation angle based on the percentage.

## Resources to Learn More

* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **MDN Web Docs on CSS Variables:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)
* **CSS-Tricks on Animations:** [https://css-tricks.com/snippets/css/keyframe-animation-syntax/](https://css-tricks.com/snippets/css/keyframe-animation-syntax/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

