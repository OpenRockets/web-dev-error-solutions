# 🐞 CSS Challenge:  Centered, Responsive Navigation Bar


This challenge focuses on creating a responsive navigation bar that remains centered horizontally across different screen sizes. We'll use CSS Grid for layout simplicity and responsiveness.

**Description of the Styling:**

The navigation bar will contain several menu items.  It should be centered both horizontally and vertically within its container.  On smaller screens, the menu items should stack vertically to accommodate smaller viewports.  The styling should be clean and modern.


**Full Code (CSS only - HTML structure is assumed):**

```css
/* Basic Styles */
.navbar {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); /* Responsive columns */
  grid-gap: 10px;
  background-color: #333;
  color: white;
  padding: 10px;
  text-align: center; /* Center text within each item */
}

.navbar-item {
  padding: 10px;
  text-decoration: none;
  color: white;
}

.navbar-item:hover {
  background-color: #555;
}


/* Responsive Styles */
@media (max-width: 768px) {
  .navbar {
    grid-template-columns: 1fr; /* Stack items vertically on smaller screens */
  }
}
```

**HTML Structure (Example):**

```html
<nav class="navbar">
  <a href="#" class="navbar-item">Home</a>
  <a href="#" class="navbar-item">About</a>
  <a href="#" class="navbar-item">Services</a>
  <a href="#" class="navbar-item">Contact</a>
</nav>
```

**Explanation:**

* **`display: grid;`:** This sets up a CSS Grid layout for the navigation bar, enabling easy control over item placement and responsiveness.
* **`grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));`:** This is the core of the responsiveness. `repeat(auto-fit, ...)` allows the grid columns to adjust based on available space. `minmax(100px, 1fr)` ensures each item is at least 100px wide but also expands to fill available space.
* **`grid-gap: 10px;`:** Adds spacing between the menu items.
* **`@media (max-width: 768px)`:** This media query applies styles when the screen width is 768 pixels or less.  In this case, it stacks the items vertically by setting `grid-template-columns: 1fr;`.


**Links to Resources to Learn More:**

* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
* **CSS Tricks (Grid):** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

