# 🐞 Creating a CSS-only Expanding Card


This document details how to create an expanding card effect using only CSS.  This is a common challenge showcasing CSS transitions and transforms to improve user experience and add visual appeal to web interfaces.  No JavaScript is required.

**Description of the Styling:**

This design implements a card that expands vertically when hovered over.  The expansion is smooth thanks to CSS transitions.  The card uses a subtle shadow to provide depth and visual separation. The text within the card remains static while the card itself expands to reveal more content that would normally be hidden.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Prevents content from overflowing during expansion */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for height change */
  max-height: 100px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Expanded height on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p>This is some example text that will be hidden initially and revealed on hover.</p>
    <p>More text to demonstrate the expansion effect.</p>
    <p>Even more text to make sure the expansion is noticeable.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the card itself. `overflow: hidden;` is crucial to prevent the content from overflowing before the expansion.  The `transition` property defines the smooth animation of the `max-height` property.  `max-height` initially limits the card's height.
* **`.card:hover`:** This selector applies styles when the mouse hovers over the card. The `max-height` is increased to reveal the full content.
* **`.card-content` and `.card-title`:** These classes style the content within the card for better readability and organization.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **Understanding Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

