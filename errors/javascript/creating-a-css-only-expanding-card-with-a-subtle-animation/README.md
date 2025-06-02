# 🐞 Creating a CSS-only Expanding Card with a Subtle Animation


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required.  The effect involves a card that smoothly expands vertically when hovered over, revealing hidden content.  We'll use standard CSS3 properties for this effect, focusing on transitions and transforms.

## Description of the Styling

The card will have a basic design initially.  On hover, the card's height will increase to reveal additional content initially hidden using the `max-height` property. A subtle ease-in-out transition will smooth the expansion.  We'll also add a slight box-shadow change to enhance the effect.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: all 0.3s ease-in-out; /* Smooth transition for all properties */
  max-height: 100px; /* Initially hidden content */
}

.card:hover {
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
  max-height: 300px; /* Reveal full content on hover */
}

.card-content {
  padding: 15px;
}

.hidden-content {
  display: block;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some visible text.</p>
    <div class="hidden-content">
      <p>This is the hidden content that appears on hover.</p>
      <p>More hidden text here to demonstrate the expansion.</p>
    </div>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`:** This class styles the main card element.  `overflow: hidden;` prevents the hidden content from spilling out before the hover effect.  The `transition` property applies a smooth transition to all properties that change.  `max-height: 100px;` initially limits the card's height, hiding the extra content.

* **`.card:hover`:** This styles the card when the mouse hovers over it.  `max-height: 300px;` allows the card to expand to its full height, revealing the hidden content. The box-shadow is enhanced to provide visual feedback.

* **`.card-content`:** This class styles the content inside the card.

* **`.hidden-content`:**  This class is used to wrap the hidden text. While not directly affecting the animation, it helps semantically separate the content.


## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS Learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

