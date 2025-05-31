# 🐞 Creating a Pure CSS Loading Spinner with Keyframes


This document details the creation of a visually appealing loading spinner using only CSS3 animations and keyframes. No images or JavaScript are required.  This technique is useful for lightweight loading indicators, particularly beneficial in projects aiming for minimal external dependencies.

**Description of the Styling:**

This spinner uses a pseudo-element (`::before`) to create a rotating circle.  The animation is achieved through CSS keyframes that control the rotation and opacity of the pseudo-element, creating a smooth and visually engaging loading effect. The spinner's color and size are easily customizable through CSS variables.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Loading Spinner</title>
<style>
  :root {
    --spinner-color: #007bff; /* Customizable spinner color */
    --spinner-size: 50px;    /* Customizable spinner size */
  }

  .loader {
    width: var(--spinner-size);
    height: var(--spinner-size);
    border-radius: 50%;
    border: 4px solid #f3f3f3; /* Light gray border */
    border-top: 4px solid var(--spinner-color); /* Colored top border */
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

* **`:root`:** Defines CSS variables for easy customization of the spinner's color (`--spinner-color`) and size (`--spinner-size`).  This makes it easy to change the appearance without modifying the core structure.

* **`.loader`:** Styles the main container element. `border-radius: 50%` creates the circular shape.  The borders create the visual effect of a rotating circle. The `border-top` is given the color defined by the CSS variable.  `animation: spin 1s linear infinite;` applies the animation defined in the `@keyframes` rule.

* **`@keyframes spin`:** Defines the animation named "spin". It smoothly rotates the element 360 degrees over one second (`1s`), repeating infinitely (`infinite`). The `linear` keyword ensures a constant speed of rotation.


**External References:**

* [MDN Web Docs on CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* [MDN Web Docs on CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)
* [Various CSS Spinner Examples](https://cssload.net/)  (This site provides numerous examples of CSS spinners for inspiration)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

