# 🐞 CSS Challenge:  Animated Expanding Card


This challenge involves creating a card that expands smoothly when hovered over, revealing additional content. We'll use CSS3 transitions and transforms to achieve this animation.  No external libraries or frameworks (like Tailwind) will be used to focus on core CSS concepts.


**Description of the Styling:**

The card will have a simple design. When not hovered over, it will show a title and a small excerpt of text. Upon hovering, the card will expand horizontally, revealing a larger excerpt and potentially an image or additional details. The animation will be smooth and visually appealing.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 5px;
  padding: 20px;
  transition: transform 0.3s ease-in-out; /* Smooth transition for transform property */
  width: 300px;
  overflow: hidden; /* Prevents content overflow during expansion */
}

.card:hover {
  transform: scaleX(1.2); /* Expands horizontally on hover */
}

.card-content {
  height: 100px; /*Initial height of the card content*/
  overflow: hidden; /* Initially hides the extra content */
}

.card-content:hover{
    overflow: visible;
}


.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.card-excerpt {
  font-size: 1em;
  line-height: 1.5;
}

.extra-content {
  height: 100px;
  overflow: hidden;
  transition: max-height 0.3s ease-in-out; /*Smooth transition for max-height*/
}

.card:hover .extra-content {
    max-height: 200px;
}

</style>
</head>
<body>

<div class="card">
  <h2 class="card-title">Expanding Card</h2>
  <div class="card-content">
    <p class="card-excerpt">This is a short excerpt of text.  Hover over the card to see more!</p>
    <div class="extra-content">
      <p>This is the additional content that is revealed when you hover over the card. You can add images, more text, or anything else you want here.</p>
    </div>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`transition` property:**  This is crucial for creating the smooth animation. It specifies which properties (`transform`) should animate, the duration (`0.3s`), and the timing function (`ease-in-out`).
* **`transform: scaleX(1.2)`:** This scales the card horizontally by 120% on hover, creating the expansion effect.
* **`overflow: hidden;`**: This property initially hides any content that exceeds the card's height, preventing the extra content from being visible before the hover.  On hover it's set to `visible` on the inner `card-content` element.
* **`max-height`:** This is used along with a transition to control the smooth expansion of additional content within the `extra-content` div.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) (For more complex animations beyond simple transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

