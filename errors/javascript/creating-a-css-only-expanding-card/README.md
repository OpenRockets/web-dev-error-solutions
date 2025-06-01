# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  This effect involves a card that expands to reveal more content when clicked or hovered over. We'll achieve this using only CSS, no JavaScript required, leveraging transitions and pseudo-elements.

## Description of the Styling

This style creates a simple card with a title, some concise content, and a "Read More" section.  On hover or click (depending on implementation chosen), the card expands vertically to reveal hidden content.  The expansion is smoothly animated using CSS transitions. The styling utilizes clean, semantic HTML, making it easy to maintain and extend.


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
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition for expansion */
  max-height: 200px; /* Initially limited height */
}

.card:hover {
  max-height: 500px; /* Expand on hover */
}

.card-header {
  background-color: #f0f0f0;
  padding: 10px;
}

.card-content {
  padding: 10px;
}

.card-content.hidden{
    max-height: 0;
    overflow: hidden;
}

.card-content.expanded{
    max-height: 300px; /* Adjust as needed */
    overflow: auto; /* Add scroll if content exceeds max-height */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-header">
    <h3>Card Title</h3>
  </div>
  <div class="card-content expanded">
    <p>This is some concise content visible initially.</p>
    <p>This is additional content that is revealed upon hovering or clicking.</p>
    <p>You can add more content here.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`:** This class styles the main card element. `overflow: hidden;` ensures that the content doesn't overflow before expansion. The `transition` property is crucial for the smooth animation.  `max-height` initially limits the card's height.

* **`.card:hover`:** On hover, `max-height` is increased to reveal the hidden content.

* **`.card-header`:** Styles the card's header.

* **`.card-content`:** Styles the card's main content.  The `.hidden` and `.expanded` classes control the initial and expanded states.

* **JavaScript Alternative (Optional):**  You could replace the `:hover` with JavaScript to handle clicks instead, providing more control over the expanding behaviour.


## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS Overflow Property:** [MDN Web Docs - CSS Overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

