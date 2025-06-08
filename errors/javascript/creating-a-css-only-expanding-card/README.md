# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing additional content.  This is achieved using pure CSS transitions and transforms, requiring no JavaScript.  This example uses standard CSS3; no framework like Tailwind is necessary.

**Description of the Styling:**

The card is composed of two main parts: a header and a content area.  The header remains static in size, while the content area is initially hidden and then expands smoothly upon hover. This effect leverages CSS transitions on `max-height` and `transform` properties. We'll also utilize a pseudo-element (`::before`) to create a subtle background shadow for visual enhancement.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: box-shadow 0.3s ease, transform 0.3s ease; /* Add smooth transitions */
}

.card:hover {
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
  transform: translateY(-2px); /* Slight lift on hover */
}


.card-header {
  background-color: #4CAF50;
  color: white;
  padding: 15px;
  text-align: center;
}

.card-content {
  max-height: 0; /* Initially hidden */
  overflow: hidden; /* Hide overflowing content */
  transition: max-height 0.5s ease-out; /* Smooth expansion */
}

.card:hover .card-content {
  max-height: 200px; /* Expanded height on hover */
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.05);
  z-index: -1; /* Place behind the card */
  opacity: 0;
  transition: opacity 0.3s ease;
}

.card:hover::before {
  opacity: 1;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">Card Title</div>
  <div class="card-content">
    <p>This is some extra content that will be revealed when you hover over the card.  It's a simple and effective way to add some interactivity without needing JavaScript.</p>
    <p>You can adjust the `max-height` in the CSS to control how much content is revealed.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`max-height: 0;` and `overflow: hidden;`:**  These initially hide the `.card-content`.
* **`transition: max-height 0.5s ease-out;`:**  This smooths the expansion by animating the `max-height` property.
* **`:hover .card-content { max-height: 200px; }`:** This expands the content area on hover.
* **`box-shadow` and `transform` transitions:** These provide subtle visual feedback on hover.
* **The `::before` pseudo-element:** Creates a subtle background shadow effect that enhances the overall card appearance.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

