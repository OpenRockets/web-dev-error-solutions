# 🐞 CSS Challenge:  Animated Gradient Text


This challenge involves creating text that smoothly transitions through a sequence of colors using CSS gradients and animations.  We'll achieve this using only CSS3, without resorting to JavaScript. The final effect will be a visually appealing and dynamic text element.

## Description of the Styling

The styling aims to create a text element ("OpenRockets") that displays a smooth, animated linear gradient.  The gradient will cycle through various shades of blue, green, and purple. The animation will be seamless, looping continuously.  We'll also add some basic styling for typography and positioning.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Gradient Text</title>
<style>
body {
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  font-family: sans-serif;
}

.animated-text {
  font-size: 3em;
  background-image: linear-gradient(to right, #4CAF50, #2196F3, #9C27B0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-animation 5s linear infinite;
}

@keyframes gradient-animation {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>
</head>
<body>
  <div class="animated-text">OpenRockets</div>
</body>
</html>
```

## Explanation

* **HTML Structure:** A simple `<div>` with the class `animated-text` holds the text "OpenRockets".
* **CSS Styling:**
    * `background-image: linear-gradient(...)`: This sets a linear gradient as the background of the text.  The colors used are shades of green, blue, and purple. You can easily customize these colors.
    * `-webkit-background-clip: text;`: This crucial property clips the background image to the text shape, making the gradient appear as the text color.
    * `-webkit-text-fill-color: transparent;`: This makes the actual text color transparent, allowing the gradient to show through.
    * `animation: gradient-animation 5s linear infinite;`: This applies the `gradient-animation` keyframes to the text, creating the animation effect.  `5s` sets the animation duration, `linear` defines a constant animation speed, and `infinite` makes it loop continuously.
* **`@keyframes gradient-animation`:** This section defines the animation.  The `background-position` property is manipulated to smoothly shift the gradient across the text.

## Links to Resources to Learn More

* **CSS Gradients:** [MDN Web Docs - CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS Backgrounds and Borders:** [MDN Web Docs - CSS Backgrounds and Borders](https://developer.mozilla.org/en-US/docs/Web/CSS/background)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

