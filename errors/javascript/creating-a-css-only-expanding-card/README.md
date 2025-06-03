# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This uses pure CSS3, without the need for JavaScript.

**Description of the Styling:**

The card is composed of two main elements: a container and an inner content section. The container has a fixed height initially.  The inner content section uses `max-height` to control its visible height, and a transition to smoothly animate its height change on hover.  We also add some visual styling for aesthetics.

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
  overflow: hidden; /* Hide overflowing content during transition */
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  transition: box-shadow 0.3s ease; /* Add a subtle shadow transition on hover */
}

.card:hover {
  box-shadow: 0 4px 8px rgba(0,0,0,0.2); /* Enhanced shadow on hover */
}


.card-container {
  width: 300px;
  height: 150px; /* Initial height */
  overflow: hidden; /* Hide the expanding content initially */
}

.card-content {
  padding: 15px;
  background-color: white;
  color: #333;
  transition: max-height 0.5s ease; /* Smooth height transition */
  max-height: 150px; /* Initial max height, matches container height */
}

.card:hover .card-content {
  max-height: 500px; /* Max height when expanded */
}


</style>
</head>
<body>

<div class="card">
  <div class="card-container">
    <div class="card-content">
      <h2>Card Title</h2>
      <p>This is some sample text for the card.  You can add as much content as you like.  The card will expand to fit.</p>
      <p>More text here to demonstrate expansion.</p>
      <p>Even more text!</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

*   **`overflow: hidden;` on `.card` and `.card-container`:** This prevents content from spilling outside the card boundaries during the transition.
*   **`transition: max-height 0.5s ease;` on `.card-content`:** This creates the smooth animation for the height change.
*   **`max-height` on `.card-content`:** This controls the visible height of the content, allowing us to expand it dynamically.
*   **`box-shadow` and `transition` on `.card`:** This is optional but provides additional visual feedback and makes the card look more polished.

**Links to Resources to Learn More:**

*   [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
*   [CSS-Tricks - Learn CSS](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

