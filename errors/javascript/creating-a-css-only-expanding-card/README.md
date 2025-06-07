# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card using only CSS.  No JavaScript is required! This effect is achieved using CSS transitions and the `:hover` pseudo-class to smoothly expand a card on mouseover.

**Description of the Styling:**

The card starts in a compact state. On hovering over the card, it expands horizontally, revealing more content.  This is achieved by transitioning the `width` property of the card container.  We also utilize a subtle box-shadow to enhance the visual effect.  The inner content is positioned using flexbox for easy centering.

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
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  padding: 10px;
  transition: width 0.3s ease-in-out; /* Smooth transition */
  width: 200px; /* Initial width */
  overflow: hidden; /* Hide content that overflows initially */
}

.card:hover {
  width: 400px; /* Expanded width on hover */
}

.card-content {
  display: flex;
  flex-direction: column;
  align-items: center; /* Center content vertically */
}

.card-title {
  font-size: 1.2em;
  margin-bottom: 10px;
}

.card-text {
  text-align: center;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This card expands on hover, showcasing a simple CSS-only animation.  No JavaScript required!</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card container.  `transition: width 0.3s ease-in-out;` is crucial for the smooth animation.  The `overflow: hidden;` prevents content from overflowing before the expansion.
* **`.card:hover`:** This targets the card when the mouse hovers over it, increasing the `width`.
* **`.card-content`:** Uses flexbox to easily center the content within the card.
* **`.card-title` and `.card-text`:** These classes simply style the title and text within the card.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **Flexbox:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

