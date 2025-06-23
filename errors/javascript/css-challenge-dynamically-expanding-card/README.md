# 🐞 CSS Challenge:  Dynamically Expanding Card


This challenge involves creating a card that expands vertically when hovered over, revealing hidden content. We'll use CSS3 transitions and transforms to achieve a smooth and engaging animation.  No JavaScript is required.


## Description of the Styling

The card will start with a minimal height, displaying only a title and a small image. On hover, the card's height will smoothly increase to reveal additional text content that was initially hidden using `max-height` and `overflow: hidden`. We'll use a subtle background color change and a shadow effect to enhance the visual feedback.


## Full Code (CSS only)


```css
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content beyond the initial height */
  transition: max-height 0.3s ease-in-out, background-color 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transitions */
  max-height: 100px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Expanded height on hover */
  background-color: #e0e0e0;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.card-image {
  width: 100%;
  height: auto;
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
```

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
  /* CSS from above goes here */
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/350x150" alt="Card Image" class="card-image">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p class="card-text">This is some example text that will be revealed when you hover over the card.  It's hidden initially to create the expanding effect.  You can add more content here as needed.</p>
  </div>
</div>

</body>
</html>
```



## Explanation

* **`transition` property:** This is crucial for the animation. It specifies which properties (`max-height`, `background-color`, `box-shadow`) should animate, the duration (`0.3s`), and the easing function (`ease-in-out`).
* **`max-height` property:** Controls the initial and expanded heights of the card. The `overflow: hidden` ensures that content beyond the `max-height` is initially hidden.
* **`hover` pseudo-class:**  Applies styles when the mouse hovers over the `.card` element.
* **`box-shadow`:**  Adds a subtle shadow to enhance the card's appearance and the hover effect.


## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

