# 🐞 CSS Challenge:  Animated Expanding Card


This challenge involves creating a card that expands smoothly when hovered over, revealing more content.  We'll use CSS3 transitions and transforms to achieve the animation.  No JavaScript is required.

**Description of the Styling:**

The card will be a simple rectangular box with a title, some text, and a hidden section that expands on hover. The expansion will be animated using a CSS transition. The styling will be clean and modern.  We'll leverage standard CSS properties for easy understanding and implementation.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows during expansion */
  transition: transform 0.3s ease-in-out; /* Smooth transition for transform property */
  width: 300px;
}

.card:hover {
  transform: scale(1.1); /* Expand the card on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.card-text {
  margin-bottom: 10px;
}

.card-hidden {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /* Smooth transition for max-height */
}

.card:hover .card-hidden {
  max-height: 200px; /* Reveal hidden content on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is some sample text to demonstrate the expanding card effect.  This is some sample text to demonstrate the expanding card effect.</p>
    <div class="card-hidden">
      <p>This is the hidden content that appears when you hover over the card.  It expands smoothly thanks to CSS transitions.</p>
      <p>More hidden content here...</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition: transform 0.3s ease-in-out;`:** This line applies a smooth transition to the `transform` property, making the scaling effect animated.
* **`transform: scale(1.1);`:** This line scales the card up by 10% on hover.
* **`max-height: 0;` and `max-height: 200px;`:** These control the height of the hidden content.  Initially, it's 0, hiding the content. On hover, it expands to 200px (you can adjust this value).
* **`overflow: hidden;`:**  This prevents the hidden content from spilling out before it's revealed.
* **`transition: max-height 0.3s ease-in-out;`:** This ensures a smooth animation for the height change.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box Model:** [MDN Web Docs - Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

