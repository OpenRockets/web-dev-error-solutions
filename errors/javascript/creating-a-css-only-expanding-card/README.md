# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically to reveal hidden content when clicked. This example uses only CSS3 properties and avoids JavaScript for a lightweight and performant solution.

**Description of the Styling:**

The styling uses CSS transitions and transforms to achieve the expanding effect. The card starts with a specific height and then smoothly transitions to a larger height when the `:target` pseudo-class is activated. We use a hidden checkbox as a toggle and link it to the card's ID using the checkbox's state. The hidden content is initially visually hidden with `overflow: hidden;`.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
body {
  font-family: sans-serif;
}

.card {
  width: 300px;
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden;
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card-content {
  padding: 20px;
}

.card-content p {
  margin: 0;
}

.card-header {
  background-color: #ddd;
  padding: 10px;
  cursor: pointer;
}

.card-header input[type="checkbox"] {
  display: none; /* Hide the checkbox */
}

.card-header input[type="checkbox"]:checked + label + .card-content {
  max-height: 500px; /* Adjust as needed */
}

.card-content {
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition for max-height */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-header">
    <input type="checkbox" id="expandCard">
    <label for="expandCard">Click to Expand</label>
  </div>
  <div class="card-content">
    <p>This is some hidden content that will be revealed when the card is expanded.  You can add as much content here as you like.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed euismod, nisl vel elementum consequat, nibh diam laoreet nisl, et consequat nibh diam at nibh. </p>
  </div>
</div>


</body>
</html>
```

**Explanation:**

1. **HTML Structure:**  We have a `div` with class `card` containing a header (`card-header`) and content (`card-content`). The header includes a hidden checkbox and a label acting as the clickable element.
2. **CSS Transitions:**  The `transition` property is used on both `.card` and `.card-content` to smoothly animate the height change over 0.3 seconds.
3. **Checkbox as Toggle:** The checkbox's `:checked` state is used to control the expansion.  When checked, it styles the `card-content` to have a maximum height, revealing the content.
4. **`max-height` and `overflow: hidden`:** We initially set `max-height` to 0, hiding the content.  `overflow: hidden` prevents content from spilling out when the card is expanded.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

