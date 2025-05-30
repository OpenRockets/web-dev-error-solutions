# 🐞 Creating a CSS-only Expanding Card with a Smooth Transition


This document details how to create an expanding card effect using only CSS.  This technique leverages CSS transitions and transforms to achieve a visually appealing and interactive experience without needing JavaScript.  We'll be using pure CSS3 for this example.

**Description of the Styling:**

This styling creates a card that expands vertically when hovered over.  The expansion is smooth due to the CSS transition property. The card's content smoothly slides down revealing more information.  The effect is subtle yet impactful, enhancing user engagement.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 15px;
  margin-bottom: 20px;
  overflow: hidden; /* Hide content that overflows initially */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card-content {
  height: 100px; /* Initial height of the card content */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  overflow: hidden; /* Hide content that overflows initially */
}

.card:hover .card-content {
  height: auto; /* Expand to full content height on hover */
}

.card h2 {
  margin-top: 0;
}
</style>
</head>
<body>

<div class="card">
  <h2>Card Title</h2>
  <div class="card-content">
    <p>This is some example text for the expanding card.  You can add as much content as you like and it will smoothly expand to accommodate it on hover.</p>
    <p>More example text to demonstrate the expanding effect.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the overall card container.  `overflow: hidden;` is crucial; it initially hides any content exceeding the initial height.  The `transition` property defines the smooth animation for the height change.

* **`.card-content`:** This class styles the inner content of the card. The `height: 100px;` sets the initial, collapsed height.  The `transition` is mirrored from the `.card` class for consistent animation.  `overflow: hidden;` prevents content from overflowing before expansion.

* **`.card:hover .card-content`:** This is the key part.  The `:hover` pseudo-class targets the card when the mouse is over it.  Setting `height: auto;` removes the height constraint, allowing the content to expand to its natural size.

* **`transition: height 0.3s ease-in-out;`:** This property smoothly animates the changes in height over 0.3 seconds, using an ease-in-out timing function for a natural feel.


**External References:**

* [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) - MDN documentation on CSS transitions.
* [CSS :hover pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover) - MDN documentation on the `:hover` pseudo-class.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

