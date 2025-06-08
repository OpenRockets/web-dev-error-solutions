# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  This effect involves a card that expands to reveal more content when hovered over.  We'll be using plain CSS3 for this, avoiding any JavaScript or frameworks like Tailwind.

**Description of the Styling:**

The styling achieves the expanding effect using CSS transitions and transforms.  The card initially has a smaller height.  On hover, the height is increased, creating the expansion.  We'll use smooth transitions to make the effect visually appealing. A subtle box-shadow will enhance the card's 3D appearance.


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
  overflow: hidden; /* Hide content that overflows during transition */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  height: 100px; /* Initial height */
  width: 200px;
}

.card:hover {
  height: 250px; /* Height on hover */
}

.card-content {
  padding: 10px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
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
    <p class="card-text">This is some example text inside the card.  This text will become visible when the card expands on hover.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the main card container. `overflow: hidden` prevents content from spilling outside the card during the transition. `transition` specifies a smooth height change over 0.3 seconds. The initial `height` is set.
* **`.card:hover`:** This styles the card when the mouse hovers over it. The `height` is increased to create the expanding effect.
* **`.card-content`, `.card-title`, `.card-text`:** These classes style the inner content of the card for better readability and structure.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks - Introduction to CSS Transitions:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

