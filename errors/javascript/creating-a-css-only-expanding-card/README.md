# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  This effect is achieved without JavaScript, relying solely on CSS transitions and the `:hover` pseudo-class.  The card expands vertically when hovered over, revealing hidden content.  We'll be using standard CSS3 for this implementation.


**Description of the Styling:**

The core of this effect lies in the use of CSS transitions to smoothly animate the height of the card.  Initially, the card has a fixed height, displaying only a portion of its content.  On hover, the height transitions to a larger value, revealing the hidden content.  We use `overflow: hidden` to initially hide the extra content and then remove the constraint on hover. We'll also add some basic styling for visual appeal.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden; /* Initially hide extra content */
  transition: height 0.3s ease; /* Smooth transition for height */
  width: 300px;
}

.card-content {
  padding: 15px;
}

.card:hover {
  height: auto; /* Remove height constraint on hover */
  overflow: visible; /* Show the full content */
}

.card-content p {
  margin-bottom: 10px;
}
</style>
</head>
<body>

<div class="card" style="height: 100px;">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some sample text within the card.  This content is initially hidden and will expand when you hover over the card.</p>
    <p>More sample text to demonstrate the expanding effect.  Notice how smoothly the animation transitions.</p>
    <p>Even more content to make sure the expanding effect is clearly visible.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`**: This class styles the main card container.  `overflow: hidden` is crucial; it hides any content that extends beyond the initial height.  `transition: height 0.3s ease` defines a smooth transition for the height property over 0.3 seconds, using an ease timing function.  The initial height is set using inline styles (`style="height: 100px;"`) for demonstration purposes. You can adjust this height to control the initial visibility.

* **`.card:hover`**: This selector applies styles when the card is hovered over.  `height: auto;` allows the card to automatically adjust its height to fit the content. `overflow: visible;` ensures the entire content is visible.

* **`.card-content`**: This class styles the content within the card.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

