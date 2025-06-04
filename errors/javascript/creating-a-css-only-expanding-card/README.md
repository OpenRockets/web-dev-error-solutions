# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript is required! This effect involves a card that expands vertically when hovered over, revealing more content. We'll be using plain CSS for this example, showcasing the power of CSS transitions and transforms.


**Description of the Styling:**

The card uses a simple layout with a main container that holds the visible content and a hidden section that expands on hover.  We leverage CSS transitions for smooth animation and transforms for the expansion effect.  The key is using `max-height` and `overflow: hidden` to initially conceal the expandable content.  On hover, `max-height` is changed to allow the content to expand, creating the animation.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: 0.3s ease-in-out; /* Smooth transition */
  width: 300px;
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-description {
  line-height: 1.6;
}

.card-expand {
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Transition for expansion */
}

.card:hover .card-expand {
  max-height: 200px; /* Expand on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-description">This is a simple card that expands on hover to reveal more content.  No JavaScript required!</p>
  </div>
  <div class="card-expand">
    <p>This is the extra content that will be revealed when you hover over the card.  You can add as much content as you need here.</p>
    <p>This demonstrates a simple but effective CSS-only animation.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`card` class:** Styles the overall card with background, border radius, shadow, and a transition for smooth animation.
* **`card-content` class:** Styles the content visible by default.
* **`card-title` and `card-description` classes:** Style the title and description.
* **`card-expand` class:**  Crucially, this class uses `max-height: 0;` and `overflow: hidden;` to initially hide the expandable content. The `transition` property ensures a smooth animation.
* **`.card:hover .card-expand`:** This selector targets the `.card-expand` element *only when* its parent `.card` is hovered. It sets `max-height: 200px;`, allowing the content to expand.  Adjust `200px` to control the expansion height.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

