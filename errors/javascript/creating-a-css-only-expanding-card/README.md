# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically to reveal more content when hovered over.  This effect is achieved using purely CSS, making it lightweight and efficient.  No JavaScript is required.

**Description of the Styling:**

The styling utilizes CSS transitions and transforms to create the smooth expanding animation. The card's height is initially set to a smaller value.  On hover, the `height` is changed to a larger value revealing the hidden content.  The `transition` property smoothly animates this height change.  For visual enhancement, a subtle shadow and border-radius are added.

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
  transition: height 0.3s ease; /* Smooth transition for height change */
  height: 100px; /* Initial height */
  width: 300px;
}

.card:hover {
  height: 250px; /* Height on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
  font-size: 14px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is some example text that will be revealed when you hover over the card.  You can add as much text as you like, and the card will expand accordingly.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden;` prevents the hidden content from peeking out before the expansion.  `transition: height 0.3s ease;` defines the transition effect for the height change.  `height: 100px;` sets the initial height.
* **`.card:hover`:** This selector styles the card when the mouse hovers over it.  `height: 250px;` sets the height on hover, causing the expansion.
* **`.card-content`, `.card-title`, `.card-text`:** These classes style the internal content of the card for better readability and structure.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **More CSS Tricks:** [CSS-Tricks](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

