# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution to create an expanding card effect, mimicking the behavior of a card that reveals more content upon click.  We'll use pure CSS3, avoiding JavaScript for a lightweight and performant solution.


**Description of the Styling:**

This effect is achieved using CSS transitions, transforms, and the `:target` pseudo-class.  The card initially shows a summary of information. Clicking on the card's title changes the URL's hash, targeting a specific element within the card. This triggers a CSS transition that expands the card to reveal the full content.  The expansion involves increasing the height of the card smoothly and a subtle fade-in effect for the hidden content.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
body {
  font-family: sans-serif;
}

.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: height 0.3s ease-in-out; /* Smooth height transition */
}

.card-header {
  background-color: #333;
  color: white;
  padding: 15px;
  cursor: pointer;
}

.card-header h2 {
  margin: 0;
}

.card-content {
  padding: 15px;
  opacity: 0; /* Initially hidden */
  transition: opacity 0.3s ease-in-out; /* Smooth opacity transition */
  max-height: 0; /* Initially collapsed */
  overflow: hidden; /* Hide content that overflows initially */
}

.card:target .card-content {
  opacity: 1; /* Show content on target */
  max-height: 500px; /* Set max height for expanded content */
}
</style>
</head>
<body>

<div class="card" id="myCard">
  <div class="card-header">
    <h2>Click to Expand</h2>
  </div>
  <div class="card-content">
    <p>This is some extra content that will be revealed when you click the header.  You can add as much text and other elements as you need here. This is just an example to show the expanding card effect in action.</p>
    <p>This is another paragraph of example content.  You can customize the styling further to match your website's design.</p>
  </div>
</div>

<a href="#myCard">Link to Card (Optional)</a>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This smoothly animates changes to the `height` and `opacity` properties.
* **`max-height` property:**  Controls the maximum height of the `.card-content`. Initially set to 0, it expands to 500px (adjust as needed) when the card is targeted.
* **`:target` pseudo-class:**  Selects the element whose ID matches the URL's hash fragment. Clicking the header changes the URL's hash, making the `.card` element the target.
* **`overflow: hidden;`:** Prevents content from overflowing outside the card's boundaries before and during the transition.

**Links to Resources to Learn More:**

* [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [MDN Web Docs - :target Pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* [CSS-Tricks](https://css-tricks.com/) (For various CSS tutorials and techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

