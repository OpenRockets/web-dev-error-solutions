# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution for creating an expanding card effect, a common user interface element.  The effect involves a card that expands vertically when hovered over, revealing additional content.  We'll achieve this using pure CSS, without relying on JavaScript.


## Description of the Styling

The card is styled using a simple `div` element and several CSS properties.  Key techniques include:

* **Transitions:**  Smooth transitions are applied to the `height` property to create the expansion animation.
* **Overflow:** The `overflow: hidden;` property initially hides the extra content, revealing it only during expansion.
* **Height:**  The initial height is set to a smaller value, then dynamically changed on hover.
* **Pseudo-elements:** We use `::before` and `::after` pseudo-elements for stylistic touches (optional).

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden; /* Hide content beyond initial height */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  width: 300px;
  height: 100px; /* Initial height */
  position: relative; /* Needed for absolute positioning of pseudo-elements */
}

.card:hover {
  height: 250px; /* Expanded height on hover */
}

.card-content {
  padding: 10px;
}

.card::before { /* Optional: Add a subtle shadow */
  content: "";
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background-color: rgba(0, 0, 0, 0.1);
  z-index: -1;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some initial text content of the card. </p>
    <p>Additional content revealed on hover. </p>
  </div>
</div>

</body>
</html>
```

## Explanation

The core logic lies in the CSS rules for the `.card` class. The `transition` property makes the change in height smooth.  The `overflow: hidden;` ensures only the visible content is initially displayed. The `height` is set to a smaller value, and the `:hover` pseudo-class increases the height, revealing hidden content smoothly.  The optional pseudo-elements (`::before`) add a simple shadow effect.  This technique relies on the browser's ability to handle CSS transitions.


## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks - Transitions and Animations:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/) (Look for examples related to height transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

