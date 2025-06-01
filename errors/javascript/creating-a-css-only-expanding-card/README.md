# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card using only CSS.  No JavaScript is required!  This effect utilizes CSS transitions and the `:hover` pseudo-class to create a smooth and visually appealing expansion on mouse hover.

**Description of the Styling:**

The card starts in a compact state.  On hover, the card expands horizontally, revealing more content.  This is achieved using CSS transitions on the `width` property and strategically placed content within the card.  We use a simple and clean design, focusing on the expanding functionality itself.  The color scheme is intentionally minimalistic for clarity.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden; /* Prevents content from overflowing during expansion */
  width: 200px;
  transition: width 0.3s ease-in-out; /* Smooth transition on width change */
}

.card:hover {
  width: 400px; /* Expands to double the width on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
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
    <p class="card-text">This card expands horizontally on hover, revealing more content.  This effect is achieved purely with CSS, using transitions and the :hover pseudo-class. No JavaScript is required!</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the main card element.  `overflow: hidden;` is crucial to prevent content from spilling outside the card during the expansion.  The `transition` property smoothly animates the width change over 0.3 seconds.
* **`.card:hover`:** This applies styles when the mouse hovers over the `.card` element.  The `width` is increased, triggering the transition.
* **`.card-content`, `.card-title`, `.card-text`:** These classes style the content within the card for better readability and structure.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **Learn CSS:** [freeCodeCamp's Responsive Web Design Certification](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

