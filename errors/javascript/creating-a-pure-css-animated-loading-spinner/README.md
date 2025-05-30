# 🐞 Creating a Pure CSS Animated Loading Spinner


This document details how to create a visually appealing animated loading spinner using only CSS.  No JavaScript is required.  This utilizes CSS animations and keyframes to achieve the effect.  We'll build a simple, circular spinner that rotates smoothly.

**Description of the Styling:**

This spinner utilizes a single element (a pseudo-element is also used for visual effect), styled with CSS to create a rotating effect.  The animation uses keyframes to define the rotation over a specified duration. We'll use borders to create the visual effect of a spinner.  The color can be easily customized.

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
  border: 5px solid #f3f3f3; /* Light grey border */
  border-top: 5px solid #3498db; /* Blue color for the spinning effect */
  border-radius: 50%;
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

* **`.spinner` class:** This class styles the main div element. `width` and `height` set the size.  The `border` property creates the circular shape.  `border-top` is set to a different color to create the spinning effect.  `border-radius: 50%;` makes it a perfect circle.  `animation: spin 1s linear infinite;` applies the animation.

* **`@keyframes spin`:** This defines the animation.  It smoothly rotates the element 360 degrees over 1 second (`1s`) repeatedly (`infinite`).  `linear` ensures a consistent speed.


**External References:**

* [MDN Web Docs on CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* [W3Schools on Keyframes](https://www.w3schools.com/css/css3_animations.asp)


This simple example demonstrates the power of CSS for creating dynamic visual effects without needing JavaScript. You can adjust the `width`, `height`, `border-width`, colors, and animation duration to customize the spinner to your needs.  For more advanced spinners, consider using multiple elements or more complex keyframe animations.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

