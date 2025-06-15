# 🐞 CSS Challenge:  Animated Rotating Square


This challenge focuses on creating a simple, yet visually appealing, rotating square using only CSS.  We'll achieve the rotation effect using CSS animations and transitions, demonstrating fundamental animation concepts.  This example utilizes plain CSS; adapting it to Tailwind CSS is straightforward, involving replacing the inline styles with appropriate Tailwind classes.

**Description of the Styling:**

The challenge involves creating a square that continuously rotates clockwise at a moderate speed.  The square will have a solid color background and a slight border for better visibility.  The animation should be smooth and seamless, looping indefinitely.


**Full Code (CSS):**

```css
.rotating-square {
  width: 100px;
  height: 100px;
  background-color: #3498db; /* A nice blue color */
  border: 2px solid #2980b9; /* Slightly darker blue border */
  animation: rotate 2s linear infinite; /* Animation properties */
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```

**Full Code (HTML -  to accompany the CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Rotating Square</title>
<style>
  /* CSS code from above goes here */
</style>
</head>
<body>
  <div class="rotating-square"></div>
</body>
</html>
```


**Explanation:**

* **`.rotating-square`:** This CSS class styles the square element.  `width` and `height` set the dimensions. `background-color` and `border` define the appearance.  `animation` applies the `rotate` animation.

* **`animation: rotate 2s linear infinite;`:** This is the core of the animation.
    * `rotate`: This is the name of the keyframes animation we define below.
    * `2s`:  Specifies the duration of one animation cycle (2 seconds).
    * `linear`:  Indicates a constant animation speed (no acceleration or deceleration).
    * `infinite`: Makes the animation loop continuously.


* **`@keyframes rotate`:** This block defines the animation itself.
    * `from`:  Specifies the starting state (0 degrees rotation).
    * `to`: Specifies the ending state (360 degrees rotation – a full circle).

**Adapting to Tailwind CSS:**

Tailwind CSS simplifies this by providing pre-defined classes.  You could achieve a similar result with:

```html
<div class="w-24 h-24 bg-blue-500 border-2 border-blue-700 animate-spin"></div>
```

This leverages Tailwind's width (`w-24`), height (`h-24`), background color (`bg-blue-500`), border (`border-2 border-blue-700`), and built-in spin animation (`animate-spin`).  Remember to include the Tailwind CSS library in your project.


**Resources to Learn More:**

* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

