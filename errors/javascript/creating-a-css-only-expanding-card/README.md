# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution for creating an expanding card effect, a common interactive element in web design.  This example uses only CSS3, avoiding the need for JavaScript.  The effect involves a card that expands to reveal more content when hovered over.

**Description of the Styling:**

The styling leverages CSS transitions and the `:hover` pseudo-class to achieve the animation. The card starts with a smaller height and then expands vertically on hover.  We'll use simple box-shadow to give it a bit of depth, and some padding for visual comfort.  The inner content will be hidden initially and then revealed with the height expansion.

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
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Prevents content from overflowing during expansion */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  height: 100px; /* Initial height */
  width: 300px;
}

.card:hover {
  height: 300px; /* Expanded height on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
    font-size: 1em;
    line-height: 1.6;
}

.hidden {
    overflow: hidden;
    height: 0; /* Initially hidden content */
    transition: height 0.3s ease-in-out;
}

.card:hover .hidden {
    height: auto;  /* Show content on hover */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is some example text that will be hidden initially and revealed when you hover over the card.  You can add as much text as you like here.</p>
    <p class="hidden">This is additional hidden content. It will only be visible on hover.</p>
    <p class="hidden">More hidden content here to demonstrate the expansion!</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition: height 0.3s ease-in-out;`**: This line creates a smooth transition for the `height` property over 0.3 seconds using an ease-in-out timing function.
* **`:hover`**: This pseudo-class applies the styles within its block only when the element is hovered over.
* **`overflow: hidden;`**:  This is crucial on the `card` and initially on the hidden content (`hidden` class). It prevents content from spilling outside the card's boundaries during the transition.
* **`.hidden` class**: This class is used to initially hide the content using `height: 0`. The hover state removes this limitation allowing the text to flow freely based on its natural size.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS `overflow` property:** [MDN Web Docs - CSS overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

