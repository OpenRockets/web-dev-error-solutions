# 🐞 Creating a CSS-only Expanding Card with a Subtle Animation


This document details the creation of an expanding card using only CSS.  The card expands smoothly on hover, revealing hidden content, and utilizes a simple animation for a more engaging user experience.  No JavaScript is required.


## Description of the Styling

This effect leverages CSS transitions and transforms to create the expansion animation.  The card initially displays a smaller size and, on hover, expands to reveal additional content. A subtle box-shadow is added to enhance the card's appearance.  The animation is smooth and controlled, ensuring a pleasant user experience.  This example doesn't use a specific CSS framework like Tailwind, focusing on pure CSS for better understanding of the underlying principles.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  height: 150px;
  background-color: #f0f0f0;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content outside the initial card size */
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transitions */
}

.card:hover {
  transform: scale(1.1); /* Expand on hover */
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Increased shadow on hover */
}

.card-content {
  padding: 10px;
  height: 100%; /* Occupies full card height initially*/
  display: flex;
  flex-direction: column;
  justify-content: space-between; /* Distribute space between header and hidden content */

}

.card-header {
  font-weight: bold;
}

.hidden-content {
  overflow: hidden; /* Hide content initially */
  height: 0; /* Initially zero height */
  transition: height 0.3s ease-in-out; /* Smooth height transition */
}

.card:hover .hidden-content {
  height: 100px; /* Expand height on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <div class="card-header">Card Title</div>
    <div class="hidden-content">
      This is some hidden content that will be revealed on hover.  This allows for a clean and engaging user experience.
    </div>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`transition` property:** This allows smooth animations for `transform` and `box-shadow` properties. The `ease-in-out` timing function provides a natural-feeling animation.
* **`transform: scale(1.1);`:** This scales the card up by 10% on hover, creating the expansion effect.
* **`box-shadow`:**  Provides a subtle shadow, which is enhanced on hover.
* **`overflow: hidden;`:**  Prevents the hidden content from overflowing the initial card size.
* **Height transition on `.hidden-content`:**  The height of the hidden content is initially zero, and transitions to 100px on hover, revealing the content smoothly.
* **`flex-direction: column;` and `justify-content: space-between;`**:These are used within the `.card-content` to properly align the header and hidden content vertically


## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (A great resource for various CSS techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

