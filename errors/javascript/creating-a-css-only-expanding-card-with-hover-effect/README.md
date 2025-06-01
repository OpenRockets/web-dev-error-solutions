# 🐞 Creating a CSS-only Expanding Card with Hover Effect


This document details a CSS-only solution for creating an expanding card with a hover effect.  No JavaScript is required.  The effect uses CSS transitions and pseudo-elements to achieve a smooth and visually appealing animation.


## Description of the Styling

The card consists of a main container (`<div class="card">`) that holds an image and some text. On hover, the card expands horizontally, revealing more information. The expansion is achieved by animating the width of the card and the opacity of the text content.  A subtle shadow effect is added to enhance the three-dimensional look.


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
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Prevents content overflow during expansion */
  transition: width 0.3s ease-in-out; /* Smooth transition for width change */
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensures image covers the entire container */
}

.card-content {
  opacity: 0; /* Initially hidden */
  padding: 10px;
  transition: opacity 0.3s ease-in-out; /* Smooth transition for opacity change */
}

.card:hover {
  width: 400px; /* Expands on hover */
}

.card:hover .card-content {
  opacity: 1; /* Reveals content on hover */
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/200x150" alt="Card Image">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some sample text for the card content.  It will appear on hover.</p>
  </div>
</div>

</body>
</html>
```

Remember to replace `"https://via.placeholder.com/200x150"` with the actual URL of your image.


## Explanation

* **`transition` property:** This is crucial for creating the animation effect. It specifies the properties to animate (`width`, `opacity`), the duration (`0.3s`), and the timing function (`ease-in-out`).
* **`overflow: hidden;`:** This prevents the image from overflowing the card container during the expansion.
* **`:hover` pseudo-class:** This selector targets the element when the mouse hovers over it.
* **`object-fit: cover;`:** This ensures that the image covers the entire area of its container, maintaining its aspect ratio.
* **`box-shadow`:** Adds a subtle shadow for a more realistic look.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS-Tricks:** (Search for "CSS transitions" or "hover effects" on their site)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

