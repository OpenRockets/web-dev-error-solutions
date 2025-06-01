# 🐞 Creating a Pure CSS Loading Spinner


This document details the creation of a loading spinner using only CSS.  No JavaScript is required. This utilizes CSS animations and keyframes to achieve a smooth, visually appealing loading effect.


## Description of the Styling

This spinner consists of a single element styled with CSS to create the illusion of rotation.  We achieve this using the `@keyframes` rule to define the animation and the `animation` property to apply it to the element.  The spinner uses a radial gradient for a visually appealing effect, but a solid color would also work.  The design is simple and adaptable; you can easily change the colors, size, and number of elements to customize the spinner to your needs.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Loading Spinner</title>
<style>
.loader {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  border: 10px solid #f3f3f3; /* Light grey */
  border-top: 10px solid #3498db; /* Blue */
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
</head>
<body>

<h1>Loading...</h1>
<div class="loader"></div>

</body>
</html>
```


## Explanation

* **`.loader`:** This class styles the spinning element.  `width` and `height` set the size, `border-radius` creates the circular shape, and the `border` properties define the thickness and colors of the spinner.  The `border-top` color is different to create the rotating effect.  `animation` applies the `spin` animation.

* **`@keyframes spin`:** This defines the animation named "spin".  It smoothly rotates the element 360 degrees over 2 seconds (`2s`), repeating infinitely (`infinite`).  `linear` ensures a constant rotation speed.

## Links to Resources to Learn More

* **CSS Animations:**  [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Keyframes:** [MDN Web Docs - @keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
* **Radial Gradients:** [MDN Web Docs - Radial Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

