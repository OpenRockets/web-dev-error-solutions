# 🐞 Creating a CSS-only Expanding Card with Hover Effect


This document details how to create an expanding card effect using only CSS.  No JavaScript is required! This effect involves a card that smoothly expands on hover, revealing additional content. We'll utilize CSS transitions and transforms to achieve this elegant animation.


## Description of the Styling

The card will be a simple rectangular element with a background image.  On hover, the card will increase in height, revealing text initially hidden by overflow.  A subtle shadow effect will be added for depth. We will use only standard CSS properties, not a CSS framework like Tailwind.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 200px;
  background-image: url('https://via.placeholder.com/300x200'); /* Replace with your image */
  background-size: cover;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: 400px; /* Expand on hover */
}

.card-content {
  padding: 20px;
  color: white;
  opacity: 0; /* Initially hidden */
  transition: opacity 0.3s ease-in-out; /* Smooth transition for opacity change */
}

.card:hover .card-content {
  opacity: 1; /* Show on hover */
}

.card-text {
    font-size: 16px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is some extra content revealed on hover.  You can add as much text as you like here.</p>
  </div>
</div>

</body>
</html>
```

Replace `https://via.placeholder.com/300x200` with a URL to your preferred background image.


## Explanation

* **`transition: height 0.3s ease-in-out;`**: This line creates a smooth transition for the `height` property over 0.3 seconds, using an `ease-in-out` timing function.
* **`overflow: hidden;`**: This prevents the content from overflowing the card before the hover effect.
* **`opacity: 0;`**: Initially hides the card content.
* **`transition: opacity 0.3s ease-in-out;`**: Creates a smooth transition for the `opacity` property when the card is hovered.
* **`.card:hover { height: 400px; }`**:  Increases the card's height on hover, revealing the hidden content.
* **`.card:hover .card-content { opacity: 1; }`**:  Makes the content visible on hover.


## Links to Resources to Learn More

* **MDN Web Docs CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **MDN Web Docs CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

