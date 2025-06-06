# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required.  This effect involves a card that expands to reveal more content when hovered over.  We'll use CSS transitions and transforms to achieve a smooth and visually appealing animation.

**Description of the Styling:**

The card uses a simple layout with a container holding the front (summary) and back (detailed) content.  The front is visible by default.  On hover, we use CSS transitions to smoothly change the transform property, effectively "rotating" the back content into view while hiding the front.  This creates a clean and intuitive expanding card interaction.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  perspective: 1000px; /* For 3D effect */
  width: 300px;
  height: 200px;
}

.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s; /* Smooth transition */
}

.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Prevent back content from showing through */
}

.card-front {
  background-color: #4CAF50;
  color: white;
}

.card-back {
  background-color: #2196F3;
  color: white;
  transform: rotateY(180deg); /* Initially hidden */
}

.card:hover .card-inner {
  transform: rotateY(-180deg); /* Reveal back content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-inner">
    <div class="card-front">
      <h2>Card Front</h2>
      <p>This is the front of the card.</p>
    </div>
    <div class="card-back">
      <h2>Card Back</h2>
      <p>This is the expanded content of the card.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:**  This property creates a 3D space for the rotation effect.
* **`transition`:** This smoothly animates the `transform` property change.
* **`transform`:**  This property rotates the `card-inner` element.  `rotateY` rotates around the Y-axis.
* **`backface-visibility: hidden;`:** This prevents the back of the card from being visible when it's facing away.
* **`.card:hover .card-inner`:** This selector targets the `.card-inner` element when the `.card` element is hovered over.

**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (various articles on CSS animations and effects):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

