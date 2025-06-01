# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The card expands smoothly when hovered over, revealing additional content. We'll leverage CSS transitions and transforms for a polished effect. No JavaScript required!

**Description of the Styling:**

The card consists of a main container that holds the front and back content.  The front displays a summary, while the back expands to reveal more detailed information. The expansion utilizes a CSS transition on `transform: scale()` and `opacity` to create a smooth, visually appealing effect.  The design uses a subtle shadow to enhance depth.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 200px;
  perspective: 1000px; /* Enables 3D transforms */
  border-radius: 8px;
  overflow: hidden; /* Hides overflowing content during transition */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Prevents flickering during transition */
  transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out; /* Smooth transition */
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 8px;
}

.card-front {
  background-color: #f0f0f0;
  color: #333;
}

.card-back {
  background-color: #ddd;
  color: #333;
  transform: rotateY(180deg); /* Initially hidden */
  opacity: 0; /* Initially hidden */
}

.card:hover .card-front {
  transform: rotateY(-180deg); /* Rotate front to show back */
  opacity: 0; /* Fade out front */
}

.card:hover .card-back {
  transform: rotateY(0deg); /* Rotate back to be visible */
  opacity: 1; /* Fade in back */
}

.card-content {
  text-align: center;
  padding: 20px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-front">
    <div class="card-content">
      <h2>Front</h2>
      <p>Summary of the content.</p>
    </div>
  </div>
  <div class="card-back">
    <div class="card-content">
      <h2>Back</h2>
      <p>More detailed information here. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    </div>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`perspective`:**  Gives the card a 3D space for the rotation to occur.
* **`backface-visibility: hidden`:** Prevents the back of the card from being visible during the transition.
* **`transition`:**  Smoothly animates the `transform` and `opacity` properties over 0.5 seconds.
* **`transform: rotateY()`:** Rotates the card around the Y-axis to create the flip effect.
* **`opacity`:** Controls the visibility of the front and back sides during the transition.
* **The hover effect:**  The `:hover` pseudo-class triggers the rotation and opacity changes when the mouse hovers over the card.


**Links to Resources to Learn More:**

* [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [CSS-Tricks - Understanding CSS Transforms](https://css-tricks.com/almanac/properties/t/transform/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

