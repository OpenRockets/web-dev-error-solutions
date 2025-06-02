# 🐞 Creating a CSS-only Expanding Card with Hover Effect


This document details the creation of an expanding card using only CSS.  The card expands on hover to reveal additional content, showcasing the power of CSS transitions and pseudo-elements.  We'll leverage CSS3 transitions and transforms for this effect.

**Description of the Styling:**

The card consists of a main container with an image and a text overlay. On hover, the card expands horizontally, pushing the text overlay to the right to reveal more content hidden initially.  The expansion is smooth thanks to CSS transitions. The added content appears to slide in from the right.  We use a simple color scheme for clarity, but you can easily customize it.


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
  perspective: 1000px; /* For 3D transform effect */
  overflow: hidden; /* Hide content outside the card */
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  transition: transform 0.3s ease-in-out; /* Smooth transition on hover */
}

.card:hover {
  transform: scale(1.1); /* Expand on hover */
}

.card-image {
  width: 100%;
  height: 100%;
  background-image: url("https://via.placeholder.com/300x200"); /* Replace with your image */
  background-size: cover;
  background-position: center;
  border-radius: 10px;
}

.card-text {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 15px;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  transform: translateY(100%); /* Initially hidden */
  transition: transform 0.3s ease-in-out;
}

.card:hover .card-text {
  transform: translateY(0); /* Reveal on hover */
}

.card-content {
  position: absolute;
  top: 0;
  right: 0;
  width: 0; /* Initially hidden */
  height: 100%;
  padding: 15px;
  background-color: rgba(0, 0, 0, 0.8);
  color: white;
  overflow: hidden; /* To hide content until expanded */
  transition: width 0.3s ease-in-out; /* Smooth width transition */
}

.card:hover .card-content {
  width: 150px; /* Show on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-image"></div>
  <div class="card-text">
    <h3>Card Title</h3>
    <p>Short description</p>
  </div>
  <div class="card-content">
    <p>Additional information revealed on hover.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:** Creates a 3D space for the smoother scaling effect.
* **`transition`:** Smoothly animates the `transform` property on hover.
* **`transform: scale(1.1)`:** Expands the card on hover.
* **`transform: translateY(100%)`:** Initially hides the card text.
* **`transition: transform 0.3s ease-in-out` on `.card-text`:**  Smoothly animates the text's vertical position.
* **`position: absolute`:** Allows absolute positioning for precise overlaying.
* **`overflow: hidden`:** Prevents content from spilling outside the card's boundaries.

**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

