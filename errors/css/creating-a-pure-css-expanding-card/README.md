# 🐞 Creating a Pure CSS Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content.  We'll use only CSS3 for this, making it lightweight and easily integrable into any project.

**Description of the Styling:**

The styling uses a combination of `max-height`, `transition`, and `overflow` properties to achieve the expansion effect.  The card initially has a limited height, hiding the content. On hover, the `max-height` is set to a larger value, allowing the content to be revealed smoothly thanks to the transition.  The `overflow` property handles the hidden content before expansion.

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
  transition: max-height 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initial height */
  width: 300px;
}

.card:hover {
  max-height: 300px; /* Expanded height on hover */
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
    <p>This is some example content that is initially hidden.  The card expands on hover to reveal this content.  You can add as much text as you like here!</p>
    <p>This is another paragraph of example content.  This effect is achieved purely using CSS, making it very lightweight and efficient.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:** This class styles the overall card.  `overflow: hidden;` is crucial for hiding the content initially.  `transition: max-height 0.3s ease-in-out;` ensures a smooth animation when the `max-height` changes.  `max-height: 100px;` sets the initial, limited height.
* **`.card:hover`:** This styles the card when the mouse hovers over it.  `max-height: 300px;` sets the expanded height. Adjust this value as needed.
* **`.card-content` and `.card-title`:** These classes simply style the inner content for better readability.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Overflow:** [https://developer.mozilla.org/en-US/docs/Web/CSS/overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

