# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  No JavaScript is required. The effect involves a card that expands vertically when hovered over, revealing more content.  We'll use plain CSS for this example, focusing on transitions and pseudo-elements.


## Description of the Styling

The card uses a simple structure: a container holding the main content and a hidden section for the expanded content.  On hover, the height of the container is transitioned, smoothly revealing the initially hidden content.  We achieve this using CSS transitions and the `max-height` property.  We also add subtle styling for visual appeal.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for height change */
  max-height: 150px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Height on hover */
}

.card-content {
  padding: 15px;
}

.card-content h2 {
  margin-top: 0;
}

.card-expanded {
  padding: 15px;
  background-color: #e0e0e0;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some sample text.</p>
  </div>
  <div class="card-expanded">
    <p>This is the expanded content.  More details can go here.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`**: This class styles the overall card.  `overflow: hidden` prevents the expanded content from peeking out before the hover effect.  `transition` defines the smooth height change.  `max-height` limits the initial height.
* **`.card:hover`**: This selector targets the card when the mouse hovers over it. It increases the `max-height`, triggering the transition.
* **`.card-content`**: Styles the visible content.
* **`.card-expanded`**: Styles the content revealed on hover.



## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks on Transitions and Transforms:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)
* **Understanding `max-height`:** Search "CSS max-height" on your favorite search engine for numerous tutorials and explanations.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

