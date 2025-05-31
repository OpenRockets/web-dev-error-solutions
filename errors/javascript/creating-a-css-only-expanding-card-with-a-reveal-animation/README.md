# 🐞 Creating a CSS-Only Expanding Card with a Reveal Animation


This document details how to create an expanding card effect using only CSS.  The card expands to reveal additional content on hover, providing a clean and engaging user experience without relying on JavaScript. This example uses pure CSS3, avoiding any external libraries like Tailwind CSS.


**Description of the Styling:**

This technique uses CSS transitions and transforms to animate the height and opacity of a hidden element within a card. On hover, the hidden element smoothly expands, revealing its content.  We use a clever combination of `max-height` and transitions to achieve this smooth expansion effect.  The card itself has a subtle shadow for visual appeal.


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
  overflow: hidden; /* Prevents content from overflowing */
  transition: box-shadow 0.3s ease; /* Smooth shadow transition on hover */
}

.card:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
}

.card-content {
  padding: 20px;
}

.card-reveal {
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.5s ease-out; /* Smooth height transition */
  opacity: 0;
  transition: opacity 0.5s ease-out;
}

.card:hover .card-reveal {
  max-height: 200px; /* Expanded height on hover */
  opacity: 1;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some initial card content.</p>
  </div>
  <div class="card-reveal">
    <p>This is the hidden content that will be revealed on hover.</p>
    <p>Add more content here as needed.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:**  Styles the main card container, including background color, border radius, box shadow, and overflow hidden to keep the expanding content contained within.
* **`.card-content`:** Styles the visible content of the card.
* **`.card-reveal`:**  This is the crucial part.  `max-height: 0;` initially hides the content. The `transition: max-height 0.5s ease-out;` ensures a smooth animation when the `max-height` changes. The `opacity` transition provides a fading-in effect.
* **`.card:hover .card-reveal`:** This selector targets the `.card-reveal` element only when the `.card` is hovered.  `max-height: 200px;` sets the expanded height, and `opacity:1` makes it fully visible.


**External References:**

* [MDN Web Docs on CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [Understanding CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

