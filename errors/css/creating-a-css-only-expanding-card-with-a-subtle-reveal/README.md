# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card effect using only CSS.  The card expands on hover to reveal additional content, using a subtle animation for a visually appealing transition. This example uses plain CSS3, but could easily be adapted to use a CSS framework like Tailwind CSS.


**Description of the Styling:**

The card uses a simple layout with a main container holding the visible content and a hidden section for the expanded content.  On hover, the main container's height increases, revealing the hidden section.  A smooth transition using `transition` property creates the animation.  We also apply some basic styling for visual appeal.

**Full Code:**

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
  overflow: hidden; /* Hide the expanding content initially */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: 350px; /* Increase height on hover to reveal hidden content */
}

.card-content {
  padding: 20px;
}

.card-content-hidden {
  padding: 20px;
  height: 0; /* Initially hidden */
  overflow: hidden; /* Hide the content until expanded */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover .card-content-hidden {
  height: auto; /* Show hidden content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Title of the Card</h2>
    <p>Some introductory text for the card.</p>
  </div>
  <div class="card-content-hidden">
    <h3>Expanded Content</h3>
    <p>This section is revealed when the user hovers over the card.</p>
    <p>You can add more content here as needed.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden` is crucial for hiding the expanded content initially.  `transition` defines the animation.
* **`.card:hover`:** This styles the card when the mouse hovers over it.  The `height` property increases to reveal the hidden content.
* **`.card-content`:** Styles the visible content of the card.
* **`.card-content-hidden`:** Styles the initially hidden content. `height: 0` and `overflow: hidden` keep it hidden until the hover effect.  The `transition` ensures a smooth expansion.
* **`.card:hover .card-content-hidden`:**  This targets the hidden content *only when* the card is hovered, changing its `height` to `auto` to display the content.


**Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks - Transitions and Animations:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)
* **Understanding CSS Selectors:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

