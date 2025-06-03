# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect, where clicking a card reveals more content.  We'll utilize pure CSS3 transitions and transformations to achieve this without JavaScript.


## Description of the Styling

The styling involves a simple card structure with a hidden content area.  On hover or click, we use CSS transitions to smoothly animate the height of the card, revealing the hidden content.  A subtle background color change adds to the visual feedback.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden; /* Hide content initially */
  transition: height 0.3s ease-in-out; /* Smooth transition for height */
  cursor: pointer; /* Indicate it's clickable */
}

.card:hover {
  background-color: #e0e0e0; /* Change background on hover */
}

.card-content {
  padding: 20px;
}

.card-content p {
  margin-bottom: 10px;
}


.card-header {
  background-color: #ccc;
  padding: 10px;
  cursor: pointer;
}

.card-hidden {
  max-height: 0; /* Initially hidden */
  overflow: hidden; /* Hide overflowing content */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for max-height */
}

.card:hover .card-hidden,
.card.active .card-hidden {
  max-height: 500px; /* Expand on hover or when active */
}
.card.active .card-header {
  background-color: lightblue; /* Additional feedback on active state */
}

</style>
</head>
<body>

<div class="card" onclick="this.classList.toggle('active');">
  <div class="card-header">
    <h3>Click to Expand</h3>
  </div>
  <div class="card-hidden">
    <div class="card-content">
      <p>This is some additional content that will be revealed when you click or hover over the card.</p>
      <p>You can add as much content as you like here.</p>
      <p>This is a simple example of a CSS-only expanding card.</p>
    </div>
  </div>
</div>

</body>
</html>
```

## Explanation

1. **`card` class:**  Sets basic styling for the card and applies the `transition` property for smooth height changes.
2. **`card-content` class:** Styles the content inside the card.
3. **`card-hidden` class:** Initially sets `max-height` to 0, hiding the content.  The `transition` property is applied here as well.
4. **`:hover` pseudo-class:**  Changes the background color on hover and increases `max-height` to reveal the hidden content.
5. **`onclick` event:** Uses Javascript to add/remove the `active` class which helps in managing the expanding state even after hover. This improves usability.
6. **`.card.active .card-hidden`:**  This selector targets the `.card-hidden` element only when its parent has the class `active`.


## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** (Search for "CSS expanding card" on their site for many examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

