# 🐞 Creating a CSS-Only Expanding Card with a Subtle Reveal


This document details how to create an expanding card using only CSS. The card expands smoothly when hovered over, revealing additional content.  We'll utilize CSS transitions and transforms for a clean, elegant effect.  This example uses plain CSS, but could easily be adapted to a CSS framework like Tailwind CSS.


## Description of the Styling

The card starts collapsed. On hover, the card's height expands, and the hidden content smoothly slides into view. We use a `transform: scale()` to add a subtle "pop" effect during the expansion. A subtle box shadow is added to enhance the 3D appearance.

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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that extends beyond the initial height */
  transition: height 0.3s ease-in-out, transform 0.3s ease-in-out; /* Smooth transition */
  height: 100px; /* Initial height */
}

.card:hover {
  height: 200px; /* Height on hover */
  transform: scale(1.02); /* Subtle scaling effect */
}

.card-content {
  padding: 15px;
}

.card-content h2 {
  margin-top: 0;
}

.hidden-content {
  height: 100px;
  overflow: hidden;
  transition: max-height 0.3s ease-in-out;
  max-height: 0; /* Initially hidden */
}


.card:hover .hidden-content {
  max-height: 100px; /* Show on hover */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some visible content.</p>
    <div class="hidden-content">
      <p>This is the hidden content that appears on hover.</p>
      <p>More hidden content here.</p>
    </div>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`transition` property:** This is crucial for the smooth animation.  It specifies that the `height` and `transform` properties should transition over 0.3 seconds using an "ease-in-out" timing function.
* **`height` property:** Controls the initial and expanded height of the card.
* **`transform: scale(1.02)`:** This adds a slight zoom effect on hover, making the expansion feel more dynamic.
* **`overflow: hidden`:** Prevents content from spilling outside the card's boundaries.
* **`max-height` property and `.hidden-content`:**  This is used in conjunction with the transition to smoothly reveal and hide the additional content.  The `max-height` is initially 0, and then expands to reveal the content on hover.


## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** (Search for "CSS transitions" or "CSS animations" on their website for many tutorials) [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

