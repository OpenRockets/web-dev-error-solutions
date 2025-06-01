# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required. This effect involves a card that expands to reveal more content when clicked.  We'll utilize CSS transitions and transforms to achieve a smooth and elegant animation.


## Description of the Styling

The card will have a basic design, featuring a title and a short description initially visible.  Upon clicking, the card will expand vertically, revealing additional content that was initially hidden. The expansion will be accompanied by a subtle transition effect. We'll use a clean, minimalist aesthetic for clarity.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Prevents content from overflowing during expansion */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for height change */
  cursor: pointer; /* Indicate that the card is clickable */
  max-height: 150px; /* Initial height of the card */
}

.card.expanded {
  max-height: 400px; /* Height when expanded */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-description {
  margin-bottom: 10px;
}

.card-extra-content {
  display: none; /* Initially hide extra content */
}

.card.expanded .card-extra-content {
  display: block; /* Show extra content when expanded */
}
</style>
</head>
<body>

<div class="card" onclick="this.classList.toggle('expanded')">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-description">Click to expand and see more details.</p>
    <p class="card-extra-content">This is the extra content that appears when the card is expanded.  You can add as much content as you need here.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`max-height` and `transition`:** These properties are key to the expansion effect. `max-height` initially limits the card's height, and `transition` smoothly animates the height change when `max-height` is modified.
* **`.expanded` class:** This class is toggled using JavaScript's `classList.toggle()` method.  When added, it changes the `max-height` and displays the hidden content.
* **`overflow: hidden;`:** This is crucial to prevent content from spilling out during the transition.
* **`display: none;` and `display: block;`:**  These control the visibility of the extra content.


## Links to Resources to Learn More

* **MDN Web Docs (CSS Transitions):** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs (CSS Transforms):** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (Transitions and Animations):** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

