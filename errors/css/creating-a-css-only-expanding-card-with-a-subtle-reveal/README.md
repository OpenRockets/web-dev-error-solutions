# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The effect involves a subtle reveal of content upon hovering, showcasing a smooth transition and clean design. This example uses plain CSS; adapting it to Tailwind CSS would be straightforward by replacing the CSS classes with their Tailwind equivalents.

**Description of the Styling:**

The card employs a basic layout with an image overlayed by text content. On hover, the card expands slightly, revealing more content initially hidden using `overflow: hidden`.  A smooth transition is achieved with CSS transitions. The styling focuses on clean aesthetics, utilizing subtle shadows and color variations for a pleasing visual effect.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 300px;
  height: 200px;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.card:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-content {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 15px;
  background-color: rgba(0, 0, 0, 0.6);
  color: white;
  transition: max-height 0.3s ease-in-out;
  max-height: 0; /* Initially hidden */
  overflow: hidden;
}

.card:hover .card-content {
  max-height: 100px; /* Revealed on hover */
}

.card-title {
  font-size: 1.2em;
  margin-bottom: 5px;
}
</style>
</head>
<body>

<div class="card">
  <img src="https://via.placeholder.com/300x200" alt="Card Image">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p>Some descriptive text about the card goes here.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`overflow: hidden`:** Initially hides the card content.
* **`transition`:** Enables smooth animations for `transform` (scaling) and `box-shadow`.
* **`:hover`:**  Triggers the expansion and shadow changes on mouse hover.
* **`transform: scale(1.05)`:** Slightly increases the card size on hover.
* **`max-height`:** Controls the height of the content area, revealing it gradually.
* **`object-fit: cover`:** Ensures the image covers the entire card area.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Overflow Property:** [MDN Web Docs - CSS Overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

