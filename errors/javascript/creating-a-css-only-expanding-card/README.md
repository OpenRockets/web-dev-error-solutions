# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically when hovered over, revealing additional content.  This effect is achieved using purely CSS, without relying on JavaScript.  We'll leverage CSS transitions and the `:hover` pseudo-class.

**Description of the Styling:**

The card consists of a container div with a fixed height. Inside, a second div contains the main content, initially visible. Below this, a third div contains the expandable content, initially hidden. On hover, we increase the height of the container using a CSS transition for a smooth animation.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 150px; /* Initial height */
  background-color: #f0f0f0;
  border-radius: 8px;
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: 300px; /* Height on hover */
}

.card-content {
  padding: 15px;
}

.expandable-content {
  overflow: hidden;
  height: 0; /* Initially hidden */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover .expandable-content {
  height: 150px; /* Height on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some initial content.</p>
  </div>
  <div class="expandable-content">
    <p>This is the expandable content that appears on hover.  It can be as long as you need it to be.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden;` ensures that the expandable content doesn't initially overflow the card.  `transition: height 0.3s ease-in-out;` sets up a smooth transition for the height change on hover.
* **`.card:hover`:**  This selector targets the card when the mouse hovers over it, increasing its height to reveal the hidden content.
* **`.expandable-content`:** This class styles the initially hidden content.  `height: 0;` makes it invisible, and `transition: height 0.3s ease-in-out;` ensures smooth transition.
* **`.card:hover .expandable-content`:** This selector targets the expandable content when the mouse hovers over the card, setting its height to reveal it.


**Links to Resources to Learn More:**

* [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [CSS-Tricks](https://css-tricks.com/) (A great resource for CSS techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

