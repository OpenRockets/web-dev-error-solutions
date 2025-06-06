# 🐞 Creating a CSS-Only Expanding Card with a Smooth Transition


This document details the creation of an expanding card using only CSS.  This effect is achieved using CSS transitions and transforms to smoothly animate the card's height and content visibility upon hover. No JavaScript is required.  The example uses plain CSS, but the concepts could easily be adapted to a framework like Tailwind CSS.


**Description of the Styling:**

The card initially occupies a small space. On hover, it expands vertically to reveal hidden content.  This expansion is accompanied by a smooth animation, making the transition visually appealing.  The styling employs a combination of `max-height`, `transition`, and `transform` properties to achieve this effect.

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
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease-in-out; /* Smooth transition for max-height */
  max-height: 100px; /* Initial height */
}

.card:hover {
  max-height: 300px; /* Height when hovering */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-weight: bold;
}

.hidden {
  overflow: hidden;
  height: 0;
  transition: height 0.3s ease-in-out;
}

.card:hover .hidden{
  height: auto;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p>This is some example text that will be hidden until you hover over the card.  You can add as much text as you like here and it will smoothly expand to show all the content.</p>
    <div class="hidden">
      <p>This is additional hidden content that will only be revealed upon hover.  Note the use of the hidden class and the adjustment of the height on hover.</p>
      <p>More hidden content here...</p>
    </div>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:** This class sets the basic styling for the card, including background color, border radius, and importantly, the `overflow: hidden;` property to prevent content from overflowing the initial height, and the `transition` property to enable smooth animation.  `max-height` sets the initial restricted height.

* **`.card:hover`:** This selector applies styles when the user hovers over the card, increasing the `max-height` to reveal the hidden content.

* **`.card-content`:** This class styles the content within the card.

* **`.card-title`:** Styles the card title.

* **`.hidden`:** This class initially hides the additional content by setting its height to 0 and using `overflow: hidden`. The `transition` property ensures a smooth height change.

* **`.card:hover .hidden`:** This selector targets the `.hidden` element when hovering over the `.card`, removing the height restriction, revealing the content.


**Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **MDN Web Docs on CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **Understanding CSS Selectors:**  Search for "CSS selectors tutorial" on your favorite search engine.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

