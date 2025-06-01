# 🐞 Creating a CSS-Only Expanding Card with a Subtle Animation


This project demonstrates how to create an expanding card effect using only CSS.  No JavaScript is required. The effect involves a card that expands vertically when hovered over, revealing additional content, with a smooth animation for a polished user experience.  This example utilizes CSS3 transitions and transforms for the animation.

**Description of the Styling:**

The card is styled using a simple, clean approach.  The main card element uses a consistent background color and padding for visual appeal. The content initially hidden is positioned absolutely within the card, allowing it to slide down smoothly when the card is hovered over. The `transform: translateY()` property combined with a CSS transition provides the animation.  We use a subtle box shadow to add depth and visual separation from the background.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Prevents content from spilling outside the card */
  transition: box-shadow 0.3s ease, transform 0.3s ease; /* Smooth transitions */
  width: 300px;
}

.card:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  transform: translateY(-2px); /* Slight lift on hover */
}

.card-content {
  position: relative;
}

.card-content-hidden {
  position: absolute;
  top: 100%; /* Initially hidden below the visible content */
  left: 0;
  transition: top 0.3s ease; /* Smooth transition for expanding */
}

.card:hover .card-content-hidden {
  top: 0; /* Reveals content on hover */
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
  line-height: 1.6;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is some sample text for the visible part of the card.  This demonstrates a simple card design with an expanding effect.</p>
    <div class="card-content-hidden">
      <p class="card-text">This is the hidden content that expands when you hover over the card. You can add more information here as needed.  Enjoy the subtle animation!</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This smooths the changes in `box-shadow` and `transform` properties over 0.3 seconds, creating the animation.
* **`transform: translateY()`:** This moves the card slightly upwards on hover, adding a subtle lift effect.
* **`position: absolute` and `top: 100%`:**  These initially hide the extra content by positioning it below the visible content.
* **`:hover` pseudo-class:** The hover state triggers the changes, revealing the hidden content and enhancing the shadow.
* **`overflow: hidden;`:** This ensures that the expanding content doesn't unexpectedly overflow the card boundaries.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

