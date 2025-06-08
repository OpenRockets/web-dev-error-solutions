# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically to reveal hidden content when hovered over.  No JavaScript is required.  We'll use pure CSS3 for this effect.


**Description of the Styling:**

This effect is achieved using CSS transitions and the `max-height` property.  Initially, the card has a small `max-height`, hiding its content.  On hover, the `max-height` is set to a larger value (or `auto` to allow it to expand to its natural height), revealing the hidden content smoothly thanks to the transition.  We'll also add some subtle visual cues to enhance the user experience.


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
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initially, only show a small portion */
}

.card:hover {
  max-height: auto; /* Expand on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
}

.card-text {
  font-size: 14px;
  line-height: 1.5;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is the content of the expanding card.  It initially starts hidden and reveals itself on hover.  This effect is achieved using pure CSS, making it lightweight and efficient.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the main card container.  `overflow: hidden` prevents the content from spilling outside the card's boundaries before expansion.  `transition` defines the smooth animation on `max-height` change.  `max-height: 100px;` sets the initial height, hiding most of the content.
* **`.card:hover`:** This selector targets the card when the mouse hovers over it. `max-height: auto;` allows the card to expand to its natural height.
* **`.card-content`, `.card-title`, `.card-text`:** These classes style the inner content for better readability and structure.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS `max-height` Property:** [MDN Web Docs - `max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* **CSS Selectors:** [MDN Web Docs - Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

