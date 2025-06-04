# 🐞 Creating a Pure CSS Loading Spinner


This document details how to create a smooth, visually appealing loading spinner using only CSS.  No JavaScript is required! We'll leverage CSS animations and transformations to achieve this effect. This example uses standard CSS, but could easily be adapted for a framework like Tailwind CSS by replacing the inline styles with Tailwind classes.

**Description of the Styling:**

The spinner is created using a single pseudo-element (`::before`) on a parent container.  We use CSS animations to rotate the element continuously, creating the spinning effect.  The `border-radius` property makes the element circular, and the different border colors create the spinner's distinct look.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Loading Spinner</title>
<style>
.loader {
  width: 60px;
  height: 60px;
  border: 5px solid #f3f3f3; /* Light gray border */
  border-top: 5px solid #3498db; /* Blue color */
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
<div class="loader"></div>

</body>
</html>
```

**Explanation:**

* **`.loader`:** This class styles the spinner container.  `width` and `height` set the size. The `border` property creates the spinner's visual components.  The top border is a different color to initiate the spinning effect. `border-radius` creates the circle.  `animation` applies the `spin` animation.
* **`@keyframes spin`:** This defines the animation.  It rotates the element 360 degrees over one second (`1s`), repeating infinitely (`infinite`).  `linear` ensures a constant rotation speed.

**Resources to Learn More:**

* **CSS Animations:**  MDN Web Docs provides comprehensive documentation on CSS animations: [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Pseudo-elements:** Learn more about pseudo-elements like `::before` and `::after`: [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **Tailwind CSS:** If you want to use Tailwind, explore its documentation on animations and utility classes: [https://tailwindcss.com/](https://tailwindcss.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

