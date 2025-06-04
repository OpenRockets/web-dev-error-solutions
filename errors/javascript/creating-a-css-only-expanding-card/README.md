# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  No JavaScript is needed! This effect uses CSS transitions and transforms to smoothly expand a card when it's hovered over.

## Description of the Styling

This technique utilizes the `:hover` pseudo-class to trigger a transformation on the card.  When the mouse hovers over the card, it expands in size and optionally reveals hidden content.  The key is leveraging CSS transitions to create a smooth animation.  We'll also employ some basic box-shadow styling for visual appeal.

## Full Code

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
  padding: 20px;
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Added transition for smoother effect */
  overflow: hidden; /* Hide content that extends beyond card initially */
  width: 300px;
}

.card:hover {
  transform: scale(1.1);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  cursor: pointer;
}

.card-content {
  height: 100px; /* Initial height */
  overflow: hidden; /* Hide content beyond initial height */
  transition: height 0.3s ease-in-out; /* Added transition for smoother effect */
}

.card:hover .card-content {
  height: 200px; /* Height on hover */
}

.card h2 {
  margin-top: 0;
}

.card p{
  margin-bottom: 0;
}
</style>
</head>
<body>

<div class="card">
  <h2>Card Title</h2>
  <div class="card-content">
    <p>This is some example text that will expand when you hover over the card.</p>
    <p>More text here to demonstrate the expansion.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`transition` property:** This is crucial for the smooth animation.  We're transitioning the `transform` (for scaling) and `box-shadow` properties over 0.3 seconds with an ease-in-out timing function. We also transition the height of the `card-content` div.
* **`transform: scale(1.1)`:** This increases the size of the card on hover by 10%.
* **`box-shadow`:**  This adds a more pronounced shadow on hover to enhance the visual effect.
* **`:hover` pseudo-class:** This selector targets the element when the mouse cursor is over it.
* **`overflow: hidden`:** This ensures that content exceeding the initial height of the card is hidden before the hover effect.
* The `card-content` div's height transition allows for a smooth expansion of the content upon hover.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (various articles on CSS animations and effects):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

