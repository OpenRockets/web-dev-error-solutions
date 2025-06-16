# 🐞 CSS Challenge:  The Pulsating Button


This challenge involves creating a button that pulsates subtly, drawing attention to itself without being overly distracting. We'll achieve this effect using pure CSS3 animations.  No JavaScript needed!


**Description of the Styling:**

The button will be a simple, rounded rectangle with a gradient background.  The pulsating effect will be created by slightly changing the button's scale and opacity over time using a CSS animation.  The animation will be smooth and continuous, creating a gentle breathing effect.


**Full Code (CSS Only):**

```css
.pulsating-button {
  background-image: linear-gradient(to right, #4CAF50, #8BC34A); /* Green gradient */
  border: none;
  border-radius: 5px;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition: all 0.2s ease-in-out; /* Smooth transitions */
  animation: pulse 1.5s infinite ease-in-out; /* Pulsating animation */
}

.pulsating-button:hover {
  transform: scale(1.05); /* Slightly enlarge on hover */
  opacity: 0.9;          /* Slightly reduce opacity on hover */
}

@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.05);
    opacity: 0.9;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}
```

**HTML (for testing):**

```html
<button class="pulsating-button">Click Me!</button>
```

**Explanation:**

* **`linear-gradient`:** Creates a smooth color transition for the button background.
* **`border-radius`:** Rounds the button's corners.
* **`transition`:** Enables smooth transitions for hover effects.
* **`animation`:** Applies the `pulse` animation.
* **`@keyframes pulse`:** Defines the animation steps, smoothly scaling and changing the opacity of the button.
* **`:hover`:** Styles the button when the mouse hovers over it.  This adds an extra visual cue.


**Resources to Learn More:**

* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS-Tricks on Animations:** [https://css-tricks.com/almanac/properties/a/animation/](https://css-tricks.com/almanac/properties/a/animation/)
* **Understanding `transform` and `opacity`:** Search for these terms on MDN Web Docs for detailed explanations.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

