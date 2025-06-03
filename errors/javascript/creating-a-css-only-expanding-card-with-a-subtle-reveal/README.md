# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card effect using only CSS.  The card expands vertically when hovered over, revealing hidden content with a smooth transition.  No JavaScript is required.  This example leverages standard CSS properties and avoids frameworks like Tailwind for clarity and educational purposes.

## Description of the Styling

The card is designed with a basic structure: a container holding a header and a content area. The content area initially has a height of zero and is hidden.  On hover, the container's height is adjusted, revealing the content using a transition for a smooth animation.  We use `overflow: hidden` on the container to initially mask the content and ensure a clean reveal.  Box-shadow adds a subtle depth effect.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card-header {
  background-color: #333;
  color: white;
  padding: 15px;
  font-weight: bold;
}

.card-content {
  padding: 15px;
  height: 0; /* Initially hidden */
  overflow: hidden; /* Hide content until expanded */
  transition: height 0.3s ease-in-out; /* Match container transition */
}

.card:hover .card-content {
  height: auto; /* Expand on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">Expanding Card</div>
  <div class="card-content">
    <p>This is the content of the expanding card.  You can add as much text or other elements here as you like.  The card will smoothly expand to accommodate the content.</p>
    <p>Notice the smooth transition effect achieved using CSS transitions.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`**: This class styles the main container.  `overflow: hidden` is crucial for masking the initially hidden content.  The `transition` property ensures a smooth animation.
* **`.card-header`**: Styles the header section.
* **`.card-content`**:  Crucially, `height: 0` hides the content initially, and `overflow: hidden` prevents content from overflowing before expansion. The `transition` matches the container's transition for synchronization.
* **`.card:hover .card-content`**: This selector targets the `.card-content` element *only* when the `.card` element is hovered.  `height: auto` allows the content to expand naturally to fit its content.


## Resources to Learn More

* **MDN Web Docs (CSS Transitions):** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (Advanced CSS Techniques):** [https://css-tricks.com/](https://css-tricks.com/) (Search for articles on transitions and animations)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

