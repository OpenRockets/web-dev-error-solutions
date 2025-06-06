# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This example utilizes only CSS3 properties and avoids JavaScript for a lightweight and performant solution.

**Description of the Styling:**

The card uses a simple structure with a container div for the entire card and inner divs for the visible and hidden content.  The key to the expansion effect is the use of `max-height` and transitions. Initially, the hidden content's `max-height` is set to 0, hiding it.  On hover, the `max-height` is changed to a value that allows the hidden content to be fully visible, and a smooth transition is applied to create the animation.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden; /* Prevents content from overflowing during expansion */
  transition: box-shadow 0.3s ease, transform 0.3s ease; /* Add smooth transitions */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Add subtle shadow */

}
.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15); /* Enhanced shadow on hover */

}

.card-content {
  padding: 20px;
}

.card-visible {
  background-color: white;
}


.card-hidden {
  background-color: #fff;
  max-height: 0; /* Initially hides the content */
  overflow: hidden; /* Prevents content from showing before expansion */
  transition: max-height 0.3s ease; /* Smooth transition for max-height */
}

.card:hover .card-hidden {
  max-height: 200px; /* Sets max-height on hover to show the content */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content card-visible">
    <h2>Card Title</h2>
    <p>This is the visible content of the card.</p>
  </div>
  <div class="card-content card-hidden">
    <p>This is the hidden content that will be revealed on hover.</p>
    <p>More hidden content here...</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This styles the main card container, setting background color, border radius, overflow, and transitions for smooth animations.
* **`.card-content`:**  Styles the content within the card.
* **`.card-visible`:** Styles the initially visible content.
* **`.card-hidden`:** Styles the hidden content, setting `max-height` to 0 initially and using transitions for smooth expansion.  The `overflow: hidden;` prevents the hidden content from spilling before the animation starts.
* **`.card:hover .card-hidden`:** This selector targets the `.card-hidden` element *only when* its parent `.card` is hovered over.  This is where the `max-height` is changed to reveal the hidden content.

**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Max-Height:** [https://developer.mozilla.org/en-US/docs/Web/CSS/max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

