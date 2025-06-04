# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect, where clicking a card reveals more information.  We'll use only CSS3, no JavaScript required.  This provides a smooth, performant, and accessible solution.


## Description of the Styling

This effect uses CSS transitions and the `:target` pseudo-class to achieve the expansion.  The card starts in a collapsed state. When the user clicks the card's title (a link), the URL hash changes, triggering the `:target` selector to expand the card, revealing hidden content.  A subtle animation makes the transition smooth and user-friendly.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
body {
  font-family: sans-serif;
}

.card {
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden;
  margin: 20px;
  transition: max-height 0.5s ease-in-out; /* Smooth transition for height change */
}

.card-header {
  background-color: #f0f0f0;
  padding: 15px;
  cursor: pointer;
}

.card-content {
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.5s ease-in-out; /* Smooth transition for height change */
}

.card:target .card-content {
  max-height: 200px; /* Expanded height */
}

.card a {
    text-decoration: none;
    color: black;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">
    <a href="#card1">Card Title 1</a>
  </div>
  <div class="card-content" id="card1">
    <p>This is the content of the first card.  You can add as much text as you want here.  This is a test to see how the expansion works.</p>
  </div>
</div>

<div class="card">
  <div class="card-header">
    <a href="#card2">Card Title 2</a>
  </div>
  <div class="card-content" id="card2">
    <p>This is the content of the second card.  This is another example of expanding content.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`:** This class styles the overall card container.  `overflow: hidden;` is crucial to hide the content initially.
* **`.card-header`:** Styles the clickable header.
* **`.card-content`:**  Contains the expandable content.  `max-height: 0;` hides it by default.  The transition property ensures smooth animation.
* **`.card:target .card-content`:** This is the key.  The `:target` pseudo-class selects the `.card` element that is currently targeted by the URL hash (e.g., `#card1`).  When the link is clicked, the `max-height` is changed to reveal the content.
* **Transitions:** The `transition` property on both `.card` and `.card-content` ensures that the height changes smoothly over 0.5 seconds.


## Links to Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on the `:target` pseudo-class:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* **CSS-Tricks (General CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

