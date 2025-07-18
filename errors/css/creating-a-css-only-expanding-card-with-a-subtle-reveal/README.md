# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The card expands vertically to reveal additional content when hovered over, employing a smooth transition for a polished user experience.  This example uses standard CSS3; no frameworks like Tailwind are employed to focus on core CSS concepts.


**Description of the Styling:**

The card utilizes a combination of pseudo-elements (`::before` and `::after`) and transitions to achieve the expanding effect.  The `::before` pseudo-element creates an overlay that obscures the hidden content. On hover, the height of the card expands, and the overlay's opacity changes, revealing the hidden content.  The transition property ensures a smooth animation.  Appropriate padding and styling are added for visual appeal.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden; /* Hide content outside the card */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  height: auto; /* Expand to content height on hover */
}

.card-content {
  padding: 20px;
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent overlay */
  transition: opacity 0.3s ease-in-out;
  opacity: 1; /* Initially opaque */
}

.card:hover::before {
  opacity: 0; /* Become transparent on hover */
}

.card-hidden {
  padding: 20px;
  height: 0; /* Initially collapsed */
  overflow: hidden; /* Hide the content initially */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover .card-hidden {
  height: auto; /* Expand on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is the visible content of the card.</p>
  </div>
  <div class="card-hidden">
    <p>This is the hidden content that reveals on hover.</p>
    <p>More hidden content here...</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

1. **Basic Card Structure:**  We create a card container with visible and hidden content divs.
2. **Overlay (`::before`):** The `::before` pseudo-element creates a semi-transparent overlay that initially hides the extra content.
3. **Transitions:**  The `transition` property on the card and overlay ensures smooth animations for height and opacity changes.
4. **Hover Effects:** On hover, the card's height is set to `auto`, allowing it to expand to fit the content, and the overlay's opacity is set to 0, making it transparent.
5. **Hidden Content Management:** The `.card-hidden` class initially sets the height to 0 and uses `overflow: hidden` to keep hidden content invisible until expanded on hover.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Tricks - Tutorials:** [https://css-tricks.com/](https://css-tricks.com/) (Search for tutorials on transitions and pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

