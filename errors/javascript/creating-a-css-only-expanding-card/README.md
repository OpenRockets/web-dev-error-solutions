# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  This effect involves a card that, upon hover, expands to reveal more content.  No JavaScript is required.  We'll achieve this using CSS transitions and transforms.

**Description of the Styling:**

The card consists of two main parts: a front and a back.  The front displays a summary, while the back reveals additional information.  Using CSS transitions, we'll smoothly animate the transform of the card's elements on hover.  We'll use the `transform: rotateY()` property to create the flip effect, though it's subtly applied to achieve expansion instead of a full 180-degree flip.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  perspective: 1000px; /* Essential for 3D transformations */
  width: 300px;
  height: 200px;
  margin: 20px auto;
  transition: transform 0.5s ease-in-out; /* Smooth transition */
}

.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Hide the back face initially */
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 5px;
}

.card-front {
  background-color: #f0f0f0;
  color: #333;
}

.card-back {
  background-color: #ddd;
  color: #000;
  transform: rotateY(-180deg); /* Initially hidden on the back */
}

.card:hover {
  transform: rotateY(-30deg); /* Expand on hover - subtle rotation */
}

.card-front h2, .card-back h2{
  margin:0;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-front">
    <h2>Card Front</h2>
    <p>Summary of the content goes here.</p>
  </div>
  <div class="card-back">
    <h2>Card Back</h2>
    <p>This is the expanded content, revealing more details.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`perspective`:** This property creates the 3D space for the transformation.
* **`transform: rotateY()`:** This rotates the element around the Y-axis. We manipulate this on hover to create the expansion.  A full 180-degree rotation would be a flip; we use a smaller angle for the expansion effect.
* **`backface-visibility: hidden;`:**  This prevents the back of the card from being visible until we rotate it.
* **`transition`:** This property smoothly animates the `transform` property over 0.5 seconds.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

