# 🐞 Creating a CSS-only Expanding Card


This document details how to create an expanding card effect using only CSS.  This effect involves a card that smoothly expands to reveal more content when hovered over.  We'll be using pure CSS3 for this, avoiding JavaScript for a lightweight and performant solution.


**Description of the Styling:**

The styling utilizes CSS transitions and transforms to create the expanding effect. The card initially has a smaller height. On hover, the height is increased, and a smooth transition ensures a visually appealing animation.  We'll also add some subtle shadows for depth and visual appeal.


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
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
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

.card-content p {
    margin: 0;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some example text inside the card.  It will expand on hover.</p>
    <p>More text to fill the expanded card.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden;` prevents content from spilling outside the card's boundaries.  `transition: height 0.3s ease-in-out;` is crucial; it defines the transition effect for the height property, making the expansion smooth.  The initial height is set to 150px.
* **`.card:hover`:** This selector targets the card when the mouse hovers over it.  The `height` is increased to 300px, triggering the transition defined in the `.card` class.
* **`.card-content`:** This class styles the inner content of the card, adding padding for visual spacing.


**Links to Resources to Learn More:**

* **CSS Transitions:**  [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box Model:** [MDN Web Docs - CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Box_model)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

