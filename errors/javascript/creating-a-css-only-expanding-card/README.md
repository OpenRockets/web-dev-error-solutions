# 🐞 Creating a CSS-Only Expanding Card


This document details the creation of an expanding card using only CSS.  No JavaScript is required! This effect uses CSS transitions and pseudo-elements to achieve a clean, smooth expansion when the card is hovered over.  We'll be leveraging pure CSS3 for this effect.

**Description of the Styling:**

The card starts in a compact state.  On hover, the card expands to reveal more content hidden initially.  The expansion utilizes a smooth transition to enhance the user experience.  A subtle shadow is added for depth and visual appeal.

**Full Code:**

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
  overflow: hidden; /* Hide content that overflows */
  transition: transform 0.3s ease-in-out; /* Smooth transition for transform */
  width: 300px;
}

.card:hover {
  transform: scale(1.05); /* Expand on hover */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
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
  transition: max-height 0.3s ease-in-out; /* Smooth transition for hidden content */
}

.card:hover .card-hidden {
  max-height: 200px; /* Height of the expanded content */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some sample text for the card.</p>
    <div class="card-hidden">
      <p>This content is initially hidden and will expand on hover.</p>
      <p>More hidden content here to demonstrate the expansion.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:**  This class styles the main card element.  `overflow: hidden;` prevents the hidden content from peeking out before expansion.  The `transition` property enables a smooth scaling effect.
* **`.card:hover`:** This styles the card when the mouse hovers over it. `transform: scale(1.05);` scales up the card slightly, creating the expansion effect. The box-shadow is intensified on hover.
* **`.card-content`:** Styles the content inside the card.
* **`.card-hidden`:** This is crucial.  `max-height: 0;` and `overflow: hidden;` initially hide the content. The `transition` property on `max-height` makes the reveal smooth.
* **`.card:hover .card-hidden`:** When hovering over the card, this targets the `.card-hidden` element and sets `max-height` to a value that shows the hidden content.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS Tutorials):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

