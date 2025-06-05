# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect, where clicking a card reveals more content smoothly.  We'll use plain CSS3 for this, avoiding JavaScript for a lightweight and performant solution.


## Description of the Styling

The card starts in a compact state, showing only a title and a small image.  Upon clicking, the card expands vertically to reveal hidden content (in this case, some placeholder text).  The transition is smooth thanks to CSS transitions.  The styling uses simple box-shadow and border-radius for visual appeal.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide the content until expanded */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
  cursor: pointer;
}

.card:hover {
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2); /*Enhanced hover effect*/
}

.card.expanded {
  max-height: 400px; /* Expanded height */
}

.card-content {
  padding: 15px;
}

.card-image {
  width: 100%;
  height: auto;
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
}

.card-text {
  font-size: 14px;
  line-height: 1.6;
}
</style>
</head>
<body>

<div class="card" onclick="this.classList.toggle('expanded')">
  <img class="card-image" src="https://via.placeholder.com/300x150" alt="Card Image">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-text">This is some placeholder text for the card content.  This will be revealed when the card is expanded. Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Nulla nec purus feugiat, molestie ipsum et, consequat nibh.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`max-height` and `transition`:** These are the key properties for the expanding effect.  `max-height` initially restricts the card's height, and `transition` makes the change in `max-height` smooth.
* **`expanded` class:** This class is toggled using JavaScript's `classList.toggle()` method on click.  It changes the `max-height` to reveal the hidden content.
* **`overflow: hidden`:** This ensures that the content outside the initial `max-height` is hidden until the card expands.
* **`box-shadow`, `border-radius`:** These are used for basic styling and visual appeal.

The JavaScript part is minimal, relying solely on the `classList.toggle()` method to add or remove the 'expanded' class which directly manipulates the CSS.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS max-height:** [https://developer.mozilla.org/en-US/docs/Web/CSS/max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

