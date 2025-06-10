# 🐞 CSS Challenge:  Animated Expanding Card


This challenge involves creating a card that expands when hovered over, revealing more content. We'll use CSS3 transitions and transforms to achieve the animation.  No JavaScript is required.

## Description of the Styling:

The card will start with a compact size. Upon hovering, it smoothly expands horizontally, revealing additional text within.  The expansion animation should be smooth and visually appealing. We'll style the card with a clean, modern look using standard CSS properties.

## Full Code:

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
  padding: 20px;
  transition: transform 0.3s ease-in-out; /* Smooth transition for transform property */
  width: 300px; /* Initial width */
  overflow: hidden; /* Hide content that overflows initially */
}

.card:hover {
  transform: scaleX(1.5); /* Expand horizontally on hover */
  width: 450px; /* Adjust width to match expanded state */
}

.card-content {
  /* Initially hidden content */
}
.card-content p{
  margin-top: 0;
}

.card-title {
  font-size: 1.2em;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1em;
}
</style>
</head>
<body>

<div class="card">
  <h2 class="card-title">Card Title</h2>
  <p class="card-text">This is some initial text content.</p>
  <div class="card-content">
    <p>This additional text content will be revealed on hover.</p>
    <p>This is a multi-line example.</p>
  </div>
</div>

</body>
</html>
```

## Explanation:

* **`.card`**: This class styles the main card element.  `transition: transform 0.3s ease-in-out;` is crucial for the smooth animation. It targets the `transform` property, specifying a 0.3-second transition with an `ease-in-out` timing function.  `overflow: hidden` prevents the initially hidden content from showing before the hover.
* **`.card:hover`**: This styles the card when the mouse hovers over it. `transform: scaleX(1.5);` scales the card horizontally by 1.5 times, creating the expansion effect.  The width is explicitly set to ensure the expanded content is visible.
* **`.card-content`**: This class wraps the content that is initially hidden, allowing for better control of its visibility and placement.
* **`.card-title` and `.card-text`**: These are simply for styling the title and paragraph text within the card.


## Resources to Learn More:

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS3 Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

