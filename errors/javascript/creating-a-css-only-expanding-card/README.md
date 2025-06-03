# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically to reveal more content when hovered over.  This effect is achieved using pure CSS, without JavaScript, leveraging the `:hover` pseudo-class and transitions.  No specific framework like Tailwind CSS is used; this focuses on fundamental CSS techniques.


**Description of the Styling:**

The card consists of a main container with a background image. Inside, there's a content area containing the title and expandable description.  The key to the effect is using `max-height` and `transition` properties. Initially, the description has a small `max-height`, limiting its visibility. On hover, the `max-height` is removed, allowing the description to expand smoothly thanks to the `transition`.  Padding and margin are used for spacing and visual appeal.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  background-image: url('https://via.placeholder.com/300x200'); /* Replace with your image */
  background-size: cover;
  border-radius: 8px;
  overflow: hidden; /* Hide content overflowing the card */
  transition: all 0.3s ease; /* Smooth transition for all properties */
}

.card:hover {
  box-shadow: 0 10px 20px rgba(0,0,0,0.2); /* Add shadow on hover */
  transform: translateY(-5px); /* Add subtle lift on hover */
}

.card-content {
  padding: 20px;
  color: white; /* Text color for contrast */
}

.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.card-description {
  max-height: 60px; /* Initially limits the height */
  overflow: hidden;
  transition: max-height 0.3s ease; /* Smooth transition for max-height */
}

.card:hover .card-description {
  max-height: 300px; /* Remove height limit on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-description">
      This is a sample text for the expanding card.  You can add as much text as you want here. The card will smoothly expand to accommodate the content when you hover over it.  This is a demonstration of a simple but effective CSS-only animation technique.
    </p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`max-height` and `overflow: hidden;`:** This limits the initial height of the description and hides any content exceeding that limit.
* **`:hover` pseudo-class:** This selector targets the element when the mouse hovers over it.
* **`transition` property:**  This smoothly animates changes to specified CSS properties (in this case, `max-height` and other properties for a more polished effect).  The `ease` timing function provides a comfortable transition curve.
* **`box-shadow` and `transform`:** These add visual enhancements on hover to improve the user experience.

**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS-Tricks:** (Search for "CSS Transitions" or "CSS Hover Effects" on their website)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

