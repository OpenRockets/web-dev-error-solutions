# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript is required!  We'll leverage CSS transitions and pseudo-elements to achieve a smooth and visually appealing expansion animation. This example uses plain CSS3, but the concepts are easily adaptable to frameworks like Tailwind CSS.

**Description of the Styling:**

The card starts in a compact state. On hover, the card expands to reveal more content. This expansion is achieved by animating the height of the card and transitioning the opacity of hidden content. The background color changes subtly on hover for added visual feedback.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease, background-color 0.3s ease; /* Smooth transition */
  width: 300px;
  height: 100px; /* Initial height */
}

.card:hover {
  background-color: #e0e0e0;
  height: 250px; /* Expanded height */
}

.card-content {
  padding: 15px;
  opacity: 0; /* Initially hidden */
  transition: opacity 0.3s ease; /* Smooth transition */
}

.card:hover .card-content {
  opacity: 1; /* Shown on hover */
}

.card-title {
  font-weight: bold;
  margin-bottom: 5px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p>This is some extra content that will be revealed when the card is hovered over.</p>
    <p>More content here...</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This is crucial for the animation. It specifies that the `height` and `background-color` properties will smoothly transition over 0.3 seconds using an "ease" timing function.  The `opacity` transition is applied to the card content.
* **`height` property:**  The initial height is set, and then increased on hover to create the expansion effect.
* **`overflow: hidden;`:** This prevents content from spilling outside the card boundaries before it expands.
* **`opacity` property:** Controls the visibility of the inner content. Initially set to 0, it transitions to 1 on hover, revealing the hidden text.
* **`card-content` class:** This class targets the content that should be revealed.

**Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks:**  (Search for "CSS transitions" or "CSS animations" on their site)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

