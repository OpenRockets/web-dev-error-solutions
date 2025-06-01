# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  This effect smoothly expands a card when hovered over, revealing more content.  We'll use plain CSS3 for this, avoiding the need for JavaScript or any frameworks like Tailwind.


**Description of the Styling:**

The effect is achieved using CSS transitions and pseudo-elements (`::before` and `::after`).  The card itself has a fixed height, and upon hover, the `::before` pseudo-element expands, pushing the card content downwards.  The `::after` pseudo-element acts as a subtle background overlay that appears on hover to enhance the visual appeal.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 150px;
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden; /* Hide the expanding element initially */
  position: relative; /* Needed for absolute positioning of pseudo-elements */
  transition: all 0.3s ease-in-out; /* Smooth transition for animation */
}

.card:hover {
  height: 300px; /* Expand height on hover */
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 150px; /* Initial height, same as card */
  background-color: rgba(0, 0, 0, 0.2); /* Semi-transparent overlay */
  transition: height 0.3s ease-in-out; /* Smooth transition for expanding overlay */
}

.card:hover::before {
  height: 300px; /* Expand height to match card on hover */
}

.card-content {
  padding: 20px;
  color: #333;
}

.card::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 255, 0); /* Transparent by default */
  transition: background-color 0.3s ease-in-out; /* Smooth transition for overlay */
}

.card:hover::after {
  background-color: rgba(0, 0, 0, 0.1); /* Semi-transparent overlay on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is the card content.  It expands on hover.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

1. **`card` class:**  Sets basic styling for the card, including dimensions, background color, and rounded corners. `overflow: hidden` prevents the pseudo-elements from showing before hover.  `position: relative` is crucial for positioning the pseudo-elements.


2. **`card:hover`:**  On hover, the card's height increases, triggering the animation.

3. **`::before` pseudo-element:** Creates the expanding background overlay.  Its height changes on hover to create the expansion effect.

4. **`::after` pseudo-element:** Adds a subtle dark overlay on hover to further enhance the effect.


5. **`card-content` class:** Styles the content inside the card.

6. **Transitions:** `transition` property is used to ensure smooth animations for height and background color changes.


**Links to Resources to Learn More:**

* **CSS Pseudo-elements:**  [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

