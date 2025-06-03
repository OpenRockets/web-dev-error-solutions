# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript is required! This effect involves a card that expands to reveal more content when hovered over. We'll use pure CSS to achieve this elegant animation.


## Description of the Styling

The styling uses a combination of CSS transitions, transforms, and the `:hover` pseudo-class.  The card starts in a collapsed state. On hover, the card expands smoothly, revealing hidden content. We'll use a simple box-shadow to add some depth and visual appeal.


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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transitions */
  width: 300px;
}

.card:hover {
  transform: scale(1.05); /* Expand on hover */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Increased shadow on hover */
}

.card-content {
  padding: 20px;
}

.card-content h2 {
  margin-top: 0;
}

.card-hidden {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition for height */
}

.card:hover .card-hidden {
  max-height: 200px; /* Reveal hidden content */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>Some initial card content.</p>
    <div class="card-hidden">
      <p>This content is hidden until the card is hovered over.</p>
      <p>More hidden content here!</p>
    </div>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`**: This class styles the main card container.  `overflow: hidden` prevents the hidden content from overflowing before expansion.  `transition` property smoothly animates the `transform` (scale) and `box-shadow`.

* **`.card:hover`**: This applies styles when the card is hovered over.  `transform: scale(1.05)` slightly increases the card's size, creating the expansion effect.  The `box-shadow` is also intensified.

* **`.card-content`**: Styles the visible content of the card.

* **`.card-hidden`**: This class initially hides the extra content.  `max-height: 0` and `overflow: hidden` ensures it's invisible.  The `transition` for `max-height` smoothly animates the height change on hover.

* **`.card:hover .card-hidden`**: On hover, `max-height` is set to a value (e.g., `200px`), revealing the hidden content.

## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (A great resource for CSS tutorials and techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

