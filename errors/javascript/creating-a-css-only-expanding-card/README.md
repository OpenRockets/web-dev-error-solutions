# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This example utilizes plain CSS3; no JavaScript or frameworks like Tailwind are needed.

## Description of the Styling

The styling uses a combination of CSS transitions and pseudo-elements (`::before` and `::after`) to achieve the expanding effect. The card's initial height is set to be smaller than its content. On hover, the height transitions to accommodate the full content, creating a smooth expansion.  A subtle background color change is also included for visual feedback.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border: 1px solid #ccc;
  border-radius: 5px;
  overflow: hidden; /* Hide overflowing content initially */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  width: 300px;
  height: 100px; /* Initial height */
  position: relative; /* Needed for absolute positioning of pseudo-elements */
}

.card:hover {
  background-color: #e0e0e0;
  height: auto; /* Expand to full content height on hover */
}


.card-content {
  padding: 10px;
}

.card::before, .card::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.1);
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
}

.card:hover::before, .card:hover::after {
  opacity: 1;
}


</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3>This is the card title</h3>
    <p>This is some example text that will be hidden initially and revealed when the card is hovered over.</p>
    <p>More text to ensure the card expands significantly.</p>
  </div>
</div>

</body>
</html>
```

## Explanation

* **`transition: height 0.3s ease-in-out;`**: This line is crucial for the smooth expansion. It specifies that the `height` property should transition over 0.3 seconds using an ease-in-out timing function.
* **`height: auto;`**: On hover, the `height` is set to `auto`, allowing the card to naturally expand to fit its content.
* **`overflow: hidden;`**: This prevents the content from overflowing the initial smaller height before the hover effect.
* **Pseudo-elements:** The `::before` and `::after` pseudo-elements are used to create a subtle darkening effect when hovered over for better visual feedback. You can customize this further or remove them if preferred.

## Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks:** Search for "CSS transitions" or "CSS hover effects" on [https://css-tricks.com/](https://css-tricks.com/) for more advanced techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

