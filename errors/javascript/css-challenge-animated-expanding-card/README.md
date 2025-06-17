# 🐞 CSS Challenge:  Animated Expanding Card


This challenge involves creating a card that expands smoothly on hover, revealing more content.  We'll use CSS3 transitions and transforms to achieve this effect. No JavaScript is required.

**Description of the Styling:**

The card will have a clean, minimalist design.  On hover, the card will increase in width and height, revealing hidden content (in this example, additional text). The transition will be smooth and visually appealing.


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
  padding: 20px;
  transition: width 0.3s ease-in-out, height 0.3s ease-in-out; /* Add transition for smooth animation */
  width: 300px;
  height: 150px;
  overflow: hidden; /* Hide content initially */
}

.card:hover {
  width: 500px;
  height: 300px;
}

.card-content {
  /* Initially hidden, will be revealed on expand */
}
</style>
</head>
<body>

<div class="card">
  <h2>Card Title</h2>
  <p>This is some initial card content.</p>
  <div class="card-content">
    <p>This additional content is initially hidden and will be revealed on hover.</p>
    <p>The card smoothly expands to accommodate it.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition: width 0.3s ease-in-out, height 0.3s ease-in-out;`:** This CSS property is crucial for the animation. It specifies that the `width` and `height` properties should transition smoothly over 0.3 seconds, using an "ease-in-out" timing function (which provides a natural acceleration and deceleration).

* **`.card:hover { width: 500px; height: 300px; }`:** This selector targets the card element when the mouse hovers over it.  The `width` and `height` are increased to reveal the hidden content.

* **`overflow: hidden;`:**  This is applied to the card initially to hide the extra content that will be revealed on hover.

* **`.card-content`:** This class styles the hidden content within the card.  You can add more detailed styling as needed.



**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS3 Tutorial:** [W3Schools CSS3 Tutorial](https://www.w3schools.com/css/css3_intro.asp)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

