# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect, where clicking a card reveals additional content.  We'll achieve this using purely CSS transitions and transformations, without relying on JavaScript. This example uses standard CSS3;  adapting it to Tailwind would simply involve replacing the CSS class names with their Tailwind equivalents.

**Description of the Styling:**

The card consists of two main parts: a front and a back.  The front displays a summary, and the back reveals more detailed information. By default, the back is hidden.  On click, we use CSS transitions to smoothly animate the transformation of the card, rotating it to reveal the back.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  perspective: 1000px; /* Necessary for 3D transforms */
  width: 300px;
  height: 200px;
  position: relative;
  cursor: pointer;
  transition: transform 0.5s ease-in-out; /* Smooth transition */
}

.card .front,
.card .back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden; /* Prevent back from showing initially */
  display: flex;
  justify-content: center;
  align-items: center;
}

.card .front {
  background-color: #4CAF50;
  color: white;
  font-size: 24px;
}

.card .back {
  background-color: #2196F3;
  color: white;
  font-size: 16px;
  transform: rotateY(180deg); /* Initially hidden */
}

.card.active {
  transform: rotateY(180deg); /* Rotate on click */
}
</style>
</head>
<body>

<div class="card" onclick="this.classList.toggle('active')">
  <div class="front">Click Me!</div>
  <div class="back">
    This is the back of the card.  More detailed information would go here.
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`perspective`:** This property creates a 3D space for the transformation to occur realistically.
* **`transition`:** This smoothly animates the `transform` property over 0.5 seconds.
* **`backface-visibility: hidden`:** This prevents the back side of the card from being visible initially.
* **`transform: rotateY(180deg)`:** This rotates the card around the Y-axis, revealing the back side.
* **`onclick="this.classList.toggle('active')"`:** This toggles the `active` class on the card element when clicked, triggering the CSS transition.  The `active` class applies the `rotateY(180deg)` transform.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **Understanding CSS 3D Transforms:**  Numerous tutorials are available on YouTube and other online learning platforms by searching for "CSS 3D transforms tutorial".


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

