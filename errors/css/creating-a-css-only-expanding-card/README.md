# 🐞 Creating a CSS-only Expanding Card


This document details how to create an expanding card effect using only CSS.  This is a common CSS challenge that showcases the power of CSS transitions and transforms. We'll use plain CSS3 for this example, making it widely compatible.


## Description of the Styling

The effect creates a card that expands vertically when hovered over.  The expansion reveals hidden content below the initial card height.  The expansion is smooth and uses CSS transitions for a polished look.  The card utilizes simple styling for clarity, but can easily be customized with different colors, fonts, and backgrounds.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease; /* Smooth transition for height change */
  height: 100px; /* Initial height */
  width: 200px;
}

.card:hover {
  height: 250px; /* Height on hover */
}

.card-content {
  padding: 10px;
}

.hidden-content {
  display: none; /* Initially hidden */
}

.card:hover .hidden-content {
  display: block; /* Shown on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>Some initial card content.</p>
  </div>
  <div class="hidden-content">
    <p>This content is hidden until the card is hovered over.</p>
    <p>More hidden content here.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`:** This class styles the main card element. `overflow: hidden;` is crucial to prevent the expanding content from overflowing before the transition completes.  The `transition` property defines a smooth 0.3-second ease transition for the `height` property. The initial `height` is set to 100px.
* **`.card:hover`:** This selector styles the card when the mouse hovers over it.  The `height` is increased to 250px, triggering the transition.
* **`.card-content`:** This class styles the visible content within the card.
* **`.hidden-content`:** This class initially hides the extra content using `display: none;`.
* **`.card:hover .hidden-content`:**  This selector shows the hidden content when the card is hovered. `display: block;` makes the content visible.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:**  Search "CSS card hover effects" on [https://css-tricks.com/](https://css-tricks.com/) for many more examples and variations.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

