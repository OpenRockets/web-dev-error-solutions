# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The card expands vertically when hovered over, revealing hidden content with a smooth transition. This effect is achieved using CSS transitions and transformations without any JavaScript.  The styling uses a modern approach suitable for integration with frameworks like Tailwind CSS, but can be readily adapted for other CSS styles.


**Description of the Styling:**

The card starts in a collapsed state.  On hover, the `height` of the card is increased using a transition to animate the change smoothly. The hidden content is initially set to `overflow: hidden`, so it doesn't affect the initial layout.  The `transform: translateY()` property is used for a subtle sliding-up effect.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  overflow: hidden; /* initially hides the overflowing content */
  transition: height 0.3s ease-in-out; /* smooth transition for height change */
  width: 300px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.card:hover {
  height: 300px; /* expanded height */
}

.card-content {
  padding: 20px;
}

.card-content-hidden {
  /* initial hidden content */
  height: 0;
  opacity: 0;
  transition: height 0.3s ease-in-out, opacity 0.3s ease-in-out;
  overflow: hidden; /* hides the content until revealed */
  transform: translateY(10px); /* initially offset slightly upwards */
}

.card:hover .card-content-hidden {
  height: auto; /* expanded height of hidden content */
  opacity: 1;
  transform: translateY(0); /* slide up on hover */
}


</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>Some initial card content.</p>
  </div>
  <div class="card-content-hidden">
    <p>This is the hidden content that is revealed when the card is hovered over.</p>
    <p>More hidden content here...</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`transition: height 0.3s ease-in-out;`**: This line creates a smooth transition for the `height` property over 0.3 seconds using an "ease-in-out" timing function.
* **`overflow: hidden;`**: This is crucial for hiding the content initially. Without it, the hidden content would affect the card's initial height.
* **`transform: translateY(10px);`**: This subtly offsets the hidden content upwards before it is revealed, adding a nice visual effect.
* **`:hover` pseudo-class**: This selector targets the card when the mouse hovers over it.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

