# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The effect involves a subtle reveal of card content upon hover, utilizing CSS transitions and transforms.  No JavaScript is required.  This example uses plain CSS3; adapting it to Tailwind would simply involve replacing the CSS class names with their Tailwind equivalents.


## Description of the Styling

The card starts in a collapsed state. On hover, the card expands horizontally, and a hidden content area slides into view.  The expansion uses a smooth transition for a polished user experience. A subtle box-shadow is added to enhance the three-dimensional effect.


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
  overflow: hidden; /* Hide overflowing content initially */
  transition: width 0.3s ease-in-out, height 0.3s ease-in-out; /* Smooth transition */
}

.card:hover {
  width: 400px;
  height: 250px;
}

.card-content {
  padding: 10px;
  height: 100%; /* Occupies the full height of the card */
  display: flex;
  flex-direction: column; /* Align content vertically */
  justify-content: space-between; /* Distribute space between items */
}

.card-title {
  font-weight: bold;
}

.card-text {
  font-size: 14px;
  overflow: hidden;
  transition: max-height 0.3s ease-in-out;
  max-height: 0; /* Initially hidden */
}


.card:hover .card-text {
  max-height: 100px; /* Reveal text on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p class="card-text">This is some example text that will expand on hover.  Lorem ipsum dolor sit amet, consectetur adipiscing elit. </p>
    <button>Learn More</button>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`overflow: hidden;`:** This is crucial for hiding the extra content initially.
* **`transition: width 0.3s ease-in-out, height 0.3s ease-in-out;`:** This line creates the smooth transition effect for width and height changes on hover.
* **`max-height: 0;` and `max-height: 100px;`:** These control the height of the text content, revealing it on hover.  Adjust `100px` as needed.
* **`display: flex;`, `flex-direction: column;`, `justify-content: space-between;`:** These flexbox properties are used to neatly arrange the content within the card.


## Resources to Learn More

* **CSS Transitions:**  [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **Flexbox Layout:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

