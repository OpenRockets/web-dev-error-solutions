# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This is achieved using pure CSS3 transitions and transforms, without the need for JavaScript.  We'll leverage the `max-height` property and transitions for a smooth animation.

## Description of the Styling

The styling focuses on creating a card with a limited initial height.  On hover, the `max-height` is increased to allow the hidden content to become visible.  A smooth transition ensures a visually appealing animation.  We'll use simple styling for clarity, but this could easily be adapted using a CSS framework like Tailwind CSS.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
  width: 300px;
}

.card:hover {
  max-height: 300px; /* Height when hovered */
}

.card-content {
  padding: 10px;
}

.hidden {
  display: none; /* Initially hide the extra content */
}

.card:hover .hidden {
  display: block; /* Show extra content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some sample text for the card.</p>
    <div class="hidden">
      <p>This is the hidden content that will appear on hover.</p>
      <p>More hidden content here...</p>
    </div>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`.card`:** This class styles the card itself.  `overflow: hidden` prevents the content from overflowing the initial height. `transition` defines the smooth animation on the `max-height` property. `max-height: 100px;` sets the initial height.
* **`.card:hover`:** This styles the card when the mouse hovers over it, increasing `max-height` to reveal the hidden content.
* **`.card-content`:**  This class styles the content inside the card.
* **`.hidden`:** This class initially hides the extra content using `display: none`.
* **`.card:hover .hidden`:** This targets the `.hidden` elements within the `.card` when hovering, changing `display` to `block` to show the content.

## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** Search for "CSS only hover effects" on [https://css-tricks.com/](https://css-tricks.com/) for many more examples.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

