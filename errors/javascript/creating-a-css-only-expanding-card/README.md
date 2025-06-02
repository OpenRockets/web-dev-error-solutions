# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required.  The effect involves a card that expands to reveal more content when hovered over. This example uses plain CSS, but could easily be adapted to Tailwind CSS.

## Description of the Styling

The styling uses a combination of CSS transitions, transforms, and pseudo-elements (`::before` and `::after`) to achieve the expanding effect. The card initially shows a smaller version of its content.  On hover, the card expands vertically, revealing hidden content.  A subtle shadow effect is also added for enhanced visual appeal.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  background-color: #f0f0f0;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: all 0.3s ease; /* Smooth transition */
  position: relative; /* Needed for absolute positioning of pseudo-elements */
}

.card:hover {
  height: 300px; /* Expand on hover */
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
}

.card-content {
  padding: 10px;
  color: #333;
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 255, 0.8); /* semi-transparent white overlay */
  z-index: 1; /* Ensure it's above the content */
  transform: scaleY(0); /* Initially collapsed */
  transform-origin: top; /* Transformation origin at the top */
  transition: transform 0.3s ease; /* Smooth transition */
}

.card:hover::before {
  transform: scaleY(1); /* Expand on hover */
}

.card-content {
  position: relative; /* Needed for content to stay on top of the pseudo-element*/
  z-index: 2;
}

/* Add some more content for the expansion */
.hidden-content {
  display: none;
}

.card:hover .hidden-content {
  display: block;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some sample text.</p>
    <div class="hidden-content">
      <p>This is the extra content that is revealed on hover.</p>
      <p>More information here...</p>
    </div>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`transition: all 0.3s ease;`**: This line creates a smooth transition for all CSS properties that change, lasting 0.3 seconds and using an ease timing function.
* **`transform: scaleY(0);` & `transform: scaleY(1);`**: These lines control the vertical scaling of the pseudo-element, creating the expanding effect.
* **`overflow: hidden;`**: This ensures that the content which overflows the initial height is hidden until expansion
* **Pseudo-element (`::before`)**: This is used to create the visual effect of the card expanding from the top.  Its background color is set to a semi-transparent white to subtly highlight the expansion.
* **`position: relative;` & `position: absolute;` & `z-index`:** These are used to correctly layer the pseudo-element and ensure the expansion appears smoothly.
* **`.hidden-content`**: This class is used to hide content until the hover effect triggers.

## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs - CSS Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

