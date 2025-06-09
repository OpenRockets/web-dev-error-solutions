# 🐞 CSS Challenge:  Animated Expanding Card


This challenge focuses on creating an animated expanding card using CSS.  The card will have a subtle hover effect, expanding slightly when the mouse hovers over it and shrinking back to its original size when the mouse leaves.  We'll use pure CSS3 for this, avoiding JavaScript for a cleaner and more performant solution.  The styling will be clean and modern, suitable for a variety of applications.

**Description of the Styling:**

The card will be a simple rectangular box with rounded corners.  The background color will be a light grey. On hover, the card will increase slightly in size (both width and height) and a subtle shadow will appear, creating a sense of depth. The animation will be smooth and natural, using CSS transitions.  Text within the card will remain centered.

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
  padding: 20px;
  text-align: center;
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transitions */
  width: 300px;
  margin: 50px auto; /* Center the card */
}

.card:hover {
  transform: scale(1.05); /* Expand on hover */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add shadow on hover */
}

.card h2 {
  margin-top: 0;
}
</style>
</head>
<body>

<div class="card">
  <h2>Expanding Card</h2>
  <p>This is a simple card that expands on hover using only CSS.</p>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the basic card structure. `transition` property is crucial; it applies a smooth transition to the `transform` (scaling) and `box-shadow` properties, creating the animation.
* **`.card:hover`:** This selector targets the card when the mouse hovers over it.  `transform: scale(1.05);` increases the size by 5% on both axes. `box-shadow` adds a subtle drop shadow to enhance the visual effect.
* **`transition` property:**  This property defines how long and how smoothly the transitions between states (normal and hover) will occur.  `0.3s` sets the duration to 0.3 seconds, and `ease-in-out` provides a smooth acceleration and deceleration.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box Shadow:** [MDN Web Docs - CSS Box Shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

