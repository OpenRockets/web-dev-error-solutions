# 🐞 Creating a CSS-Only Expanding Card with a Hover Effect


This document details the creation of an expanding card using only CSS.  The card expands on hover, revealing hidden content, providing a smooth and engaging user experience without the need for JavaScript.  This example uses plain CSS3, but similar effects can be achieved with CSS preprocessors like Sass or frameworks like Tailwind CSS.


## Description of the Styling

The card utilizes several CSS techniques to achieve the expanding effect:

* **Transitions:** Smoothly animate the changes in height and opacity.
* **Overflow:** Initially hides the expanded content.
* **Height:** Dynamically adjusts the card's height on hover.
* **Opacity:** Fades in the content as the card expands.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  overflow: hidden; /* Hide content outside the initial height */
  transition: height 0.3s ease-in-out, opacity 0.3s ease-in-out; /* Smooth transitions */
  height: 150px; /* Initial height */
  width: 300px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
}

.card:hover {
  height: 300px; /* Expanded height */
}

.card-content {
  padding: 20px;
  opacity: 1;
  transition: opacity 0.3s ease-in-out; /* Smooth opacity transition */
}

.card-content-hidden {
  opacity: 0; /* Initially hidden */
  transition: opacity 0.3s ease-in-out; /* Smooth opacity transition */
}

.card:hover .card-content-hidden {
  opacity: 1; /* Show on hover */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some initial content.</p>
  </div>
  <div class="card-content card-content-hidden">
    <p>This is the expanded content that appears on hover.</p>
    <p>More details here...</p>
  </div>
</div>

</body>
</html>
```


## Explanation

The core logic lies in the CSS rules for `.card`, `.card:hover`, `.card-content`, and `.card-content-hidden`.  The initial height of the card is set, and the `overflow: hidden` property ensures that the extra content is initially hidden. The `transition` property provides smooth animations for both height and opacity changes.  On hover, the `.card:hover` selector increases the height, revealing the hidden content, and the opacity transition smoothly fades in the hidden content using the `.card-content-hidden` class and its hover modification.


## Links to Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks on Hover Effects:** [https://css-tricks.com/snippets/css/hover-effects/](https://css-tricks.com/snippets/css/hover-effects/)  (Search for expanding card examples)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (Helpful for more advanced layouts)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

