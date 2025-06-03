# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details a CSS-only solution to create an expanding card effect.  The card expands smoothly when hovered, revealing hidden content with a subtle animation.  We'll use only CSS, requiring no JavaScript. This example uses plain CSS, but could be easily adapted to a framework like Tailwind CSS.

**Description of the Styling:**

The card utilizes transitions for smooth animation on hover.  The main container has a fixed height, initially showing only the title and a small portion of the content. On hover, the height expands, revealing the full content.  A subtle box-shadow is added for visual depth, and the content inside smoothly transitions with the card expansion.

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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  height: 150px; /* Initial height */
  width: 300px;
}

.card:hover {
  height: 300px; /* Height on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1em;
  line-height: 1.6;
  transition: opacity 0.3s ease-in-out; /* Smooth transition for opacity change */
  opacity: 1; /* Initially visible */
}


.card:hover .card-text {
    opacity: 1; /* Fully visible on hover */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is the content of the expanding card.  It starts hidden and expands smoothly on hover.  You can add as much text as you like.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`transition: height 0.3s ease-in-out;`**: This line is crucial. It tells the card to smoothly transition its `height` property over 0.3 seconds using an "ease-in-out" timing function.  This creates the smooth expansion effect.
* **`height: 150px;` and `height: 300px;`**: These set the initial and hover heights of the card, respectively.  Adjust these values to change the expansion size.
* **`overflow: hidden;`**: This prevents the content from overflowing the card before the expansion.
* **`box-shadow`**: This adds a subtle shadow for visual enhancement.
* The `transition: opacity 0.3s ease-in-out;` on `.card-text` provides a smooth fade-in effect for the content on hover.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks - Learn CSS:** [https://css-tricks.com/](https://css-tricks.com/) (Search for tutorials on transitions and animations)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

