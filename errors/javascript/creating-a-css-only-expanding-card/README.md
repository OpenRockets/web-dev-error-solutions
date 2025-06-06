# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card using only CSS.  No JavaScript is required. The effect involves a card that smoothly expands vertically to reveal more content when hovered over.  We'll utilize pure CSS techniques to achieve this.


## Description of the Styling

The card will have a simple design: a rectangular container with a title and some hidden content. On hover, the hidden content will smoothly slide down, revealing itself.  The transition will be smooth and visually appealing.  We will use CSS transitions and the `max-height` property to control the expansion.

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
  overflow: hidden; /* Hide content outside of card */
  transition: max-height 0.5s ease-out; /* Smooth transition */
  max-height: 100px; /* Initially, content is collapsed */
}

.card:hover {
  max-height: 300px; /* Expand on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
}

.card-text {
    font-size: 14px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is some example text for our expanding card.  It demonstrates how you can use CSS alone to create interactive elements.</p>
    <p class="card-text">More text here to show the expansion in action.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`**: This class styles the main card container.  `overflow: hidden;` ensures that content outside the specified `max-height` is hidden. The `transition` property sets up the smooth animation for the `max-height` change.  The initial `max-height` is set to a small value to keep the content collapsed.
* **`.card:hover`**: This selector styles the card when the mouse hovers over it.  The `max-height` is increased to reveal the hidden content.
* **`.card-content`, `.card-title`, `.card-text`**: These classes are used for basic styling of the content within the card. You can customize these to match your design preferences.

The magic happens with the combination of `max-height`, `transition`, and the `:hover` pseudo-class. The transition smoothly animates the change in `max-height` from the initial collapsed state to the expanded state when the mouse hovers over the card.

## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

