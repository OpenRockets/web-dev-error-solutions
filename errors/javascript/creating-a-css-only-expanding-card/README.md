# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  This effect provides a visually appealing way to reveal more information upon hovering over a card element. We'll use plain CSS, avoiding JavaScript for a lightweight and performant solution.

**Description of the Styling:**

The card will initially display a concise title and a small image. On hover, the card expands vertically, revealing a longer description and potentially more content.  This is achieved using CSS transitions and the `max-height` property, dynamically controlled by the `:hover` pseudo-class.

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
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Height when hovering */
}

.card-image {
  width: 100%;
  height: auto;
}

.card-content {
  padding: 10px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
}

.card-description {
  font-size: 0.9em;
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/350x150" alt="Card Image" class="card-image">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-description">This is a short description of the card content.  On hover, more details will appear.</p>
    <p class="card-description">This is additional text revealed on hover.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`max-height`:**  This property initially limits the card's height.  The `:hover` pseudo-class increases this height, revealing hidden content.
* **`transition`:** This property ensures a smooth animation when the `max-height` changes.  It specifies the property to transition (`max-height`), the duration (`0.3s`), and the easing function (`ease-in-out`).
* **`overflow: hidden;`:**  This is crucial to prevent the content from overflowing the card before expansion.
* **Card Structure:**  The HTML is structured logically with a container (`card`), an image (`card-image`), and content (`card-content`).


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks - Understanding CSS Transitions:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

