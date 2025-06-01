# 🐞 Creating a CSS-only Expanding Card with Hover Effect


This document details the creation of an expanding card using only CSS.  The card expands on hover, revealing hidden content.  This effect is achieved using CSS transitions and transforms without any JavaScript.  We'll utilize standard CSS properties for a broad compatibility.


## Description of the Styling

The card's base style is a simple rectangular container.  On hover, the card's height increases, revealing a hidden section. A smooth transition effect is applied to make the expansion visually appealing.  We'll use a subtle background color change on hover to enhance the user experience.


## Full Code

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
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  overflow: hidden; /* Hide the expanding content initially */
  height: 150px; /* Initial height of the card */
}

.card:hover {
  background-color: #e0e0e0;
  height: 250px; /* Height on hover, revealing hidden content */
}

.card-content {
  /* Content within the card */
}

.hidden-content {
  /* Initially hidden content, displayed on hover */
  padding-top: 10px;
  display: none;
}

.card:hover .hidden-content {
    display: block;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is the main content of the card.</p>
  </div>
  <div class="hidden-content">
    <p>This content is initially hidden and reveals on hover.</p>
    <p>More detailed information can be placed here.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`**: This class styles the main card container.  `transition: height 0.3s ease-in-out;` is crucial for the smooth expansion.  `overflow: hidden;` prevents the hidden content from peeking before the hover effect.  The initial `height` is set.

* **`.card:hover`**: This selector applies styles when the card is hovered over.  The `height` is increased to reveal the hidden content. The background color change provides visual feedback.

* **`.hidden-content`**: This class styles the content that's initially hidden.  `display: none;` ensures it's not visible initially.

* **`.card:hover .hidden-content`**:  This selector specifically targets the `.hidden-content` *only* when the parent `.card` is hovered, making the hidden content visible on hover.



## Resources to Learn More

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Search for "CSS transitions" or "CSS hover effects")


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

