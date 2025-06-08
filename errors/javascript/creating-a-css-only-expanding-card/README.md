# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript is required! This effect utilizes CSS transitions and transforms to create a smooth and visually appealing animation when a card is hovered over.  We'll be using plain CSS3 for this example, making it highly compatible across browsers.

## Description of the Styling

The card starts in a compact state.  Upon hovering, it smoothly expands horizontally, revealing more content.  This is achieved using CSS transitions on `transform: scaleX()` and `box-shadow`.  A subtle box shadow is added to enhance the three-dimensional effect. The expansion is confined to the horizontal axis to maintain a clean and focused animation.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 100px;
  background-color: #f0f0f0;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
  overflow: hidden; /* Hide content that overflows during expansion */
}

.card:hover {
  transform: scaleX(1.2); /* Expand horizontally */
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2); /* Increased shadow on hover */
}

.card-content {
  padding: 10px;
  color: #333;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    This is some sample text inside the card.  It will expand horizontally on hover.
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`**: This class styles the base card.  `transition` property is key; it defines smooth transitions for `transform` and `box-shadow` properties over 0.3 seconds.
* **`.card:hover`**: This selector targets the card when the mouse hovers over it.  `transform: scaleX(1.2)` expands the card horizontally by 20% (`1.2 * original width`).  The `box-shadow` is increased to provide a more pronounced visual effect.
* **`.card-content`**: This class styles the content within the card.
* **`overflow: hidden;`**: This is crucial for preventing content from overflowing during the expansion, keeping the effect clean.


## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Tricks (website):** [https://css-tricks.com/](https://css-tricks.com/) - A great resource for CSS tutorials and techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

