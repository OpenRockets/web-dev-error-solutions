# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered, revealing additional content.  This technique uses pure CSS3, avoiding the need for JavaScript.

## Description of the Styling

The card consists of a container with two inner elements: a header and a content section.  The content section is initially hidden using `max-height: 0` and `overflow: hidden`. On hover, the `max-height` is changed to a value large enough to display the full content, revealing it smoothly via a transition effect.  The transition provides a smooth animation during the expansion.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden; /* Prevents content from overflowing before expansion */
  transition: all 0.3s ease; /* Smooth transition for expansion */
}

.card-header {
  background-color: #f0f0f0;
  padding: 10px;
  cursor: pointer; /* Indicate it's interactive */
}

.card-content {
  padding: 10px;
  max-height: 0; /* Initially hidden */
  overflow: hidden; /* Hide overflowing content */
  transition: max-height 0.3s ease; /* Smooth transition for height change */
}

.card:hover .card-content {
  max-height: 200px; /* Set desired height when hovered */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">
    <h3>Click to Expand</h3>
  </div>
  <div class="card-content">
    <p>This is the content that will expand when you hover over the card.  You can add as much text or other elements as you need here.  This is just an example to demonstrate the functionality.</p>
    <p>More content here...</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`**: This class styles the overall card container, setting its width, border, rounded corners, and applying a transition for smooth animations.  `overflow: hidden` is crucial for hiding the content initially.

* **`.card-header`**: Styles the header section, including background color and padding.  `cursor: pointer` makes the cursor change to a hand when hovering, indicating it's clickable (though it's actually the hover effect that drives the expansion).

* **`.card-content`**: Styles the content section. `max-height: 0` hides the content by default. `overflow: hidden` prevents content from spilling outside the `max-height` boundary.  The transition is applied to `max-height` specifically for smooth expansion.

* **`.card:hover .card-content`**: This is the crucial selector.  It targets the `.card-content` element *only* when the `.card` element is hovered.  The `max-height` is changed to a value (200px in this example, adjust as needed) that allows the content to be visible.


## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks:**  Search for "CSS-only expanding card" on [https://css-tricks.com/](https://css-tricks.com/) for more advanced variations and techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

