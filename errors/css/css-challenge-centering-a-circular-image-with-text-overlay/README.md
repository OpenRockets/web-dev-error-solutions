# 🐞 CSS Challenge:  Centering a Circular Image with Text Overlay


This challenge focuses on styling a circular image with text overlaid in the center.  We'll achieve this using CSS, specifically utilizing techniques for centering elements both horizontally and vertically.  The styling will be responsive to different screen sizes.


## Description of the Styling

The goal is to create a visually appealing component: a circular image with text positioned precisely at its center.  The text should be visible and readable even on smaller screens.  The approach leverages techniques like `border-radius`, flexbox, and potentially `text-align` for optimal centering.


## Full Code (CSS Only - can be easily integrated into HTML)


```css
.circular-image {
  width: 200px; /* Adjust as needed */
  height: 200px; /* Maintain aspect ratio */
  border-radius: 50%; /* Creates the circle */
  overflow: hidden; /* Hides any overflow from the image */
  display: flex; /* Enables flexbox for centering */
  justify-content: center; /* Centers horizontally */
  align-items: center; /* Centers vertically */
  position: relative; /* Needed for absolute positioning of text */
}

.circular-image img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensures image covers the entire circle */
}

.circular-image .overlay-text {
  position: absolute;
  color: white; /* Or any desired color */
  font-weight: bold;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5); /* Adds a subtle shadow for readability */
  z-index:1; /* Ensures text is on top */
}

/* Responsive adjustments (optional) */
@media (max-width: 768px) {
  .circular-image {
    width: 150px;
    height: 150px;
  }
}
```

**To use this CSS:**

You would embed this within `<style>` tags in your HTML file or link to a separate CSS file. Example HTML structure:

```html
<div class="circular-image">
  <img src="your-image.jpg" alt="Circular Image">
  <div class="overlay-text">Your Text Here</div>
</div>
```


## Explanation

* **`border-radius: 50%;`**: This is the key to creating the circular shape.  Setting the border radius to 50% of the width and height makes the element perfectly round.
* **`overflow: hidden;`**: This prevents the image from overflowing the circular container.
* **`display: flex; justify-content: center; align-items: center;`**: Flexbox is used for easy centering. `justify-content: center` centers the content horizontally, and `align-items: center` centers it vertically.
* **`position: relative;` and `position: absolute;`**:  The parent container (`circular-image`) is set to `relative` to allow the absolutely positioned child element (`overlay-text`) to be positioned relative to it. This is crucial for accurate text overlaying.
* **`object-fit: cover;`**: This ensures that the image scales to cover the entire circular area, maintaining aspect ratio.
* **Responsive adjustments**: The `@media` query provides responsiveness by adjusting the size of the circular image based on the screen width.


## Links to Resources to Learn More

* **CSS Flexbox:**  [MDN Web Docs - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Positioning:** [MDN Web Docs - Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **CSS `border-radius`:** [MDN Web Docs - border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

