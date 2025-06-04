# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically to reveal additional content when hovered over.  No JavaScript is required.  This example uses plain CSS3, but the principles could be adapted to frameworks like Tailwind CSS.

**Description of the Styling:**

The core technique relies on CSS transitions and the `height` property.  The card initially has a fixed height, displaying only a summary. On hover, the height transitions to a larger value, revealing the hidden content.  We use `overflow: hidden` to initially hide the extra content and then let it smoothly transition in.  Some additional styling is added for visual appeal.

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
  overflow: hidden;
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  width: 300px;
  height: 150px; /* Initial height */
}

.card:hover {
  height: 300px; /* Height on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1em;
  line-height: 1.5;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p class="card-text">This is a short summary of the card content.  More details will be revealed upon hovering.</p>
    <p class="card-text" style="display: none;">This is the additional content that appears on hover.</p>
    <p class="card-text" style="display: none;">More hidden content here...</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the overall card.  `overflow: hidden` is crucial; it hides content that extends beyond the initial height.  The `transition` property enables a smooth animation.
* **`.card:hover`:**  This styles the card when the mouse hovers over it. The `height` property increases, revealing the hidden content.
* **`.card-content`, `.card-title`, `.card-text`:** These classes provide basic styling for the card's content.  The extra `card-text` paragraphs initially use `display: none;` to be hidden.

**Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (general CSS resource):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

