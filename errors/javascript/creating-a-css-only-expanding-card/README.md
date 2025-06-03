# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript is required. This effect is achieved using CSS transitions and the `:hover` pseudo-class to smoothly expand a card on mouse hover. We'll use plain CSS for this example, but the principles could easily be adapted for a CSS framework like Tailwind CSS.


**Description of the Styling:**

The card will start small and have a fixed width. On hover, the card's width will expand, revealing more content.  A smooth transition will enhance the visual appeal. We’ll also use some basic styling for aesthetics.

**Full Code:**

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
  padding: 20px;
  transition: width 0.3s ease-in-out; /* Smooth transition for width */
  width: 200px; /* Initial width */
  overflow: hidden; /* Prevents content overflow during transition */
}

.card:hover {
  width: 400px; /* Expanded width on hover */
}

.card-content {
  /*Optional styling for content within the card*/
  font-family: sans-serif;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Expanding Card</h2>
    <p>This is some example content within the expanding card.  You can add more text and elements here as needed. </p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card element.  `background-color`, `border`, `border-radius`, and `padding` provide basic styling.  Crucially, `transition: width 0.3s ease-in-out;` sets up a smooth transition for the `width` property over 0.3 seconds using an ease-in-out timing function. `width: 200px;` sets the initial width. `overflow: hidden;` ensures that content doesn't spill outside the card during the expansion.
* **`.card:hover`:** This styles the card when the mouse hovers over it. `width: 400px;` increases the width, triggering the transition defined in the `.card` class.
* **`.card-content`:** This optional class styles the content within the card.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS-Tricks (a great resource for CSS techniques):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

