# 🐞 CSS Challenge: Responsive Image Gallery with CSS Grid


This challenge focuses on building a responsive image gallery using CSS Grid.  The goal is to create a visually appealing layout that adapts seamlessly to different screen sizes, showcasing a set of images effectively. We'll utilize CSS Grid for its power in creating complex layouts easily.

**Description of the Styling:**

The gallery will display images in a grid, with a fixed number of columns on larger screens and collapsing to a single column on smaller screens.  We'll add a subtle hover effect to the images, perhaps a slight shadow or opacity change.  The overall style will be clean and modern.

**Full Code (HTML & CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Image Gallery</title>
<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); /* Responsive columns */
  grid-gap: 20px;
  padding: 20px;
}

.gallery img {
  width: 100%;
  height: auto;
  display: block; /* Prevents extra space below images */
  transition: transform 0.3s ease; /* Smooth hover effect */
}

.gallery img:hover {
  transform: scale(1.05);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

/* Mobile-first approach: Single column on smaller screens */
@media (max-width: 768px) {
  .gallery {
    grid-template-columns: 1fr; /* Single column */
  }
}
</style>
</head>
<body>

<div class="gallery">
  <img src="image1.jpg" alt="Image 1">
  <img src="image2.jpg" alt="Image 2">
  <img src="image3.jpg" alt="Image 3">
  <img src="image4.jpg" alt="Image 4">
  <img src="image5.jpg" alt="Image 5">
  <img src="image6.jpg" alt="Image 6">
</div>

</body>
</html>
```

**Remember to replace `"image1.jpg"`, `"image2.jpg"`, etc. with the actual paths to your images.**


**Explanation:**

* **`display: grid;`**: This is the core of CSS Grid.  It enables grid layout for the `.gallery` container.
* **`grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));`**: This is the magic of responsive grid. `repeat(auto-fit, ...)` allows the grid to automatically adjust the number of columns based on available space. `minmax(250px, 1fr)` ensures each column is at least 250px wide, but will also share available space equally (`1fr`).
* **`grid-gap: 20px;`**: Adds spacing between the grid items (images).
* **`@media (max-width: 768px)`**: This media query targets screens smaller than 768px (tablets and smaller).  Inside, we set `grid-template-columns: 1fr;` to create a single-column layout.
* **`transition` and `transform`**: These properties create the smooth hover effect.


**Links to Resources to Learn More:**

* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) (MDN Web Docs)
* **CSS Grid Tutorial:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (CSS-Tricks)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

