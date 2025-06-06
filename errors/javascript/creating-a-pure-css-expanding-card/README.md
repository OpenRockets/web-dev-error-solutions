# 🐞 Creating a Pure CSS Expanding Card


This document details the creation of an expanding card using only CSS.  No JavaScript is required. This effect involves a card that reveals more content upon hovering over it.  We'll be using CSS3 transitions and transforms to achieve this smooth animation.


**Description of the Styling:**

The card uses a simple layout with a main container, an image, and a text section. On hover, the card scales up slightly, while the text area expands vertically, revealing hidden content.  This is achieved with CSS transitions and transforms applied to different elements.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 200px;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease-in-out; /* Smooth transition for scaling */
}

.card:hover {
  transform: scale(1.05); /* Scale up on hover */
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-content {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  padding: 10px;
  transform: translateY(100%); /* Initially hidden */
  transition: transform 0.3s ease-in-out; /* Smooth transition for expansion */
}

.card:hover .card-content {
  transform: translateY(0); /* Reveal content on hover */
}


.card-text {
  overflow: hidden;
  max-height: 0; /* Initially hidden */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for text expansion */

}

.card:hover .card-text{
  max-height: 100px; /* Reveal text on hover */
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/300x200" alt="Card Image" class="card-image">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-text">This is some hidden text that will reveal itself when you hover over the card.  This demonstrates a simple expanding card effect using only CSS.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`transition` property:**  This is crucial for the smooth animation. It's applied to the `transform` property of the `.card` class for scaling and to the `transform` and `max-height` properties of `.card-content` and `.card-text` respectively for the expansion effect.
* **`transform: scale(1.05)`:** This scales the card up slightly on hover.
* **`transform: translateY(100%)`:** This initially hides the card content by moving it off-screen. On hover, `translateY(0)` brings it back into view.
* **`max-height`:** Controls the height of the text. By setting it to 0 initially and then increasing it on hover, we create a gradual revealing of the hidden text content.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

