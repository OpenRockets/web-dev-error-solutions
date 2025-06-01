# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  No JavaScript is required! This utilizes CSS transitions and transforms to achieve a smooth, visually appealing animation.

**Description of the Styling:**

The styling focuses on creating a card with a subtle hover effect.  On hover, the card expands slightly, revealing more content that was initially hidden.  This is achieved using CSS transitions to smoothly animate the changes in `transform: scale()` and the visibility of hidden content.


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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  padding: 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  overflow: hidden; /* Hide initially hidden content */
  width: 300px;
}

.card:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.card-content {
  height: 100px;
  overflow: hidden;
}

.card-content.show {
  height: auto; /* Expand height on hover */
  transition: height 0.3s ease; /* Smooth height transition */
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
}

.card:hover .card-content {
    height: auto; /* Expand height on hover */
}


</style>
</head>
<body>

<div class="card">
  <div class="card-title">Expanding Card</div>
  <div class="card-content">
    <p>This is some example text that is initially hidden.  On hover, the card will expand to reveal this content.</p>
    <p>More example text... </p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`transition: transform 0.3s ease, box-shadow 0.3s ease;`**: This line adds smooth transitions to the `transform` (scaling) and `box-shadow` properties, making the hover effect fluid.
* **`transform: scale(1.05);`**: This line scales the card up slightly on hover.
* **`overflow: hidden;`**: This initially hides the extra content within `card-content`.
* **`height: auto;`**: This allows the content to expand to its natural height when `show` class is added or on hover.  This combined with the transition on height creates the expanding animation.
* **`transition: height 0.3s ease;`**: Smooths the expansion of the height.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

