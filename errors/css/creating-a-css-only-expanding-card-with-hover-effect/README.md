# 🐞 Creating a CSS-only Expanding Card with Hover Effect


This document details the creation of an expanding card using only CSS.  The card expands on hover, revealing hidden content, showcasing the power of CSS transitions and pseudo-elements. We'll use plain CSS3 for this example, avoiding frameworks like Tailwind for clarity.

**Description of the Styling:**

The card uses a simple container with a background image.  On hover, the container expands vertically, revealing additional content initially hidden using `max-height`.  A subtle shadow effect is added for visual enhancement.  The transition property smoothly animates the height change.


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
  overflow: hidden; /* Hide content that overflows */
  transition: max-height 0.5s ease-in-out; /* Smooth transition */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card-content {
  padding: 20px;
  color: white;
  max-height: 0; /* Initially hidden */
  overflow: hidden;
  transition: max-height 0.5s ease-in-out; /* Smooth transition */
}

.card:hover .card-content {
  max-height: 200px; /* Height on hover */
}

.card-title {
  font-size: 1.5em;
  margin-bottom: 10px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2 class="card-title">Card Title</h2>
    <p>This is some additional content that is revealed when you hover over the card.  You can add as much text or other elements as needed.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`max-height: 0;`**: This initially hides the card content.
* **`overflow: hidden;`**: Prevents content from overflowing the card's boundaries.
* **`transition: max-height 0.5s ease-in-out;`**: This is crucial for the smooth animation.  It specifies that the `max-height` property should change over 0.5 seconds using an "ease-in-out" timing function.
* **`.card:hover .card-content { max-height: 200px; }`**: On hover, the `max-height` is set to 200px, revealing the hidden content.  Adjust this value as needed.
* **Background Image:**  Replace `'https://via.placeholder.com/300x200'` with the URL of your desired background image.

**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

