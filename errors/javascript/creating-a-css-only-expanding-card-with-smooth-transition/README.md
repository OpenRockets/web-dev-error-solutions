# 🐞 Creating a CSS-Only Expanding Card with Smooth Transition


This document details the creation of an expanding card using only CSS.  This effect leverages CSS transitions and transforms to create a visually appealing and user-friendly interactive element. No JavaScript is required!

**Description of the Styling:**

The card starts in a collapsed state.  On hover, it smoothly expands to reveal more content. This expansion utilizes CSS transitions to animate the changes in height and transform properties. The styling incorporates a subtle shadow and rounded corners for a modern look.  The visual changes are entirely handled by CSS, enhancing performance and simplifying the implementation.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows during transition */
  transition: height 0.3s ease-in-out, transform 0.3s ease-in-out; /* Smooth transition */
  height: 100px; /* Initial height */
}

.card:hover {
  height: 250px; /* Expanded height */
  transform: translateY(-5px); /* Slight lift on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
  font-size: 14px;
  line-height: 1.5;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is a simple example of an expanding card created using only CSS. Hover over the card to see the animation.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden;` prevents content from spilling outside the card during the expansion.  `transition` property defines the smooth animation for height and transform. The initial `height` is set to 100px.
* **`.card:hover`:** This selector targets the card when the mouse hovers over it.  The `height` is increased to 250px, and `transform: translateY(-5px);` creates a subtle lifting effect.
* **`.card-content`, `.card-title`, `.card-text`:** These classes style the inner content of the card, providing basic formatting for the title and text.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

