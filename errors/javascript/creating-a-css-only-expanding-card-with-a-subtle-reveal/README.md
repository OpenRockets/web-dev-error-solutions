# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details a CSS-only solution for creating an expanding card effect.  The card reveals additional content smoothly when clicked, all without JavaScript. This example leverages CSS transitions and transforms for a clean, elegant animation.

**Description of the Styling:**

The card utilizes a simple structure: a container div holding an image, a title, and a description.  The key to the effect is using CSS transitions on `transform` and `max-height` properties.  Initially, the description is hidden using `max-height: 0; overflow: hidden;`. Upon clicking, we use the `:target` pseudo-class to change the `max-height` to `auto`, allowing the description to expand.  The transition smoothly animates this change in height.  A subtle shadow and rounded corners enhance the visual appeal.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
body {
  font-family: sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: 300px;
  cursor: pointer;
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.2em;
  margin-bottom: 10px;
}

.card-description {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.5s ease-out;
}

.card:target .card-description {
  max-height: 200px; /* Adjust as needed */
}

.card a {
  text-decoration: none;
  color: inherit;
}
</style>
</head>
<body>
  <div class="card" id="myCard">
    <img src="https://via.placeholder.com/300x200" alt="Card Image">
    <div class="card-content">
      <h2 class="card-title">Card Title</h2>
      <p class="card-description">This is a sample description.  It will expand when you click the card.  Add more text here to see the full effect of the animation.  You can customize the `max-height` in the CSS to control the final expanded height.</p>
    </div>
  </div>

  <a href="#myCard">Click to go to Card</a>

</body>
</html>
```


**Explanation:**

* **`body` styles:**  Sets up basic page styling for centering the card.
* **`.card` styles:**  Basic card styling with shadows and rounded corners.
* **`.card img` styles:**  Ensures the image fits the card container.
* **`.card-description` styles:**  Crucially sets `max-height: 0;` to initially hide the content, and `overflow: hidden;` to prevent overflow. The `transition` property is key to the animation.
* **`.card:target .card-description` styles:** This uses the `:target` pseudo-class. When the `#myCard` element is the target of a link (clicked), this style applies, changing `max-height` to `auto`, triggering the transition.  The `max-height` value should be adjusted to suit the amount of content.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

