# 🐞 Creating a CSS-only Expanding Card


This document details how to create an expanding card effect using only CSS.  No JavaScript required! This effect uses CSS transitions and transforms to smoothly expand a card when it's hovered over.  We'll use standard CSS3 properties; no Tailwind CSS is needed for this particular example.


## Description of the Styling

The card will have a basic design initially. On hover, the card will expand slightly, revealing more content and subtly changing its shadow.  The expansion will be a smooth transition, enhancing the user experience.


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
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
  overflow: hidden; /* Hide content that overflows on smaller cards */
  position: relative; /* For absolute positioning of inner content*/
}

.card:hover {
  transform: scale(1.1);
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.3);
  cursor: pointer;
}

.card-content {
  padding: 15px;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}


.card h2 {
  margin-top: 0;
}

.card p {
  margin-bottom: 0;
  font-size: 14px;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>Some card content goes here.  This is a longer paragraph to demonstrate expansion.</p>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`.card`:** This class styles the main card element. `width` and `height` define its dimensions. `border-radius` creates rounded corners. `box-shadow` adds a subtle shadow.  `transition` specifies the smooth animation for `transform` (scaling) and `box-shadow` properties. `overflow: hidden;` ensures content doesn't spill outside the card's bounds. `position: relative;` allows us to absolutely position the inner content.
* **`.card:hover`:**  This styles the card when the mouse hovers over it. `transform: scale(1.1);` increases the card size by 10%. `box-shadow` is intensified. `cursor: pointer;` changes the cursor to a hand, indicating an interactive element.
* **`.card-content`:** This class styles the content within the card. `padding` adds spacing, `position: absolute;` and the width and height properties make it fill the card completely. The flexbox properties (`display: flex`, etc.) centers the content.

## Links to Resources to Learn More

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Search for "CSS transitions" or "CSS transforms" for numerous tutorials)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

