# 🐞 Creating a CSS-only Expanding Card with a subtle reveal


This document details a CSS-only solution for creating an expanding card effect. The card expands on hover, revealing additional content with a smooth, subtle animation.  This utilizes pure CSS3, requiring no JavaScript.


## Description of the Styling

This design creates a card with a visually appealing expansion effect. On hover, the card increases in height, revealing hidden content smoothly. The transition is handled purely with CSS transitions, making it lightweight and performant. The design uses a simple layout with a fixed width and dynamically adjusted height.  A subtle background color change adds to the user experience.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  background-color: #f0f0f0;
  border-radius: 8px;
  overflow: hidden; /* Hide content outside the card */
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
}

.card:hover {
  background-color: #ddd; /* subtle color change on hover */
  height: 350px; /* Expands the card on hover */
}

.card-content {
  padding: 20px;
  height: 150px; /* Initial height of the card */
  overflow: hidden; /* Hide content until expansion */
}

.card-content h2 {
  margin-top: 0;
}

.card-content p {
  margin-bottom: 0;
}

.hidden-content {
    height: 0;
    overflow: hidden;
    transition: height 0.3s ease-in-out; /* Smooth transition for hidden content */
}

.card:hover .hidden-content {
    height: 200px; /* Reveals hidden content on hover */
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some sample text for the card.</p>
    <div class="hidden-content">
        <p>This is the hidden content that appears on hover.</p>
        <p>More hidden content here!</p>
    </div>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`transition: height 0.3s ease-in-out;`**: This CSS property provides the smooth animation when the card's height changes.  `0.3s` sets the animation duration, and `ease-in-out` specifies the timing function for a natural-feeling animation.

* **`overflow: hidden;`**: This prevents the content from overflowing the card's boundaries before and during the expansion.  It's crucial for the hidden-content reveal.

* **`:hover`**: This CSS pseudo-class targets the card when the mouse hovers over it.

* **`.hidden-content`**: This class is used to manage the hidden section of the card, using height to initially hide it and then reveal it on hover.

* **`height` manipulation**: The `height` property of both `.card` and `.hidden-content` is manipulated on hover to create the expansion effect.

## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Search for "CSS animations" or "hover effects")
* **FreeCodeCamp CSS challenges:** [https://www.freecodecamp.org/learn/responsive-web-design/](https://www.freecodecamp.org/learn/responsive-web-design/) (Look for relevant projects involving animations and hover effects)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

