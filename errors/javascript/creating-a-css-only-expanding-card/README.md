# 🐞 Creating a CSS-Only Expanding Card


This document details the creation of an expanding card using only CSS.  This effect is achieved without any JavaScript, relying solely on CSS transitions and pseudo-elements. The card expands vertically when hovered over, revealing hidden content.  This example utilizes plain CSS, but could easily be adapted for frameworks like Tailwind CSS.

**Description of the Styling:**

The core of this effect involves using the `:hover` pseudo-class to trigger a transition on the card's height.  The hidden content is initially set to `height: 0;` and `overflow: hidden;`.  On hover, the height is changed to `auto`, revealing the hidden content smoothly thanks to the CSS transition. A subtle background color change and border radius modification enhance the visual appeal.

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
  transition: background-color 0.3s ease, height 0.3s ease, border-radius 0.3s ease; /* Smooth transitions */
  overflow: hidden; /* Hide content that overflows */
  height: 100px; /* Initial height */
}

.card:hover {
  background-color: #ddd;
  border-radius: 10px;
  height: auto; /* Expand to full height on hover */
}

.card-content {
  /* initially hidden content */
}
</style>
</head>
<body>

<div class="card">
  <p>This is the visible content of the card.</p>
  <div class="card-content">
    <p>This is the hidden content that appears on hover.  This could be a longer description, additional images, or any other information you want to reveal.</p>
    <p>Expanding cards are a great way to add interactive elements to your website without resorting to JavaScript.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`.card`:**  This class styles the card itself, setting the background color, padding, initial height, and the transitions for background color, height, and border radius. `overflow: hidden` ensures that the hidden content doesn't initially bleed out.
* **`.card:hover`:** This targets the card when the mouse hovers over it.  It changes the background color, increases the border radius, and crucially, sets the `height` to `auto`, allowing the content to expand to its natural height.
* **`.card-content`:** This class (though not explicitly styled here) contains the hidden content, which is revealed on hover due to the height transition.  You could add more specific styling to this class as needed.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **Understanding `overflow` property:** [MDN Web Docs - overflow property](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

