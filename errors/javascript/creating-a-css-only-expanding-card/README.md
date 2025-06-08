# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required.  The effect involves a card that expands vertically when hovered over, revealing hidden content.  We'll achieve this using CSS transitions and transforms.


**Description of the Styling:**

The card will have a basic structure: a container holding a header and a content section.  The content section will initially be hidden using `max-height: 0;` and `overflow: hidden;`. On hover, we'll use a CSS transition to smoothly increase the `max-height` to allow the content to become visible.  A subtle transform will be added for visual appeal.


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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide overflowing content */
  transition: transform 0.3s ease, box-shadow 0.3s ease; /* Smooth transitions */
  width: 300px;
}

.card:hover {
  transform: translateY(-5px); /*Slight lift on hover*/
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* More pronounced shadow */
}

.card-header {
  background-color: #333;
  color: white;
  padding: 15px;
  text-align: center;
}

.card-content {
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.3s ease; /* Smooth height transition */
  padding: 15px;
}

.card:hover .card-content {
  max-height: 200px; /* Height on hover, adjust as needed */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">Card Title</div>
  <div class="card-content">
    <p>This is the content of the expanding card.  It's initially hidden and will smoothly appear when you hover over the card.</p>
    <p>Add more content here as needed.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** Styles the main card container, setting background, border radius, box shadow, and crucial transitions for smooth animations.
* **`.card:hover`:**  Applies styles specifically when the card is hovered over (the `translateY` creates a subtle lift effect).
* **`.card-header`:** Styles the header section.
* **`.card-content`:**  Crucially, `max-height: 0;` and `overflow: hidden;` initially hide the content.  The transition on `max-height` controls the animation.
* **`.card:hover .card-content`:** When hovering over the card,  `max-height` is increased to reveal the content.  Adjust `200px` to control the final expanded height.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Search for "CSS transitions" or "CSS animations")


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

