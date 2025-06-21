# 🐞 CSS Challenge:  Animated Expanding Card


This challenge involves creating a card element that expands smoothly upon hovering, revealing more content. We'll use CSS3 transitions and transforms to achieve the animation.  No JavaScript is required.

## Description of the Styling

The card will start with a compact size. On hover, it expands horizontally to reveal hidden content.  The expansion will be accompanied by a smooth animation. We'll style the card with a simple, clean design using only CSS.  No external libraries like Tailwind are used for this example to focus on core CSS concepts.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: width 0.3s ease-in-out; /* Animate width change */
  width: 200px; /* Initial width */
  padding: 10px;
}

.card:hover {
  width: 400px; /* Expanded width on hover */
}

.card-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start; /* Align items to the left */
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 5px;
}

.card-text {
  font-size: 0.9em;
  line-height: 1.5;
  color: #555;
}

.hidden-content{
    display: none;
}

.card:hover .hidden-content {
    display: block;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p class="card-text">This is some sample text for the card.  It's quite short.</p>
    <p class="hidden-content">This is the extra content that appears on hover.  It's hidden by default.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`transition: width 0.3s ease-in-out;`**: This line is crucial for the animation. It specifies that the `width` property should transition smoothly over 0.3 seconds, using an `ease-in-out` timing function for a natural feel.
* **`.card:hover { width: 400px; }`**: This selector targets the card when the mouse hovers over it, changing its width to 400px.  The transition then smoothly animates this change.
* **`overflow: hidden;`**: This prevents the hidden content from leaking out before the hover effect.
* **`.hidden-content` and `.card:hover .hidden-content`**: These selectors control the visibility of the hidden content. It is initially hidden using `display: none;` and shown on hover.
* The use of `flexbox` (with `display: flex`) for the card content allows for easy vertical alignment of the title and text.

## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Flexbox:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

