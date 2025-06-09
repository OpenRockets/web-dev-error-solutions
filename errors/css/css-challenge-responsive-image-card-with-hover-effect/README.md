# 🐞 CSS Challenge: Responsive Image Card with Hover Effect


This challenge focuses on creating a responsive image card using CSS.  The card will feature a background image, overlaid text, and a subtle hover effect that changes the opacity of the overlay. We'll use plain CSS3 for this example, avoiding any CSS frameworks like Tailwind for clarity.

**Description of the Styling:**

The card will be a fixed width (e.g., 300px) with a maximum width of 100% to ensure responsiveness.  The background image will cover the entire card.  A semi-transparent overlay will sit on top, containing the title and a short description. On hover, the overlay's opacity will decrease, revealing more of the background image.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Image Card</title>
<style>
.image-card {
  width: 300px;
  max-width: 100%;
  position: relative;
  overflow: hidden; /* Prevents image overflow */
  margin: 20px auto;
  border-radius: 8px; /* Add rounded corners */
  box-shadow: 0 4px 8px rgba(0,0,0,0.1); /* Add a subtle shadow */
}

.image-card img {
  width: 100%;
  height: auto;
  display: block; /* Remove default margin from img */
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6); /* Semi-transparent black overlay */
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  opacity: 1;
  transition: opacity 0.3s ease; /* Smooth transition on hover */
}

.overlay h2 {
  margin-bottom: 10px;
}

.image-card:hover .overlay {
  opacity: 0.3; /* Reduced opacity on hover */
}
</style>
</head>
<body>

<div class="image-card">
  <img src="https://via.placeholder.com/300x200" alt="Placeholder Image">
  <div class="overlay">
    <h2>Beautiful Landscape</h2>
    <p>A breathtaking view from the mountain top.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

*   We use `position: relative` on the `.image-card` and `position: absolute` on the `.overlay` to correctly layer the elements.
*   `overflow: hidden` prevents the image from overflowing the card boundaries.
*   The `transition` property creates the smooth hover effect.
*   Flexbox is used within the overlay to center the text vertically and horizontally.
*   Replace `"https://via.placeholder.com/300x200"` with your desired image URL.

**Links to Resources to Learn More:**

*   **CSS Positioning:** [MDN Web Docs - CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
*   **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
*   **CSS Flexbox:** [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

