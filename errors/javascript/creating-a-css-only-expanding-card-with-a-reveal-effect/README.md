# 🐞 Creating a CSS-Only Expanding Card with a Reveal Effect


This document details how to create an expanding card effect using only CSS.  The card initially shows a minimal preview and expands to reveal more content on hover. This example uses pure CSS3, avoiding JavaScript for a lightweight and performant solution.


## Description of the Styling

The styling uses a combination of CSS transitions, transforms, and pseudo-elements (`::before` and `::after`) to achieve the expanding card effect.  The card starts with a smaller height and, on hover, expands vertically while smoothly fading in additional content. A subtle shadow is added to enhance the three-dimensional appearance.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  background-color: #f2f2f2;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: 300px; /* Expand height on hover */
}

.card-content {
  padding: 10px;
  opacity: 1;
  transition: opacity 0.3s ease-in-out; /* Smooth transition for opacity change */
}

.card:hover .card-content {
  opacity: 1; /* Ensure content is fully visible on hover */
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
}

.card-text {
  font-size: 14px;
  line-height: 1.5;
}

.card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.3); /*Overlay during transition*/
    opacity: 1;
    transition: opacity 0.3s ease-in-out;
}

.card:hover::before {
    opacity: 0;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-text">This is some sample text for the card.  You can add more content here to make the expansion effect more pronounced.</p>
    <p class="card-text">More text...</p>
  </div>
</div>

</body>
</html>
```


## Explanation

1. **Base Styling:** The `.card` class sets the initial dimensions, background color, border radius, and shadow of the card. `overflow: hidden` prevents content from overflowing the initial bounds.

2. **Hover Effect:** The `:hover` pseudo-class increases the `height` of the card on mouse hover, triggering the transition.

3. **Content Transition:** The `.card-content` and `.card::before` classes handle the smooth appearance of the content using opacity transitions. Initially, the overlay hides the full content, and on hover, the overlay fades out.

4. **Transitions:** The `transition` property on height and opacity enables smooth animations.  `ease-in-out` provides a natural easing effect.

## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** (Search for "CSS only card hover effects" for various examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

