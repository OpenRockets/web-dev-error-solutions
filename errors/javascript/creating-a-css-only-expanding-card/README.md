# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content.  This example uses only CSS3 properties, avoiding any JavaScript.

**Description of the Styling:**

The styling relies primarily on the `height` property and transitions.  The card starts with a smaller height, only showing a title and a small portion of the content. On hover, the `height` transitions smoothly to a larger value, revealing the full content.  We also use `overflow: hidden` initially to hide the extra content and a subtle box-shadow to enhance the card's appearance.

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
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: height 0.3s ease-in-out; /* Smooth transition for height change */
  width: 300px;
}

.card:hover {
  height: 250px; /* Expanded height on hover */
}

.card-content {
  padding: 15px;
}

.card-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
  height: 100px; /* Initial height of the content; Adjust as needed */
  overflow: auto; /* Allows scrolling if the content exceeds the height */
}

</style>
</head>
<body>

<div class="card" style="height: 100px;">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-text">This is the content of the expanding card.  You can add as much text as you like here, and it will smoothly expand on hover. This demonstrates a simple but effective CSS-only animation.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition: height 0.3s ease-in-out;`**: This line is crucial. It tells the browser to smoothly animate the change in the `height` property over 0.3 seconds, using an "ease-in-out" timing function for a natural feel.
* **`overflow: hidden;`**: This prevents the content from overflowing the initial smaller height of the card.
* **`height: 100px;` (in `.card` and `.card-text`)**:  Sets the initial height of the card and the content area. Adjust these values to control the starting size.
* **`height: 250px;` (in `.card:hover`)**:  This sets the height of the card when the user hovers over it. Adjust this value to control the expanded size.
* **`overflow: auto;` (in `.card-text`)**: This ensures that if the content exceeds the expanded height, a scrollbar will appear.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transitions and Animations:** [W3Schools - CSS Transitions](https://www.w3schools.com/css/css3_transitions.asp)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

