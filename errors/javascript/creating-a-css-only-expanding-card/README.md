# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically to reveal more content when clicked.  No JavaScript is required. This example uses plain CSS3; however, the concept could easily be adapted to a CSS framework like Tailwind CSS.

**Description of the Styling:**

The core technique uses CSS transitions and the `max-height` property.  The card starts with a small `max-height`, limiting its visible content. On click, the `max-height` is dynamically changed to allow the card to expand to its full content height.  The transition smooths the expansion animation.  We also style the card with some basic visual enhancements.


**Full Code:**

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
  overflow: hidden; /* Hide content that overflows max-height */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  cursor: pointer;
  max-height: 100px; /* Initial height */
  width: 300px;
  padding:10px;
}

.card.expanded {
  max-height: 500px; /* Expanded height */
}

.card-content {
  padding: 10px;
}
</style>
</head>
<body>

<div class="card" onclick="this.classList.toggle('expanded')">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some sample text for the card content.  You can add as much text as you need here.  The card will expand to fit the content.</p>
    <p>More text to demonstrate the expansion.</p>
    <p>Even more text!</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the card itself.  `overflow: hidden;` is crucial to prevent content from overflowing before expansion. `transition: max-height 0.3s ease-in-out;`  creates the smooth animation. `max-height: 100px;` sets the initial restricted height.
* **`.card.expanded`:** This class is applied when the card is clicked. `max-height: 500px;` sets the height to allow the full content to be displayed.  You should adjust `500px` to a value larger than your expected maximum content height.
* **`onclick="this.classList.toggle('expanded')"`:** This inline JavaScript (minimal and acceptable for this simple example) toggles the `expanded` class on the card when it is clicked.  For larger projects, consider separating JavaScript logic from HTML.

**Links to Resources to Learn More:**

* [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [CSS max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* [Learn CSS](https://www.freecodecamp.org/learn/responsive-web-design/) (general CSS learning resource)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

