# 🐞 Creating a CSS-Only Expanding Card with a Subtle Reveal Animation


This document details a CSS-only technique for creating an expanding card element with a smooth, subtle reveal animation.  No JavaScript is required. The animation uses CSS transitions and transforms to achieve a visually appealing effect.  This example uses plain CSS, but the principles can be easily adapted to frameworks like Tailwind CSS.


**Description of the Styling:**

This style creates a card that, on hover, expands slightly, revealing a hidden portion of its content.  The expansion is coupled with a subtle fade-in effect on the revealed content.  The overall effect is clean, modern, and interactive without needing any JavaScript.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  padding: 20px;
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transitions */
  box-shadow: 2px 2px 5px rgba(0,0,0,0.1); /* subtle shadow */
  overflow: hidden; /* Prevents content from overflowing during expansion */
}

.card:hover {
  transform: scale(1.05); /* Expand on hover */
  box-shadow: 4px 4px 10px rgba(0,0,0,0.2); /* Increased shadow on hover */
}

.card-content {
  opacity: 1;
  transition: opacity 0.3s ease-in-out; /* Fade-in transition */
}

.card:hover .card-content {
  opacity: 1; /* Fully visible on hover */
}

.hidden-content {
  opacity: 0; /* Initially hidden */
  height: 0;
  overflow: hidden; /* hides the content initially */
  transition: opacity 0.3s ease-in-out, height 0.3s ease-in-out;
}

.card:hover .hidden-content {
  opacity: 1;
  height: auto; /* Reveal on hover */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is the visible card content.</p>
  </div>
  <div class="hidden-content">
    <p>This content is initially hidden and reveals on hover.</p>
    <p>More hidden content can be added here.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:**  This is crucial for the animation. It smoothly transitions the `transform` (scale) and `box-shadow` properties over 0.3 seconds using an ease-in-out timing function.
* **`transform: scale(1.05)`:** This scales the card up slightly on hover, creating the expansion effect.
* **`opacity` and `height` transitions:** These control the fade-in and height changes of the hidden content.
* **`overflow: hidden;`:** This is vital to prevent the initially hidden content from affecting the layout before the hover effect.
* **Class Structure:**  The use of separate classes (`card-content` and `hidden-content`) allows for targeted styling of the visible and hidden parts of the card.

**External References:**

* [MDN Web Docs on CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [MDN Web Docs on CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

