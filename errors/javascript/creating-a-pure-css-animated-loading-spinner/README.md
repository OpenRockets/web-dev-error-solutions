# 🐞 Creating a Pure CSS Animated Loading Spinner


This document details the creation of a simple, yet visually appealing loading spinner using only CSS.  No JavaScript is required!  This example uses pure CSS3 animations and transforms to achieve the effect.

**Description of the Styling:**

The spinner consists of a single element, a pseudo-element (`::before`), that is rotated continuously using CSS animations. The pseudo-element is styled to create a circular shape with a gradient for visual appeal. The animation smoothly rotates the element, creating the spinning effect. We use keyframes to define the animation's progression over time.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Loading Spinner</title>
<style>
.spinner {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 5px solid #f3f3f3; /* Light grey border */
  border-top: 5px solid #3498db; /* Blue color for the spinning part */
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
</head>
<body>

<h1>Loading...</h1>
<div class="spinner"></div>

</body>
</html>
```

**Explanation:**

* **`.spinner`:** This class defines the main container for the spinner.  `width` and `height` set its size, `border-radius` creates the circle, and the `border` properties define the spinner's appearance.  The `border-top` is a different color to create the spinning effect.  The `animation` property applies the `spin` animation.

* **`@keyframes spin`:** This defines the animation named "spin". It smoothly rotates the element from 0 degrees to 360 degrees over one second (`1s`), repeating infinitely (`infinite`).  The `linear` keyword ensures a constant rotation speed.


**Links to Resources to Learn More:**

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

