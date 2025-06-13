# 🐞 CSS Challenge:  Animated Gradient Loading Button


This challenge involves creating an animated loading button using CSS gradients and keyframes. The button will smoothly transition from a static state to a loading state, displaying a spinning gradient circle within the button.  We'll use CSS3 for this implementation.

**Description of the Styling:**

The button will be rectangular with rounded corners. In its default state, it will have a solid background color.  Upon clicking (or simulating a loading state), a circular gradient will appear and animate within the button.  The gradient itself will be a vibrant color scheme.  The text within the button will change to indicate loading.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Gradient Loading Button</title>
<style>
.button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border-radius: 8px;
  transition: background-color 0.3s ease;
  position: relative;
  overflow: hidden; /* Hide the spinner initially */
}

.button:hover {
  background-color: #3e8e41; /* Darker green on hover */
}

.button.loading {
  background-color: transparent; /* Make background transparent during loading */
  cursor: wait; /* Indicate that the button is busy */
}

.button.loading::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 4px solid #4CAF50; /* Green border for spinner */
  border-color: #4CAF50 transparent #4CAF50 transparent; /* Gradient effect */
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% { transform: translate(-50%, -50%) rotate(0deg); }
  100% { transform: translate(-50%, -50%) rotate(360deg); }
}

.button span {
  transition: opacity 0.3s ease;
}

.button.loading span {
  opacity: 0; /* Fade out text during loading */
}


</style>
</head>
<body>

<button class="button" onclick="this.classList.toggle('loading');">
  <span>Click Me</span>
</button>

</body>
</html>
```

**Explanation:**

* **Base Button Styling:**  Sets up the initial button appearance (color, padding, etc.).
* **Hover Effect:** Changes the background color on hover.
* **Loading Class:**  This class is added to the button when clicked. It makes the background transparent and adds a loading cursor.
* **Pseudo-element `::before`:** This creates the spinning circle using a pseudo-element. The `border-color` property with transparent values creates the gradient effect.
* **`@keyframes spin`:** Defines the animation for the spinning circle.
* **Text Fade:** The `span` element containing the button text fades out during loading.

**Resources to Learn More:**

* **MDN Web Docs CSS Keyframes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Keyframes)
* **MDN Web Docs CSS Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks (General CSS Learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

