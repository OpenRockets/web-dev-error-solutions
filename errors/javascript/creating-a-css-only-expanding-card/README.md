# 🐞 Creating a CSS-Only Expanding Card


This document details how to create an expanding card effect using only CSS.  This effect is achieved without JavaScript, relying solely on CSS transitions and the `:hover` pseudo-class. The card expands horizontally when hovered over, revealing hidden content.  We'll use plain CSS for this example, showcasing a clean and efficient approach.

**Description of the Styling:**

The styling uses a simple card structure with a container div and inner divs for the visible and hidden content.  Key CSS properties include:

* `transition`: This provides a smooth animation when hovering over the card.
* `width`: The initial and expanded widths are controlled to create the expansion effect.
* `overflow`: Hidden content is initially concealed and revealed on expansion.
* `:hover`:  Triggers the expansion effect when the mouse hovers over the card.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 20px;
  width: 200px;
  transition: width 0.3s ease-in-out; /* Smooth transition for width */
  overflow: hidden; /* Hide content that overflows */
}

.card:hover {
  width: 400px; /* Expand on hover */
}

.card-content {
  display: flex;
  flex-direction: column;
}

.card-hidden {
  display:none;
}

.card:hover .card-hidden{
  display:block;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Card Title</h3>
    <p>This is some visible content.</p>
    <div class="card-hidden">
      <p>This content is hidden until the card is hovered over.</p>
      <p>More hidden details here...</p>
    </div>
  </div>
</div>

</body>
</html>
```


**Explanation:**

1. **The `card` class:**  Sets the basic styling for the card (background, border, padding, etc.).  The `transition` property is crucial for the animation.  `overflow:hidden` ensures the hidden content stays out of view before expansion.
2. **The `:hover` pseudo-class:** This targets the card when the mouse is hovering over it.  It changes the `width` to trigger the expansion.
3. **The `card-hidden` class:** This class initially hides the content using `display:none;`. The `:hover` on the `.card` changes the display of `.card-hidden` to `block;` to reveal the hidden content.

**Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on the `:hover` pseudo-class:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:hover](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover)
* **CSS-Tricks (various articles on CSS animations and effects):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

