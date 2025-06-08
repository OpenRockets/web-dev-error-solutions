# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript is required! This utilizes CSS transitions and transforms to achieve a smooth and visually appealing animation.

**Description of the Styling:**

This example creates a card that expands vertically when hovered over.  The expansion reveals hidden content below the initial card.  The styling uses a combination of `transition`, `transform`, and `max-height` properties to control the animation and size of the card.  We also leverage some basic box-shadow and padding for visual enhancement.


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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  padding: 15px;
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Expanded height on hover */
}

.card-content {
  /* Content within the card */
}

.card-title{
  font-weight:bold;
}

</style>
</head>
<body>

<div class="card">
  <h2 class="card-title">Card Title</h2>
  <div class="card-content">
    <p>This is some example text that will be revealed when you hover over the card.</p>
    <p>More text here to demonstrate the expansion effect. You can add as much content as you like!</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card element.  `overflow: hidden;` prevents content from spilling outside the card boundaries during the transition.  `transition: max-height 0.3s ease-in-out;` defines the transition property, specifying that the `max-height` property will change smoothly over 0.3 seconds using an ease-in-out timing function.  `max-height: 100px;` sets the initial height of the card.

* **`.card:hover`:** This styles the card when the mouse hovers over it.  `max-height: 300px;` sets the expanded height of the card.  The transition defined in the `.card` class will automatically animate this height change.


* **`.card-content`:** This class styles the content within the card; you can adjust this as needed for your layout.


**Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:**  Search for "CSS transitions" or "CSS card hover effects" on [https://css-tricks.com/](https://css-tricks.com/) for more advanced examples.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

