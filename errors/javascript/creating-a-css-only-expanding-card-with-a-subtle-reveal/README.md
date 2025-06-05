# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details the creation of an expanding card using only CSS.  The card expands smoothly on hover, revealing hidden content with a subtle animation.  We'll leverage CSS transitions and transforms for a clean and elegant effect. This example doesn't utilize any JavaScript or a framework like Tailwind CSS; it focuses on pure CSS3 capabilities.


**Description of the Styling:**

The card utilizes a simple structure: a container (`div`) holding the visible content (title and short description) and a hidden section (`div`) containing the expanded content.  On hover, we use CSS transitions to smoothly animate the height and transform properties, creating the expansion effect. We also add a slight box-shadow change on hover to further enhance the visual feedback.

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
  overflow: hidden; /* Hide overflowing content on expansion */
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease, transform 0.3s ease; /* Smooth transitions */
  width: 300px;
}

.card:hover {
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
  transform: translateY(-2px); /* Subtle lift on hover */
}

.card-content {
  padding: 20px;
}

.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.card-description {
  margin-bottom: 20px;
}

.card-expanded {
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.5s ease; /* Smooth height transition */
}

.card:hover .card-expanded {
  max-height: 200px; /* Expanded height on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Expanding Card</h2>
    <p class="card-description">This is a short description of the card.</p>
  </div>
  <div class="card-expanded">
    <p>This is the expanded content.  It reveals more detailed information about the subject. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nec enim eget elit tempus aliquam. </p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`max-height: 0;`**: This initially hides the expanded content.
* **`overflow: hidden;`**: Prevents the content from overflowing the card boundaries.
* **`transition: max-height 0.5s ease;`**:  Animates the change in `max-height` over 0.5 seconds using an ease timing function.
* **`:hover .card-expanded { max-height: 200px; }`**:  On hover, the `max-height` is set to 200px, triggering the animation.  Adjust 200px to control the expanded height.
* The `transition` on the `.card` class itself handles the box-shadow and transform changes, creating the subtle hover effects.

**Links to Resources to Learn More:**

* **CSS Transitions:**  [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

