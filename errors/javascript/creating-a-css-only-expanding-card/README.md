# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands to reveal more content when hovered over, providing a clean and engaging user experience without JavaScript. This example uses pure CSS3, but similar effects could be achieved with frameworks like Tailwind CSS.

**Description of the Styling:**

This effect relies on CSS transitions and the `:hover` pseudo-class.  The card starts with a smaller height. On hover, the height transitions to a larger value, revealing the hidden content.  We use a smooth transition for a polished look.  We also add some subtle shadow effects to enhance the visual appeal.


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
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  height: 100px; /* Initial height */
}

.card:hover {
  height: 250px; /* Height on hover */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Increased shadow on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
    line-height: 1.6;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is a sample text within the expanding card.  This text is initially hidden and only revealed when the card is hovered over. You can add as much text as needed.  This demonstrates the use of CSS transitions to create an engaging user interface element.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card container. `overflow: hidden;` prevents the hidden content from spilling out before the transition. The `transition` property specifies that the `height` should smoothly change over 0.3 seconds using an ease-in-out timing function.
* **`.card:hover`:** This styles the card when the mouse hovers over it. The `height` is increased, revealing the hidden content. The box-shadow is also intensified to provide visual feedback.
* **`.card-content`, `.card-title`, `.card-text`:** These classes style the inner content of the card for better readability and organization.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **Understanding Box-Shadow:** [CSS-Tricks - Box Shadow](https://css-tricks.com/almanac/properties/b/box-shadow/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

