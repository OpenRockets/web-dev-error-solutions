# 🐞 CSS Challenge:  Three-Column Layout with Sticky Header and Footer


This challenge focuses on creating a responsive three-column layout using CSS.  The layout should include a sticky header that remains at the top of the viewport during scrolling, and a footer that remains fixed at the bottom.  We'll use plain CSS for this example, showcasing fundamental layout techniques.

**Description of the Styling:**

The design consists of three columns of equal width on larger screens.  On smaller screens, the columns stack vertically.  A header is fixed to the top, and a footer is fixed to the bottom.  Basic styling is applied to give each section some visual separation.  We aim for a clean, minimalist aesthetic.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Three-Column Layout</title>
<style>
body {
  margin: 0;
  font-family: sans-serif;
}

header {
  background-color: #f0f0f0;
  padding: 1rem;
  position: sticky;
  top: 0;
  z-index: 1000; /* Ensure it stays above other content */
}

main {
  display: flex;
  flex-wrap: wrap; /* Allow columns to wrap on smaller screens */
}

.column {
  flex: 1 0 33%; /* Each column takes 33% width, 1 is flex-grow, 0 is flex-shrink */
  padding: 1rem;
  box-sizing: border-box; /* Include padding in element width */
}

footer {
  background-color: #f0f0f0;
  padding: 1rem;
  position: fixed;
  bottom: 0;
  width: 100%;
  text-align: center; /* Center the footer content */
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .column {
    flex: 1 0 100%; /* Full width on smaller screens */
  }
}
</style>
</head>
<body>

<header>
  <h1>My Three-Column Layout</h1>
</header>

<main>
  <div class="column">
    <h2>Column 1</h2>
    <p>Some content for column 1.</p>
  </div>
  <div class="column">
    <h2>Column 2</h2>
    <p>Some content for column 2.</p>
  </div>
  <div class="column">
    <h2>Column 3</h2>
    <p>Some content for column 3.</p>
  </div>
</main>

<footer>
  <p>&copy; 2024 My Website</p>
</footer>

</body>
</html>
```


**Explanation:**

* **`position: sticky` for the header:** This makes the header stay fixed at the top once the user scrolls past its initial position.  `z-index` ensures it stays above other content.
* **`display: flex` for the main section:** This enables flexible box layout, allowing easy column creation.  `flex-wrap: wrap` handles responsiveness.
* **`flex: 1 0 33%;` for columns:** This divides the available space equally among the three columns.  `1` allows columns to grow if content expands, `0` prevents shrinking below 33%, and `33%` sets the initial width.
* **`box-sizing: border-box;`:** This crucial line ensures that padding and borders are included within the element's total width, preventing unexpected layout issues.
* **`@media (max-width: 768px)`:** This media query adjusts the layout for smaller screens, making the columns stack vertically.


**Links to Resources to Learn More:**

* **CSS Flexbox:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Positioning:** [https://developer.mozilla.org/en-US/docs/Web/CSS/position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **CSS Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

