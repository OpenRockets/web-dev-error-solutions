# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  No JavaScript is required! This example uses pure CSS3 techniques.


**Description of the Styling:**

This example creates a card that expands vertically when hovered over. The expansion reveals hidden content within the card. The transition effect is smooth and visually appealing, achieved solely through CSS transitions and transforms. We'll use a simple structure with a container, an image, and some text to demonstrate.

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
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden; /* Hide content that overflows the card initially */
  perspective: 1000px; /* Enables 3D transforms */
  transition: 0.3s ease-in-out; /* Smooth transition for expansion */
}

.card:hover {
  transform: scale(1.1); /* Scale up on hover */
  box-shadow: 0 10px 20px rgba(0,0,0,0.1); /* Add a subtle shadow on hover */
  cursor: pointer;
}

.card-content {
  display: flex;
  flex-direction: column;
  padding: 10px;
  height: 100%; /* Ensures content fills card height */
}

.card-image {
  width: 100%;
  height: 100px;
  object-fit: cover; /* Ensure image covers entire area */
}

.card-text {
  flex-grow: 1; /* Allows text to take up remaining space */
  overflow: hidden; /* Hide text that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for text expansion */
  max-height: 0; /* Initially hide text */
}

.card:hover .card-text {
  max-height: 200px; /* Show text on hover */
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/300x100" alt="Card Image" class="card-image">
  <div class="card-content">
    <div class="card-text">
      This is some sample text that will expand when you hover over the card.  It demonstrates a simple yet effective CSS-only card expansion effect.  You can customize the text, image, and styling as needed to fit your design.
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:**  This property is crucial for creating the 3D scaling effect.  It defines a vanishing point for the 3D transformation.
* **`transform: scale(1.1)`:** This scales the card up slightly on hover, creating a subtle expansion.
* **`transition`:** The `transition` property makes the scaling and text expansion smooth.
* **`overflow: hidden`:** Initially hides the overflowing content, creating the "hidden" effect until hover.
* **`max-height`:** Controls the height of the text container, allowing for the expanding/collapsing effect.
* **`flex-grow: 1`:** Ensures that the text area uses all available space within the card.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Flexbox:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

