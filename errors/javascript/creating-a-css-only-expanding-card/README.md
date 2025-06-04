# 🐞 Creating a CSS-only Expanding Card


This document details the creation of an expanding card effect using only CSS.  No JavaScript is required! This effect showcases the power of CSS transitions and transforms to create engaging user interface elements. The card expands on hover, revealing more content.

**Description of the Styling:**

The styling uses a combination of CSS transitions, transforms (`scale`), and pseudo-elements (`::before` and `::after`) to achieve the expanding effect.  The card itself is styled with a simple box-shadow and padding.  The hidden content is initially hidden with `max-height: 0; overflow: hidden;` and then revealed using `max-height` set dynamically with the height of the content on hover. The subtle animation is added via the transition property applied to max-height.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: box-shadow 0.3s ease, transform 0.3s ease; /*Added transition for smoother effects*/
  width: 300px;
}

.card:hover {
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
  transform: translateY(-2px); /* Added slight lift on hover */
}


.card-content {
  padding: 20px;
}

.card-content p {
  margin-bottom: 10px;
}

.card-hidden {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.5s ease-out; /* Added transition for smooth expansion */
}

.card:hover .card-hidden {
  max-height: 200px; /* Adjust as needed to fit your content */
}


/* Optional styling to make example visually better */
.card-header{
    background-color: #f0f0f0;
    padding: 10px;
    font-weight: bold;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">Expanding Card</div>
  <div class="card-content">
    <p>This is some visible text content of the card.</p>
  </div>
  <div class="card-hidden">
    <p>This content is initially hidden and reveals on hover.</p>
    <p>You can add more content here as needed.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

1. **`card` class:**  This styles the overall card with background color, border radius, box-shadow, and sets up transitions. The `transform: translateY(-2px);` on hover adds a subtle lift effect, enhancing the visual appeal.

2. **`card-content` class:**  This styles the visible content within the card.

3. **`card-hidden` class:** This is crucial.  `max-height: 0;` initially hides the content.  `overflow: hidden;` prevents any overflow from being visible. The `transition` property enables a smooth expansion.

4. **`card:hover .card-hidden`:**  This selector targets the `.card-hidden` element *only* when the `.card` is hovered.  `max-height: 200px;`  reveals the hidden content.  Adjust the `200px` value to fit your content height.



**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** (Search for "CSS transitions" or "CSS transforms" on their site for numerous tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

