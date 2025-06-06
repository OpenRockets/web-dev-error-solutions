# 🐞 Creating a CSS-only Expanding Card with a subtle animation


This document details how to create an expanding card effect using only CSS.  The card expands smoothly on hover, revealing additional content.  We'll use CSS transitions and transforms for a clean, modern look. This technique is adaptable to various design styles and is great practice for understanding CSS transitions and transformations.


**Description of the Styling:**

The card uses a simple structure: a container div with an inner div for the main content and another for the expandable content.  On hover, the inner container expands using a CSS transition and transform.  We'll use subtle box-shadows and border-radius to add depth.


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
  overflow: hidden; /* Hide content that overflows */
  transition: box-shadow 0.3s ease, transform 0.3s ease; /* Smooth transitions */
  width: 300px;
}

.card:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Increased shadow on hover */
  transform: translateY(-2px); /* Subtle lift on hover */
}

.card-content {
  padding: 20px;
}

.card-expand {
  max-height: 0; /* Initially hidden */
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.3s ease; /* Smooth transition for height */
}

.card:hover .card-expand {
  max-height: 200px; /* Expand on hover */
}


/* Example Content Styling (optional) */
.card h2 {
  margin-top: 0;
}
.card p {
  line-height: 1.6;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some initial content of the card.</p>
  </div>
  <div class="card-expand">
    <p>This is the expandable content that will be revealed on hover.  It can be anything you want, like additional details, images, or buttons.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`overflow: hidden;`**: This is crucial for hiding the expandable content initially and preventing it from affecting the card's layout.
* **`transition`**: This property allows for smooth animations when the `max-height` or `box-shadow` changes on hover.  The `ease` timing function provides a natural-looking transition.
* **`max-height`**:  This property controls the height of the expandable content.  Setting it to `0` initially hides the content, and setting it to a specific value on hover reveals it.
* **`transform: translateY(-2px)`**: This creates a subtle lift effect when hovering over the card, adding a nice visual touch.  Adjust the value as needed.

**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks (various articles on CSS animations and transitions):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

