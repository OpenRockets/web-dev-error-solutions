# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing additional content.  No JavaScript is required.  This example uses plain CSS3, but could easily be adapted for a framework like Tailwind CSS.

**Description of the Styling:**

The effect is achieved using CSS transitions and the `max-height` property. Initially, the card has a very low `max-height`, hiding the extra content.  On hover, the `max-height` is dynamically set to `auto`, allowing the content to expand naturally.  Smooth transitions are applied to create a fluid animation.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden; /* Hide content that overflows max-height */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initially hidden content */
}

.card:hover {
  max-height: auto; /* Expand on hover */
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
    line-height: 1.6;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is a simple example of an expanding card using only CSS.  Hover over the card to see the effect.  This demonstrates the power of CSS transitions and the `max-height` property to create dynamic and engaging user interfaces without relying on JavaScript.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`max-height: 100px;`**: This limits the initial height of the card, hiding the extra content.  You can adjust this value to control how much is initially visible.
* **`transition: max-height 0.3s ease-in-out;`**: This line applies a transition to the `max-height` property.  The `0.3s` specifies the duration of the transition, and `ease-in-out` defines the timing function (you can experiment with others like `ease`, `linear`, etc.).
* **`.card:hover { max-height: auto; }`**: This selector targets the card when the mouse hovers over it, setting `max-height` to `auto` which allows the content to expand to its natural height.
* **`overflow: hidden;`**: This is crucial. Without it, content that exceeds the initial `max-height` will still be visible even though it’s not part of the visible area.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS max-height:** [https://developer.mozilla.org/en-US/docs/Web/CSS/max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* **CSS-Tricks (general CSS resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

