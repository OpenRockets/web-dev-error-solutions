# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  No JavaScript is required.  The effect involves a card that expands vertically when hovered over, revealing additional content.  We'll utilize CSS transitions and the `:hover` pseudo-class to achieve this.


**Description of the Styling:**

The card is structured using a combination of divs. The main container holds the card's content, and the expanding section is contained within a child div. The CSS utilizes `max-height` and transitions to smoothly animate the height change on hover.

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
  overflow: hidden; /* Hide content that overflows */
  transition: all 0.3s ease-in-out; /* Smooth transition */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-expand {
  max-height: 0; /* Initially collapsed */
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
}

.card:hover .card-expand {
  max-height: 200px; /* Expand on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p>This is some introductory text for the card.  It demonstrates a simple expanding card effect created using only CSS.</p>
  </div>
  <div class="card-expand">
    <p>This is the additional content that expands when you hover over the card.  You can add as much content as you want here.</p>
    <p>This extra content adds more visual interest and demonstrates the expanding nature of the card.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the overall card, including background color, border radius, and a crucial `overflow: hidden;` to prevent the expanded content from overflowing before the transition.  The `transition` property ensures a smooth animation.
* **`.card-content`:**  This styles the initial, always visible content of the card.
* **`.card-expand`:** This class styles the expanding section.  `max-height: 0;` keeps it initially collapsed, and `overflow: hidden;` prevents content from peeking out before expansion. The `transition` property is vital for animation.
* **`.card:hover .card-expand`:** This is where the magic happens. The `:hover` pseudo-class targets the `.card` when the mouse hovers over it.  Then, it changes the `max-height` of the `.card-expand` element to `200px`, causing it to smoothly expand due to the transition.  You can adjust `200px` to control the expanded height.



**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - :hover Pseudo-class:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:hover](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

