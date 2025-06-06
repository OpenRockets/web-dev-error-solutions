# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card using only CSS.  No JavaScript is required.  This effect is achieved using CSS transitions and the `:hover` pseudo-class.

**Description of the Styling:**

This example creates a simple card that expands horizontally when the user hovers over it.  The expansion is smooth thanks to CSS transitions.  We'll use a basic structure with a container, an image, and some text. The key is manipulating the `width` and `transform` properties with transitions.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  border: 1px solid #ccc;
  overflow: hidden; /* Important for hiding overflowing content during transition */
  transition: width 0.3s ease, transform 0.3s ease; /* Smooth transition */
}

.card img {
  width: 100%;
  height: auto;
  display: block; /* Remove extra space below image */
}

.card-content {
  padding: 10px;
}

.card:hover {
  width: 300px; /* Expand on hover */
  transform: translateX(-50px); /* Add a slight shift to make it visually appealing*/
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/200x150" alt="Card Image">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>Some descriptive text about the card goes here.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`**: This class styles the main card container.  `overflow: hidden` is crucial to prevent content from overflowing during the expansion. `transition` property smoothly animates changes in `width` and `transform` over 0.3 seconds using an "ease" timing function.
* **`.card img`**:  This styles the image within the card to ensure it scales appropriately. `display: block` removes the default space below inline elements.
* **`.card-content`**:  This styles the text content within the card.
* **`.card:hover`**: This styles the card when the user's mouse hovers over it. `width` is increased to 300px for expansion.  `transform: translateX(-50px)` shifts the card slightly to the left to prevent it from abruptly appearing to the right.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

