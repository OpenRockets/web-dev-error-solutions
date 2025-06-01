# 🐞 Creating a CSS-Only Expanding Card with Hover Effect


This document details the creation of an expanding card using only CSS.  The card expands on hover, revealing more content. We'll be using CSS3 transitions and transforms to achieve this effect.  No JavaScript is required.


**Description of the Styling:**

The card consists of a container element (`div.card`) containing an image (`img.card-image`), a title (`h2.card-title`), and a description (`p.card-description`).  On hover, the card scales up slightly, and the description smoothly slides down from being hidden. This is all handled via CSS transitions and transforms.  The styling aims for a clean, modern look.


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
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out; /* Smooth transition for scaling */
}

.card:hover {
  transform: scale(1.05); /* Slightly scale up on hover */
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-content {
  position: relative;
  background-color: white; /* Ensure content is visible over image */
  padding: 15px;
  opacity: 0;
  transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out; /* Smooth transition for opacity and sliding */
  transform: translateY(100%); /* Initially hide content */
}

.card:hover .card-content {
  opacity: 1;
  transform: translateY(0); /* Show content on hover */
}

.card-title {
  margin-top: 0;
}
</style>
</head>
<body>

<div class="card">
  <img class="card-image" src="https://via.placeholder.com/300x200" alt="Card Image">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p class="card-description">This is a sample card description.  It expands on hover to reveal more information.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`transition` property:** This is key to the smooth animations.  We apply it to the `transform` property of the `.card` class for scaling and to `opacity` and `transform` of the `.card-content` for the description's slide-down effect.
* **`transform: scale(1.05)`:** This slightly increases the size of the card on hover.
* **`transform: translateY(100%)`:** This initially moves the card content completely off-screen.  On hover, it's reset to `translateY(0)`.
* **`opacity`:** Controls the visibility of the card content, allowing for a fade-in effect.
* **`object-fit: cover`:** Ensures the image fills the entire container, maintaining aspect ratio.
* **`position: relative` on `.card-content` and `overflow: hidden` on `.card`:** These are used in conjunction to ensure the content slides in and out cleanly, hidden from view before the effect starts.

**Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

