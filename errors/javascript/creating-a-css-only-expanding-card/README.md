# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically to reveal additional content when hovered over, providing a clean and engaging user experience without relying on JavaScript. This example uses only CSS3 properties.


**Description of the Styling:**

This effect leverages CSS transitions and the `max-height` property.  The card initially has a small `max-height`, limiting its visible content. On hover, the `max-height` is changed to a larger value (or `auto` to allow the content to naturally expand), revealing the hidden content. Smooth transitions ensure a polished animation.


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
  overflow: hidden; /* Prevents content overflow before expansion */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
  width: 300px;
}

.card:hover {
  max-height: 400px; /* Expanded height */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p>This is some example text for the expanding card.  You can add as much content as you need. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:**  This class styles the main card container.  `overflow: hidden` is crucial to prevent the content from overflowing before expansion.  The `transition` property defines the animation for the `max-height` change.  The initial `max-height` is set to a small value.
* **`.card:hover`:** This selector targets the card when the mouse hovers over it. The `max-height` is increased to reveal the full content.  You can adjust the value to control the expanded height, or use `max-height: auto;` to let the content determine the height.
* **`.card-content` and `.card-title`:** These classes are used for styling the content inside the card for better readability and structure.


**Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks on Transitions:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

