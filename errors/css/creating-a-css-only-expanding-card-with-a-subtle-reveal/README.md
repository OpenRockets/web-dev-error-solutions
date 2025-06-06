# 🐞 Creating a CSS-Only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS. The card expands to reveal additional content on hover, employing a smooth transition for a polished user experience.  We'll be using plain CSS (no CSS preprocessors like Sass or Less, and no frameworks like Tailwind CSS) for this example to demonstrate the core concepts.

**Description of the Styling:**

The card uses a single `<div>` element to contain the entire structure.  The front of the card displays a title and a brief summary.  On hover, the card expands vertically, revealing hidden content below.  The expansion is animated using CSS transitions.  A subtle shadow effect is added to enhance the three-dimensional look.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide the content initially */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: 400px; /* Expand on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.card-summary {
  margin-bottom: 20px;
}

.card-details {
  height: 0; /* Initially hidden */
  overflow: hidden; /* Hide overflow */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover .card-details {
  height: 150px; /* Reveal details on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-summary">This is a simple example of an expanding card created using only CSS.  Hover over the card to see it in action!</p>
    <div class="card-details">
      <p>This is the hidden content that is revealed when you hover over the card. You can add any content you want here, like more details, images, or anything else.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`overflow: hidden;`**: This is crucial for hiding the content initially and preventing the card from expanding beyond its initial height before the hover effect is triggered.
* **`transition: height 0.3s ease-in-out;`**: This line adds a smooth transition to the height change, making the expansion visually appealing.  Adjust the duration (`0.3s`) and easing function (`ease-in-out`) to your liking.
* **`.card:hover`**: This selector targets the `.card` element when the mouse hovers over it.
* **`height: 0;` (on `.card-details`)**:  Keeps the details section collapsed initially.
* **`height: 150px;` (on `.card:hover .card-details`)**: Sets the height when hovering to reveal the content. Adjust this value as needed.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks - CSS Transitions and Transforms:** [https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

