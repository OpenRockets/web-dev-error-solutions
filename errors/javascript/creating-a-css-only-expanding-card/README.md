# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This technique utilizes CSS transitions and the `max-height` property to achieve the animation without JavaScript.  While this example uses plain CSS, the concepts can be easily adapted for use with frameworks like Tailwind CSS.


**Description of the Styling:**

The card consists of a container div with a fixed height. Inside, we have another div containing the main content (initially visible) and a hidden section that will be revealed on hover.  We use `max-height` and CSS transitions to smoothly animate the height change on hover.  The hidden content initially has `overflow: hidden`, preventing it from overflowing the container, and `max-height: 0`. On hover, `max-height` is changed to a value that allows the full content to be displayed, creating the expansion effect.

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
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 150px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Height when hovering */
}

.card-content {
  padding: 20px;
}

.hidden-content {
  overflow: hidden;
  max-height: 0; /* Initially hidden */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
}

.card:hover .hidden-content {
  max-height: 200px; /* Height of hidden content when hovering */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Title of Card</h2>
    <p>This is some visible content of the card.</p>
  </div>
  <div class="hidden-content">
    <p>This is the hidden content that will be revealed on hover.</p>
    <p>More hidden content here...</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`**: This class styles the main card container. `max-height` initially limits the card's height, and `transition` ensures a smooth animation.
* **`.card:hover`**:  This selector targets the card when the mouse hovers over it, increasing the `max-height` to reveal the hidden content.
* **`.card-content`**:  This styles the initially visible content within the card.
* **`.hidden-content`**:  This styles the hidden content. `max-height: 0` initially hides it, and `overflow: hidden` prevents content overflow before expansion.
* **`.card:hover .hidden-content`**: This selector targets the hidden content *when* the card is hovered over, increasing its `max-height`.


**Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS `max-height` Property:** [MDN Web Docs - max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

