# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The card expands smoothly on hover, revealing hidden content with a subtle animation.  We'll be using plain CSS3, avoiding any CSS frameworks like Tailwind for clarity.

**Description of the Styling:**

The card utilizes several CSS features to achieve its effect:

* **Transitions:** Smoothly animate the height and opacity changes on hover.
* **Overflow:** Initially hides the expanded content.
* **Height:** Dynamically changes based on the content height on hover.
* **Opacity:** Gradually reveals the hidden content during the expansion.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: height 0.3s ease-in-out;
  width: 300px;
}

.card:hover {
  height: auto;
}

.card-content {
  padding: 20px;
}

.card-content p {
  margin-bottom: 10px;
}

.hidden {
  opacity: 0;
  height: 0;
  overflow: hidden;
  transition: opacity 0.3s ease-in-out, height 0.3s ease-in-out;
}

.card:hover .hidden {
  opacity: 1;
  height: auto;
}

</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some initial content visible by default.</p>
    <div class="hidden">
      <p>This is extra content revealed on hover.</p>
      <p>It smoothly expands the card!</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* The `.card` class sets up the basic styling for the card, including background color, border radius, and shadow.  The `overflow: hidden;` is crucial for initially hiding the expanded content.  The `transition` property enables the smooth animation.
* The `.card:hover` selector triggers the height change to `auto`, allowing the card to expand to fit its content.
* The `.hidden` class initially sets the opacity and height to 0, effectively hiding the extra content.  The `transition` property on `.hidden` ensures smooth changes in opacity and height.
* The `.card:hover .hidden` selector reverses the effect of `.hidden` when the card is hovered, revealing the hidden content.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Overflow:** [https://developer.mozilla.org/en-US/docs/Web/CSS/overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
* **CSS-Tricks (General CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

