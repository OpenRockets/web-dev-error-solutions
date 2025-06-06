# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered, revealing hidden content.  This uses only CSS3, avoiding JavaScript for a lightweight and performant solution.

**Description of the Styling:**

The card uses a combination of transitions, pseudo-elements (`::before` and `::after`), and max-height to achieve the expanding effect.  The `::before` pseudo-element is used to create the visually appealing overlay that appears upon hover.  The max-height is initially set to a smaller value, limiting the card's height. Upon hover, the max-height is removed, allowing the card to expand to its full content height.  Transitions ensure a smooth animation.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 150px; /* Initial height */
  width: 300px;
}

.card:hover {
  max-height: 500px; /* Expanded height on hover */
}

.card-content {
  padding: 20px;
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Overlay on hover */
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
}

.card:hover::before {
  opacity: 1; /* Show overlay on hover */
}

.card h2 {
  margin-top: 0;
}

.card p {
    margin-bottom: 0;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Expanding Card</h2>
    <p>This is some example content within the card.  It will expand when you hover over the card.</p>
    <p>Additional content to demonstrate the expansion effect. Add as much text as you like!</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:**  The main container for the card.  `overflow: hidden` prevents content from overflowing before the expansion.  `max-height` initially restricts the card's height.  `transition` defines the smooth animation.
* **`.card:hover`:**  Styles applied when the card is hovered over.  `max-height` is removed to allow expansion.
* **`.card::before`:**  Creates a semi-transparent overlay that appears on hover.
* **`.card:hover::before`:**  Sets the overlay's opacity to 1 when hovering, making it visible.
* **`.card-content`:** Contains the actual content of the card.

**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks:** Search for "CSS-only card animations" on [https://css-tricks.com/](https://css-tricks.com/) for more advanced examples.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

