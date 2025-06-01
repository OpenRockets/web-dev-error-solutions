# 🐞 Creating a Pure CSS Expanding Card with a Hover Effect


This document details the creation of an expanding card using only CSS.  No JavaScript is required. The effect involves a card that smoothly expands its content area on hover, revealing hidden information.  This is achieved using CSS transitions and animations.


**Description of the Styling:**

The card utilizes a simple layout with a main container holding an image and a content area.  On hover, the `transform` property scales the card slightly, giving the impression of depth.  The content area's height expands using the `max-height` property combined with a transition, creating a smooth animation.  We leverage pseudo-elements (`::before` and `::after`) for visual enhancements like a subtle shadow and a background color.


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
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease; /* Smooth transition for scaling */
}

.card:hover {
  transform: scale(1.05); /* Scale up on hover */
}

.card-image {
  width: 100%;
  height: 100px;
  object-fit: cover;
}

.card-content {
  padding: 15px;
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.3s ease; /* Smooth transition for height change */
}

.card:hover .card-content {
  max-height: 150px; /* Expand on hover */
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.1);
  z-index: -1; /* Behind the content */
  transform: scale(1.05);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.card:hover::before{
  opacity: 1;
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/300x100" alt="Card Image" class="card-image">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some sample text for the card content.  This area expands on hover.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

1. **Container (`card`):** Sets the basic dimensions, border radius, shadow, and transition for scaling.
2. **Image (`card-image`):**  Ensures the image covers the entire area.
3. **Content Area (`card-content`):** Initially has `max-height: 0`, hiding the content.  The transition on `max-height` enables the smooth expansion.
4. **Hover Effects:**  The `:hover` pseudo-class triggers the scaling and content expansion.
5. **Pseudo-elements (`::before`):** Creates a subtle background effect and shadow that appear on hover.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-elements:** [MDN Web Docs - CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

