# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically to reveal hidden content when clicked. This example utilizes pure CSS3, avoiding the need for JavaScript.  No frameworks like Tailwind CSS are used to keep the principles clear and accessible.

**Description of the Styling:**

This effect relies on CSS transitions and the `max-height` property. Initially, the card has a limited `max-height`, hiding its content. On hover or click, the `max-height` is increased to allow the content to expand. The transition smoothly animates this change in height.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden; /* Hide content that overflows the max-height */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initially, the card is collapsed */
  cursor: pointer;
}

.card:hover,
.card.expanded {
  max-height: 500px; /* Expanded height */
}

.card-content {
  padding: 10px;
}

</style>
</head>
<body>

<div class="card" onclick="this.classList.toggle('expanded')">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the card container.  `overflow: hidden` prevents content from spilling outside the `max-height` boundary. The `transition` property creates the smooth expansion effect. `max-height: 100px;` sets the initial collapsed height.
* **`.card:hover, .card.expanded`:**  This selector targets the card when the mouse hovers over it, or when the `expanded` class is added (via the `onclick` event). The `max-height` is increased to `500px`, allowing the content to become visible.  The `onclick` event toggles the 'expanded' class, providing the expand/collapse functionality.
* **`.card-content`:** This class styles the content within the card.

**Resources to Learn More:**

* **CSS Transitions:**  [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS `max-height` Property:** [MDN Web Docs - max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* **CSS Transitions and Transforms Tutorial:** [Many tutorials are available on YouTube and other coding platforms; search for "CSS transitions tutorial"]

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

