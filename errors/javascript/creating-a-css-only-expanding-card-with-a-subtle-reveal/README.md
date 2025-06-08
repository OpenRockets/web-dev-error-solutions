# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card effect using only CSS.  The card expands on hover, revealing hidden content with a smooth transition.  We'll leverage CSS transitions and transforms to achieve this effect without any JavaScript.

## Description of the Styling

The card will start in a collapsed state.  On hover, it will smoothly expand to reveal additional content positioned below the initial visible section. The expansion will be accompanied by a subtle scaling effect to enhance the visual appeal. We’ll also use a simple box-shadow to add depth.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 150px;
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: transform 0.3s ease-in-out, height 0.3s ease-in-out; /* Smooth transition */
}

.card:hover {
  transform: scale(1.05); /* Subtle scaling effect */
  height: 300px; /* Expand on hover */
}

.card-content {
  padding: 20px;
}

.card-content-hidden {
  height: 0; /* Initially hidden content */
  overflow: hidden; /* Hide overflow of hidden content */
  transition: height 0.3s ease-in-out; /* Smooth transition for height */
}

.card:hover .card-content-hidden {
    height: 150px; /* Reveal hidden content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>This is the visible content</h3>
    <p>Some text here...</p>
  </div>
  <div class="card-content card-content-hidden">
    <h3>This is the hidden content</h3>
    <p>This content will reveal on hover.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`**: This class styles the main card container. `overflow: hidden;` is crucial to prevent the hidden content from peeking out before the hover effect.  The `transition` property is used for smooth animations.
* **`.card:hover`**: This styles the card when the mouse hovers over it.  `transform: scale(1.05);` provides the subtle scaling effect.  `height: 300px;` increases the height of the card to reveal hidden content.
* **`.card-content`**:  Styles the visible content area.
* **`.card-content-hidden`**:  Styles the initially hidden content. `height: 0;` and `overflow: hidden;` ensure the content is hidden until the hover effect. The transition allows for smooth height changes.
* **`.card:hover .card-content-hidden`**: This targets the hidden content specifically when the card is hovered, smoothly changing its `height` to reveal the content.


## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (various articles on CSS effects):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

