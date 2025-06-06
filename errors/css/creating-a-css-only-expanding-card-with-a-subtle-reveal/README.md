# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS. The effect involves a subtle reveal of content upon hovering over the card, showcasing a smooth transition and clean visual design.  We'll use standard CSS3 properties for this example.


**Description of the Styling:**

The card will have a default state with limited height, showing only a title. On hover, the card will smoothly expand vertically to reveal a hidden description.  We'll achieve this using transitions on the `height` property and clever manipulation of the `overflow` property to control what's initially visible.


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
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth transition for height changes */
  width: 300px;
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-description {
  font-size: 1em;
  line-height: 1.5;
  height: 0; /* Initially hidden */
  overflow: hidden; /* Hide overflow until expanded */
  transition: height 0.3s ease-in-out; /* Match card transition */
}

.card:hover .card-description {
  height: auto; /* Expand on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-description">This is a simple expanding card created using only CSS.  Hover over the card to see the description expand smoothly.  This effect is achieved by using CSS transitions and manipulating the height and overflow properties.  It's a great example of what's possible with just CSS!</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`.card`:**  This class styles the main card container, setting background, border radius, shadow, and importantly, `overflow: hidden` to initially hide the description. The `transition` property ensures a smooth animation.
* **`.card-content`:** This class provides internal padding for the card content.
* **`.card-title`:** Styles the card's title.
* **`.card-description`:** This is crucial.  `height: 0` initially hides the description, and `overflow: hidden` prevents it from spilling outside its container. The `transition` matches the card's transition.
* **`.card:hover .card-description`:** This is the key selector. On hover over the `.card`, the `.card-description`'s `height` is set to `auto`, allowing it to expand to its natural content height.

The combination of `overflow: hidden`, `height: 0`, and the transition on hover creates the expanding effect.  The matching transitions ensure a smooth, visually appealing animation.


**Links to Resources to Learn More:**

* **MDN Web Docs CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

