# 🐞 Creating a CSS-only Expanding Card


This document details how to create an expanding card effect using only CSS.  This effect is achieved without JavaScript, relying solely on CSS transitions and pseudo-elements.  The card expands vertically to reveal additional content when hovered.

**Description of the Styling:**

The card uses a simple design.  The main content is initially visible. On hover, a pseudo-element (`::before`) expands downwards, revealing hidden content.  This is achieved using `height` transitions and clever positioning.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  background-color: #f2f2f2;
  border-radius: 5px;
  overflow: hidden; /* Hide the expanding pseudo-element initially */
  position: relative; /* Required for absolute positioning of the pseudo-element */
  transition: 0.3s ease-in-out; /* Smooth transition for expansion */
}

.card:hover {
  box-shadow: 0 10px 20px rgba(0,0,0,0.1); /* Add shadow on hover */
}

.card-content {
  padding: 20px;
}

.card::before {
  content: "";
  position: absolute;
  top: 100%; /* Start at the bottom */
  left: 0;
  width: 100%;
  height: 0; /* Initially hidden */
  background-color: #fff;
  transition: height 0.3s ease-in-out; /* Smooth height transition */
}

.card:hover::before {
  height: 100px; /* Expand to reveal hidden content */
}

.hidden-content {
  padding: 10px;
  background-color: #fff;
  margin-top: 10px; /* Add some spacing from the main content*/

}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is the main content of the card.</p>
  </div>
  <div class="hidden-content">
    <p>This is the hidden content that appears on hover.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`overflow: hidden;` on `.card`:** This is crucial. It hides the `::before` pseudo-element until it's expanded.
* **`position: relative;` on `.card`:** This allows the absolutely positioned pseudo-element to be relative to the card.
* **`::before` pseudo-element:** This creates an invisible element at the bottom. Its `height` is manipulated on hover.
* **`transition` property:** This provides the smooth animation for both the box-shadow and the height of the pseudo-element.
* **`height: 0;` initially:** Keeps the hidden content out of sight until hover.
* **`height: 100px;` on hover:** This expands the pseudo-element, revealing the hidden content. Adjust `100px` to control the expansion height.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks (various articles on CSS animations and effects):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

