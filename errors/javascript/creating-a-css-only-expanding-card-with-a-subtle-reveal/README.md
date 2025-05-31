# 🐞 Creating a CSS-Only Expanding Card with a Subtle Reveal


This document details how to create an expanding card effect using only CSS.  The effect features a subtle reveal animation as the card expands to display more content.  No JavaScript is required.  This example uses plain CSS3, but could easily be adapted for a CSS framework like Tailwind CSS.


**Description of the Styling:**

This effect uses CSS transitions and transforms to create a smooth expansion animation. The card starts in a compact state, and on hover, it expands vertically, revealing hidden content. The opacity of the expanded content is initially set to 0 and then transitioned to 1, creating a subtle fade-in effect.  The box-shadow is also subtly adjusted on hover to add depth.


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
  overflow: hidden; /* Hide content that overflows */
  transition: all 0.3s ease-in-out; /* Smooth transition for all properties */
  width: 300px;
}

.card:hover {
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
  transform: translateY(-5px); /* Subtle lift on hover */
}

.card-content {
  padding: 20px;
}

.card-content-hidden {
  max-height: 0;
  overflow: hidden;
  opacity: 0;
  transition: max-height 0.3s ease-in-out, opacity 0.3s ease-in-out; /* Transition for hidden content */
}

.card:hover .card-content-hidden {
  max-height: 200px; /* Adjust as needed */
  opacity: 1;
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
    <p>This is some sample text for the card.  You can add as much content as you like to see the expansion effect in action.</p>
    <div class="card-content-hidden">
      <p>This is the hidden content that will be revealed when you hover over the card.</p>
      <p>Add more hidden content here to test the expansion.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This is crucial for the animation.  It applies to the `max-height`, `opacity`, and other properties, making changes smooth.
* **`max-height` property:**  Controls the visible height of the hidden content.  Initially set to 0, it expands to a specified value on hover.
* **`overflow: hidden`:** Prevents the hidden content from spilling out of the card before expansion.
* **`opacity` property:**  Creates the fade-in effect for the hidden content.
* **`transform: translateY(-5px)`:** Creates the subtle lift effect on hover, adding to the animation's visual appeal.
* **`box-shadow`:** Adds depth and enhances the visual feedback on hover.

**External References:**

* [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [CSS `max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

