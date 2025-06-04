# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content.  This example utilizes only CSS, avoiding the need for JavaScript, making it lightweight and performant.  No specific CSS framework (like Tailwind CSS) is used to emphasize the fundamental CSS concepts.

**Description of the Styling:**

The card is created using a single `<div>` element with nested divs for the visible and hidden content.  The key styling involves using the `max-height` property along with transitions to animate the expansion.  The `overflow: hidden;` property ensures that the hidden content initially remains invisible.  On hover, the `max-height` is increased to allow the hidden content to become visible, smoothly transitioning thanks to the transition property.

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
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Height on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
}

.hidden-content {
  display: block; /* Necessary for the transition to work correctly */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">My Expanding Card</h2>
    <p>This is some visible content.</p>
    <div class="hidden-content">
      <p>This is the hidden content that appears on hover.</p>
      <p>More hidden text here...</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`max-height: 100px;`**: This limits the initial height of the card.
* **`transition: max-height 0.3s ease-in-out;`**: This applies a smooth transition to the `max-height` property over 0.3 seconds. The `ease-in-out` timing function provides a natural easing effect.
* **`overflow: hidden;`**: This hides any content that exceeds the `max-height`.
* **`.card:hover { max-height: 300px; }`**: This increases the `max-height` on hover, revealing the hidden content.
* **`display: block;` on `.hidden-content`**:  Ensures the hidden content is treated as a block-level element, which is essential for the `max-height` property to work correctly.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Overflow:** [https://developer.mozilla.org/en-US/docs/Web/CSS/overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
* **CSS-Tricks (General CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

