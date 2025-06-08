# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically to reveal hidden content when hovered over.  This effect is achieved purely with CSS, making it lightweight and efficient. We'll be using standard CSS3 properties.


**Description of the Styling:**

The styling relies primarily on transitions and the `max-height` property.  The card starts with a constrained `max-height`, hiding its inner content. On hover, the `max-height` is changed to allow the content to expand, and the transition property smoothly animates this change. We'll also add some basic styling for visual appeal.


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
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initially hidden content */
}

.card:hover {
  max-height: 300px; /* Expand on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
  margin-bottom: 10px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p>This is some example text inside the expanding card.  You can add as much content as you need.  This is just a demonstration.</p>
    <p>More text here to demonstrate the expansion effect.  Notice how smoothly the card expands when hovered over.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class defines the basic card styling, including background color, border radius, and importantly, the `overflow: hidden;` property (to prevent content from spilling outside the card's boundaries) and the `transition` property (which dictates the animation speed and timing function). The initial `max-height` keeps the content hidden.
* **`.card:hover`:** This selector targets the card when the mouse hovers over it.  The `max-height` is increased to reveal the full content.
* **`.card-content` and `.card-title`:** These classes provide basic styling for the content within the card.

The magic happens with the interplay of `max-height` and `transition`. The `transition` smoothly animates the change in `max-height`, creating the expanding effect.  You can adjust the `max-height` values and the `transition` duration to fine-tune the animation to your liking.


**Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS max-height:** [https://developer.mozilla.org/en-US/docs/Web/CSS/max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

