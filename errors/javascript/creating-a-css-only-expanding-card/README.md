# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically when hovered over, revealing hidden content.  This technique uses only CSS transitions and avoids JavaScript for a lightweight and performant solution. We'll utilize standard CSS3 properties.


**Description of the Styling:**

The card is styled using a simple container (`div`) with a specific height. The content to be revealed is initially hidden using `overflow: hidden;`. On hover, the height of the container is increased using the `:hover` pseudo-class and CSS transitions, creating a smooth expanding animation.  We’ll also add some basic styling for aesthetics.


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
  overflow: hidden; /* Hide content initially */
  transition: height 0.3s ease-in-out; /* Smooth transition */
  width: 300px;
  height: 100px; /* Initial height */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.card:hover {
  height: 250px; /* Height when hovered */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
}

.hidden-content {
  display: none; /* Initially hide the extra content */
}

.card:hover .hidden-content {
  display: block; /* Show on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p>This is some initial card content.</p>
    <div class="hidden-content">
      <p>This is the extra content that will be revealed on hover.</p>
      <p>More information can be added here.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`overflow: hidden;`:** This prevents the initially hidden content from overflowing the card's boundaries.
* **`transition: height 0.3s ease-in-out;`:** This creates a smooth transition effect when the `height` property changes. The `0.3s` is the duration, and `ease-in-out` is the timing function.
* **`:hover { height: 250px; }`:** This increases the height of the card on hover, revealing the hidden content.
* **`.hidden-content`:** This class hides the extra content initially, and the `:hover` pseudo-class in conjunction with this class shows the hidden content.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS-Tricks:**  (Search for "CSS only hover effects" or "CSS transitions")  [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

