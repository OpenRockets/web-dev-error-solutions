# 🐞 Creating a CSS-Only Expanding Card with a Reveal Effect


This document details a CSS-only solution to create an expanding card effect.  When the card is hovered over, it expands revealing additional content, all without using JavaScript. This utilizes CSS transitions and pseudo-elements for a smooth and visually appealing animation.


## Description of the Styling

The card starts in a collapsed state.  On hover, it expands horizontally revealing a hidden section.  The expansion is smooth thanks to CSS transitions. We achieve this by manipulating the width and padding of the card along with the opacity of the hidden content.  The visual effect mimics a reveal animation.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide the expanding content initially */
  transition: width 0.3s ease-in-out; /* Smooth transition for width change */
  width: 200px;
  padding: 10px;
}

.card:hover {
  width: 400px; /* Expand on hover */
}

.card-content {
  padding-bottom:20px;
}

.card-hidden {
  opacity: 0;
  transition: opacity 0.3s ease-in-out; /* Smooth transition for opacity change */
  padding-left:20px;
}

.card:hover .card-hidden {
  opacity: 1; /* Reveal hidden content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some initial content.</p>
  </div>
  <div class="card-hidden">
    <p>This is the hidden content revealed on hover.</p>
    <p>It smoothly transitions in using CSS transitions.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`**: This class styles the main card container.  `overflow: hidden;` is crucial for keeping the hidden content out of sight until the hover effect.  The `transition` property ensures smooth animation.

* **`.card:hover`**: This selector targets the card when the mouse hovers over it, expanding the width.

* **`.card-hidden`**: This class styles the hidden content, initially with `opacity: 0`. The transition on opacity mirrors the width transition.

* **`.card:hover .card-hidden`**:  This selector sets the opacity to 1 when hovering over the card, revealing the hidden content.


## Links to Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks on Advanced Hover Effects:** [https://css-tricks.com/examples/HoverEffect1/](https://css-tricks.com/examples/HoverEffect1/) (search for similar examples on the site)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

