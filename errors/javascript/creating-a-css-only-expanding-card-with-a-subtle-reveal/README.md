# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required!  The effect involves a card that smoothly expands on hover, revealing additional content. This uses pure CSS3 transitions and transformations.

**Description of the Styling:**

The card is designed with a simple, clean look.  On hover, the card expands horizontally, revealing hidden content smoothly thanks to the CSS transitions. We use a subtle box-shadow to enhance the 3D effect and give the card more depth.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  background-color: #f0f0f0;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows initially */
  transition: width 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transition for width and box shadow */
}

.card:hover {
  width: 400px; /* Expand on hover */
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Increased box shadow on hover */
}

.card-content {
  padding: 10px;
}

.card-content-hidden {
  display: none; /* Hidden content initially */
}

.card:hover .card-content-hidden {
  display: block; /* Show hidden content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some initial card content.</p>
  </div>
  <div class="card-content card-content-hidden">
    <p>This content is revealed on hover.</p>
    <p>It expands the card smoothly.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This is crucial for the smooth animation.  It specifies that the `width` and `box-shadow` properties should transition over 0.3 seconds using an ease-in-out timing function.
* **`:hover` pseudo-class:** This targets the card when the mouse is hovering over it.
* **`overflow: hidden;`:** This prevents the hidden content from being visible before the hover effect.
* **`display: none;` and `display: block;`:**  These control the visibility of the hidden content.  `display: none;` hides the element completely, while `display: block;` makes it visible.

**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) (While not directly used here, understanding transforms is helpful for more advanced card animations)
* **CSS-Tricks:**  [https://css-tricks.com/](https://css-tricks.com/) (A great resource for learning CSS techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

