# 🐞 Creating a CSS-only Expanding Card with a Reveal Effect


This document details the creation of an expanding card using only CSS.  The card expands vertically when hovered, revealing hidden content. We'll be using CSS transitions and transforms to achieve this smooth animation effect. No JavaScript is required.

**Description of the Styling:**

The card utilizes a simple structure: a container holding a visible front section and a hidden back section.  On hover, the front section scales down slightly and moves upward, revealing the back section which simultaneously slides upwards.  The animation is controlled using CSS transitions and transforms.  We will style it with simple box-shadow and padding for a more appealing look.


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
  perspective: 1000px; /* Required for 3D transforms */
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  overflow: hidden; /* Hide content overflowing during transition */
}

.card-front, .card-back {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Prevent back face from showing during transition */
  transition: transform 0.3s ease-in-out; /* Smooth transition */
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  text-align: center;
}

.card-front {
  background-color: #f0f0f0;
  color: #333;
}

.card-back {
  background-color: #4CAF50;
  color: white;
  transform: translateY(100%); /* Initially hidden below the front */
}

.card:hover .card-front {
  transform: translateY(-20%) scale(0.9); /* Move up and scale down */
}

.card:hover .card-back {
  transform: translateY(0%); /* Reveal the back section */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-front">
    <h3>Click to Reveal!</h3>
  </div>
  <div class="card-back">
    <h2>Hidden Content!</h2>
    <p>This is the hidden content revealed on hover.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:** This property creates a 3D space for the card's transformation, making the animation more realistic.
* **`backface-visibility: hidden;`:** This prevents the back of the card from being visible during the transition.
* **`transition`:** This property defines the smooth animation for the transform property.
* **`transform: translateY()`:** This property moves the elements along the Y-axis (vertically).
* **`transform: scale()`:** This property changes the size of the element.
* **Hover Effects:** The `:hover` pseudo-class triggers the animation when the mouse hovers over the card.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks:** (Search for "CSS animations" or "CSS transitions" on their site for numerous tutorials and examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

