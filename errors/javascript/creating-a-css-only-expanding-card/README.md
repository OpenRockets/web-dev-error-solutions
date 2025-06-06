# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  No JavaScript is required.  The effect uses CSS transitions and transforms to smoothly expand a card when hovered over, revealing hidden content.  We'll be using standard CSS3 for this example.


**Description of the Styling:**

The styling employs a container div for the card.  Inside, there's a "front" section displaying the main content visible initially, and a "back" section containing the expanded content, initially hidden.  We use `transform: rotateY()` and transitions to create the flipping animation.  The hover effect triggers the transformation, revealing the back of the card.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  perspective: 1000px; /* Necessary for 3D transformations */
  margin: 20px;
}

.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.8s; /* Smooth transition for the flip */
  transform-style: preserve-3d; /* Enables 3D transformations on child elements */
}

.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Prevents the back from being visible during transition */
}

.card-front {
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #333;
  font-size: 1.2em;
}

.card-back {
  background-color: #ddd;
  transform: rotateY(180deg); /* Initially rotated to the back */
  display: flex;
  justify-content: center;
  align-items: center;
  color: #333;
  font-size: 1em;
}

.card:hover .card-inner {
  transform: rotateY(180deg); /* Flip on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-inner">
    <div class="card-front">Front</div>
    <div class="card-back">Back: This is the expanded content!</div>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`perspective`**: This property creates the 3D space for the flip effect.
* **`transform-style: preserve-3d`**: This ensures that child elements are also transformed in 3D space.
* **`backface-visibility: hidden`**: This prevents the back of the card from being visible before the flip.
* **`transition`**: This property provides a smooth animation for the `transform` property.
* **`transform: rotateY()`**: This rotates the card around the Y-axis to create the flip effect.
* **The hover event**: This triggers the rotation, revealing the hidden content.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks - 3D Transforms:** [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

