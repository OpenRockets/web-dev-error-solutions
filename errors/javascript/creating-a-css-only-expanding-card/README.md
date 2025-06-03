# 🐞 Creating a CSS-only Expanding Card


This document details how to create an expanding card effect using only CSS.  This effect is achieved using CSS transitions and transforms to smoothly expand a card when it's hovered over.  No JavaScript is required.  We'll be using plain CSS3 for this example.


## Description of the Styling

The card starts with minimal dimensions. On hover, the card expands to reveal more content, while maintaining a smooth animation. The expansion is achieved by increasing the width and height of the card and subtly changing its shadow.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  padding: 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease; /* Smooth transition on hover */
  width: 200px;
  height: 150px;
  overflow: hidden; /* Prevent content overflow before expansion */
}

.card:hover {
  transform: scale(1.1); /* Expand the card on hover */
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Increased shadow on hover */
  cursor: pointer; /* Indicate interactivity */
}

.card-content {
  /* Style the inner content as needed */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Expanding Card</h2>
    <p>This is some sample text inside the expanding card.  You can add more content here as needed.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`transition: transform 0.3s ease, box-shadow 0.3s ease;`**: This line applies a smooth transition to the `transform` and `box-shadow` properties over 0.3 seconds, using an ease timing function. This creates the smooth animation.
* **`transform: scale(1.1);`**: This line scales the card up by 10% on hover, creating the expanding effect.
* **`box-shadow`**: The box-shadow is adjusted on hover to further enhance the visual effect of expansion.
* **`overflow: hidden;`**: This prevents content from spilling outside the card before expansion.  Without this, you might see content clipping.


## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box-Shadow:** [MDN Web Docs - CSS box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

