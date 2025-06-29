# 🐞 CSS Challenge:  Animated Expanding Card


This challenge focuses on creating an animated expanding card using pure CSS. The card will subtly expand on hover, revealing more content, providing a visually engaging user experience.  We'll be using CSS3 transitions and transforms to achieve this effect.


**Description of the Styling:**

The card will be a simple rectangular element with a background color and padding.  On hover, the card will smoothly increase its width and height by a small percentage, creating an expanding animation.  We'll add a subtle box-shadow to enhance the 3D effect. The content inside the card will remain static; the animation focuses solely on the card's dimensions.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  padding: 20px;
  border-radius: 5px;
  transition: width 0.3s ease, height 0.3s ease, box-shadow 0.3s ease; /* Smooth transitions */
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1); /* Subtle shadow */
  width: 200px;
  height: 150px;
}

.card:hover {
  width: 250px;
  height: 200px;
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
}

.card-content {
  text-align: center;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>Expanding Card</h3>
    <p>This is some example content.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class styles the main card element.  `background-color`, `padding`, `border-radius` provide basic styling.  `transition` is crucial; it defines the smooth animation for `width`, `height`, and `box-shadow` properties.  The initial `box-shadow` gives a subtle 3D look.
* **`.card:hover`:** This targets the card when the mouse hovers over it.  `width` and `height` are increased, causing the expansion. The `box-shadow` is intensified on hover to emphasize the animation.
* **`.card-content`:** This class styles the content within the card for better presentation.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box-Shadow:** [MDN Web Docs - CSS box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

