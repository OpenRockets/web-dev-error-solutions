# 🐞 Creating a CSS-only Expanding Card with a Reveal Effect


This document details the creation of an expanding card using only CSS.  The card initially displays a concise title and image; upon hover, it expands to reveal additional content. We'll use pure CSS3, avoiding JavaScript for a lightweight and performant solution.

## Description of the Styling

This effect leverages CSS transitions and transformations to achieve a smooth expanding animation. The card's height dynamically adjusts on hover, revealing hidden content.  We'll also style the card for visual appeal using box-shadow and subtle gradients.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  border-radius: 10px;
  overflow: hidden; /* Hide content that overflows */
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  background: linear-gradient(135deg, #f0f0f0, #e0e0e0);
}

.card:hover {
  height: 400px; /* Expand on hover */
}

.card-image {
  height: 200px;
  background-size: cover;
  background-position: center;
}

.card-content {
  padding: 20px;
  height: 0; /* Initially hidden */
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover .card-content {
  height: 200px; /* Reveal on hover */
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

/* Example image and content */
.card.example1 {
  background-image: url('https://via.placeholder.com/300x200'); /* Replace with your image */
}
.card.example2 {
    background-image: url('https://via.placeholder.com/300x200/FF0000/FFFFFF'); /* Replace with your image */
}

</style>
</head>
<body>

<div class="card example1">
  <div class="card-image"></div>
  <div class="card-content">
    <h2 class="card-title">Card Title 1</h2>
    <p>Some additional text for card 1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
  </div>
</div>
<div class="card example2">
  <div class="card-image"></div>
  <div class="card-content">
    <h2 class="card-title">Card Title 2</h2>
    <p>Some additional text for card 2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
  </div>
</div>


</body>
</html>
```

## Explanation

1. **`card` class:**  Sets the base styles for the card, including width, border radius, box-shadow, and initial height.  The `transition` property is crucial for the smooth animation.
2. **`card:hover`:** Defines the styles applied when the mouse hovers over the card.  The `height` increases, revealing the hidden content.
3. **`card-image` class:** Styles the image within the card.  `background-size: cover` ensures the image scales to fill the container.
4. **`card-content` class:**  Contains the text content.  `height: 0` initially hides it; on hover, the `height` increases to reveal the text.  `overflow: hidden` prevents content from overflowing before it's revealed.
5. **`card-title` class:** Styles the card title.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transformations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Search for "CSS animations" or "CSS transitions" for many tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

