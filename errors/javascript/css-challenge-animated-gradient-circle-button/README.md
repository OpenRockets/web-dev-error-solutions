# 🐞 CSS Challenge:  Animated Gradient Circle Button


This challenge focuses on creating a visually appealing and animated button using CSS.  The button will be a circle with a radial gradient that animates smoothly when hovered over. We'll use pure CSS3 for this, avoiding any JavaScript.


**Description of the Styling:**

The button will be a circle with a diameter of 150px.  The background will be a radial gradient transitioning from a dark blue (#222) to a light blue (#666). On hover, the gradient will shift, becoming brighter and more vibrant, creating an animation effect.  The text within the button will be white and centered.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Gradient Circle Button</title>
<style>
.button {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-image: radial-gradient(circle, #222, #666);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.2em;
  text-decoration: none; /*removes underline*/
  transition: background-image 0.5s ease; /* Smooth transition on hover */
}

.button:hover {
  background-image: radial-gradient(circle, #444, #999); /*Brighter gradient on hover*/
}
</style>
</head>
<body>

<a href="#" class="button">Click Me!</a>

</body>
</html>
```

**Explanation:**

* **`width` and `height`:** Set the button's dimensions to create a square.  `border-radius: 50%` transforms the square into a circle.
* **`background-image: radial-gradient(...)`:** This creates the radial gradient effect.  The `circle` keyword specifies a circular gradient. The colors are defined as a comma-separated list.
* **`display: flex`, `justify-content: center`, `align-items: center`:** These flexbox properties center the text within the button.
* **`transition: background-image 0.5s ease;`:** This line is crucial for the animation. It specifies that the `background-image` property should smoothly transition over 0.5 seconds using an "ease" timing function.
* **`:hover` pseudo-class:** This selector styles the button when the mouse hovers over it, changing the gradient to a brighter variation.

**Links to Resources to Learn More:**

* **CSS Gradients:** [MDN Web Docs - CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)
* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Flexbox:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

