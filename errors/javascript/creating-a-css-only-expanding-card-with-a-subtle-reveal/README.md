# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details how to create an expanding card effect using only CSS.  The card expands to reveal hidden content upon hover, offering a smooth, visually appealing transition.  We'll leverage CSS transitions and transforms to achieve this effect without JavaScript.

## Description of the Styling

The card will initially appear compact, displaying only a title and a small preview image. On hover, the card will smoothly expand vertically, revealing additional content (a longer description in this example). The expansion is accompanied by a subtle fade-in effect for the expanded content.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 150px;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden;
  transition: height 0.3s ease-in-out; /* Smooth height transition */
}

.card:hover {
  height: 300px; /* Expanded height on hover */
}

.card-content {
  padding: 10px;
}

.card-title {
  font-weight: bold;
}

.card-image {
  width: 100%;
  height: 100px;
  object-fit: cover;
  margin-bottom: 10px;
}

.card-description {
  opacity: 0;
  transition: opacity 0.3s ease-in-out; /* Smooth opacity transition */
}

.card:hover .card-description {
  opacity: 1; /* Fade in description on hover */
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/300x100" alt="Card Image" class="card-image">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-description">This is a longer description that will be revealed when you hover over the card.  It smoothly fades in to enhance the user experience.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`transition: height 0.3s ease-in-out;`:** This line applies a smooth transition to the `height` property, making the expansion visually appealing.  The `0.3s` specifies the duration, and `ease-in-out` defines the easing function.
* **`height: 300px;` (inside `:hover`):** This increases the card's height on hover, revealing the hidden content.
* **`overflow: hidden;`:** This prevents content from overflowing the card's initial boundaries before expansion.
* **`opacity: 0;` and `transition: opacity 0.3s ease-in-out;` (on `.card-description`):** These lines control the fade-in effect for the description.  Initially, it has zero opacity (hidden), and the transition smoothly changes its opacity to 1 (fully visible) on hover.


## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (A great resource for various CSS techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

