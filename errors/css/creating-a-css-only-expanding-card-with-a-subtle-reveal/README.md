# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details how to create an expanding card effect using only CSS.  The card expands on hover, revealing hidden content with a smooth animation.  This effect utilizes CSS transitions and transforms for a clean and modern look.  We'll be using standard CSS3, no preprocessors like Sass or Tailwind are needed.

**Description of the Styling:**

The card consists of a container element holding a front and a back element. The front displays the initial card content, while the back contains the hidden content revealed on hover.  We use CSS transitions to smoothly animate the card's transformation on hover.  The `transform: perspective()` and `transform-style: preserve-3d;` properties are crucial for creating the 3D expanding effect.  We also use a subtle box-shadow to add depth.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  perspective: 1000px; /* Creates the 3D perspective */
  transform-style: preserve-3d; /* Ensures child elements are rendered in 3D space */
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  transition: transform 0.5s ease-in-out; /* Smooth transition for hover effect */
}

.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Hides the back of the card initially */
  border-radius: inherit;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  box-sizing: border-box;
}

.card-front {
  background-color: #4CAF50;
  color: white;
}

.card-back {
  background-color: #2196F3;
  color: white;
  transform: rotateY(180deg); /* Rotate the back face 180 degrees */
}

.card:hover {
  transform: rotateY(180deg); /* Rotate the card on hover to reveal the back */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-front">
    <h3>Front of Card</h3>
  </div>
  <div class="card-back">
    <h3>Back of Card - Hidden Content</h3>
    <p>This content is revealed on hover.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`perspective`:** This property creates the 3D perspective, making the rotation effect more realistic.
* **`transform-style: preserve-3d`:**  This is essential for ensuring that the child elements (`card-front` and `card-back`) are correctly positioned in 3D space.
* **`backface-visibility: hidden`:** This prevents the back of the card from being visible before the hover effect.
* **`transform: rotateY(180deg)`:** This rotates the card around the Y-axis.
* **`transition`:** This property allows for a smooth animation when the `transform` property changes on hover.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (General CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

