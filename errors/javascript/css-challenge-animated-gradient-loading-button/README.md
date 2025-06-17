# 🐞 CSS Challenge:  Animated Gradient Loading Button


This challenge focuses on creating a visually appealing loading button using CSS animations and gradients. The button will smoothly transition from a static state to an animated loading state, showcasing a gradient effect and a spinning indicator. We'll use plain CSS for this example.


**Description of the Styling:**

The button will initially display solid text.  On click, it will transition to a loading state, where the text is hidden, and a spinning circular gradient is displayed.  The gradient will use a vibrant color scheme.  The animation will be smooth and visually engaging.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Gradient Loading Button</title>
<style>
.button {
  display: inline-block;
  padding: 15px 30px;
  border-radius: 5px;
  background-color: linear-gradient(to right, #4CAF50, #8BC34A);
  color: white;
  text-decoration: none;
  transition: background-color 0.3s ease;
  cursor: pointer;
}

.button:hover {
  background-color: linear-gradient(to right, #388E8E, #008080);
}

.button.loading {
  background-color: transparent; /* Remove background for loading state */
  cursor: wait; /* Indicate loading */
  animation: spinner 1s linear infinite;
}

.button.loading span {
    display: none;
}

.button.loading::before {
  content: '';
  display: block;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  border: 3px solid #f00;
  border-color: #4CAF50 transparent #4CAF50 transparent; /* Gradient border */
  animation: rotate 1s linear infinite;
}


@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes spinner {
  0% { transform: scale(1); }
  50% { transform: scale(1.1); }
  100% { transform: scale(1); }
}

</style>
</head>
<body>

<a href="#" class="button" id="myButton">Click Me</a>

<script>
const button = document.getElementById('myButton');
button.addEventListener('click', () => {
  button.classList.add('loading');
  setTimeout(() => {
    button.classList.remove('loading');
    // Add any further actions here, e.g., after the simulated load is complete.  
  }, 2000); // Simulate a 2-second loading time.
});
</script>

</body>
</html>
```


**Explanation:**

1. **Base Styling:**  The base `.button` class sets up the button's appearance (padding, background, color, etc.).  A hover effect is included.

2. **Loading State:** The `.button.loading` class styles the button during the loading animation. It makes the text disappear, adds a `cursor:wait` style,  and adds the spinning element using the `::before` pseudo-element.  The spinner is created using a rotating circular gradient.

3. **Keyframes:** The `@keyframes` rules define the animations for the spinner (`rotate`) and a subtle scaling animation for the button itself (`spinner`).

4. **JavaScript:**  A small JavaScript snippet adds the `loading` class to the button on click, simulating a loading process. After a 2-second delay (adjustable), the `loading` class is removed.


**Links to Resources to Learn More:**

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Gradients:** [MDN Web Docs - CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* **CSS Pseudo-elements:** [MDN Web Docs - CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

