# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  This effect reveals additional content within a card when it's clicked, without using JavaScript. We'll leverage CSS transitions and the `:target` pseudo-class for this.


**Description of the Styling:**

This effect utilizes a simple HTML structure with a container `<div>`, a clickable header `<button>`, and a section for the expandable content `<div>`.  CSS is used to style the card, hide the content initially, and smoothly reveal it upon clicking the header. The `:target` pseudo-class and a unique ID are used to control the visibility based on the URL hash.  We'll also use CSS transitions for a smooth animation.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden; /* Hide content that extends beyond card boundaries */
  width: 300px;
  transition: max-height 0.5s ease-in-out; /* Smooth transition for height change */
}

.card-header {
  background-color: #4CAF50;
  color: white;
  padding: 10px;
  cursor: pointer;
  text-align: center;
}

.card-content {
  padding: 10px;
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.5s ease-in-out; /* Smooth transition for height change */
}

.card.active .card-content {
  max-height: 200px; /* Adjust as needed */
}
</style>
</head>
<body>

<div class="card" id="myCard">
  <button class="card-header" onclick="location.hash = 'content';">Click to Expand</button>
  <div class="card-content" id="content">
    This is the expandable content.  Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`card` class:** Styles the overall card appearance. `overflow: hidden` is crucial to prevent content from spilling outside the card during the transition.
* **`card-header` class:** Styles the clickable header.
* **`card-content` class:**  Contains the expandable content.  `max-height: 0` initially hides the content, and `overflow: hidden` prevents it from overflowing.  The transition property ensures smooth animation.
* **`.card.active .card-content`:** This targets the `card-content` when the parent `card` has the class `active`.  This class is added when the URL hash changes to '#content'  (triggered by the `onclick` event).  We set a `max-height` to reveal the content.
* **`onclick="location.hash = 'content';"`:** This line updates the URL hash when the header is clicked.  This triggers the `.active` class via the `:target` pseudo-class which is implicitly applied to the `#content` element when it's the target of a hash link.


**Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on `:target` Pseudo-class:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* **Understanding CSS Selectors:** Numerous tutorials are available online by searching "CSS Selectors".

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

