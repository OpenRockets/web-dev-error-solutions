# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  This effect is achieved without JavaScript, relying solely on CSS transitions and pseudo-elements. The card expands to reveal additional content when hovered over.


**Description of the Styling:**

This design uses a simple card structure with a main content area and a hidden expandable section.  On hover, the card expands vertically, revealing the hidden content smoothly thanks to CSS transitions. We'll leverage `::before` and `::after` pseudo-elements to achieve a clean visual effect without extra HTML.


**Full Code:**

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
  overflow: hidden; /* Hide content overflowing on expansion */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: 300px; /* Expanded height on hover */
}

.card-content {
  padding: 10px;
}

.card-expand {
  height: 150px; /* Initial height of expandable section */
  background-color: #e0e0e0;
  overflow: hidden;
  transition: height 0.3s ease-in-out;
}

.card:hover .card-expand {
  height: 150px; /* Expanded height on hover */
}

.card h2 {
  margin-top: 0;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>Some initial content.</p>
  </div>
  <div class="card-expand">
    <p>This is the expanded content that appears on hover.</p>
    <p>More expanded content here.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden` prevents content from spilling outside the card boundaries before expansion. The `transition` property ensures a smooth animation when the height changes.

* **`.card:hover`:** This selector targets the card when the mouse hovers over it, increasing its height to reveal the hidden content.

* **`.card-content`:** Styles the initial visible content of the card.

* **`.card-expand`:** This class styles the expandable section, initially hidden by the `height` property and `overflow: hidden`. The `transition` property ensures smooth height changes on hover.

* **`.card:hover .card-expand`:**  When hovering over the card, this selector changes the height of the `.card-expand` div, revealing its content.


**Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **Understanding CSS Selectors:** [MDN Web Docs - Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

