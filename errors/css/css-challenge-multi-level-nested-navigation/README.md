# 🐞 CSS Challenge:  Multi-level Nested Navigation


This challenge focuses on creating a multi-level nested navigation menu using CSS. We'll aim for a clean, modern look that gracefully handles different screen sizes.  This example uses plain CSS3, but could easily be adapted to a framework like Tailwind CSS.

## Description of the Styling:

The navigation will be a vertically oriented menu with sub-menus appearing on hover.  The top-level items will be bold and have a background color. Sub-menu items will be indented and have a slightly lighter background.  The styling will be responsive, adapting to smaller screens by stacking the menu vertically.


## Full Code (CSS):

```css
.nav {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav li {
  position: relative; /* Needed for submenus */
}

.nav li a {
  display: block;
  padding: 10px 20px;
  text-decoration: none;
  color: #333;
  font-weight: bold;
  background-color: #f0f0f0;
  border-bottom: 1px solid #ddd;
  transition: background-color 0.3s ease; /* Smooth transition for hover effect */
}

.nav li a:hover {
  background-color: #ddd;
}

.nav ul {
  display: none; /* Hide submenus by default */
  position: absolute;
  left: 100%; /* Position submenu to the right */
  top: 0;
  background-color: #f0f0f0;
  border: 1px solid #ddd;
  z-index: 1; /* Ensure submenu is on top */
}

.nav li:hover > ul {
  display: block; /* Show submenu on hover */
}

.nav ul li a {
  font-weight: normal; /* Submenu items less bold */
  background-color: #f8f8f8;
  border-bottom: 1px solid #eee;
}

/* Responsive adjustments for smaller screens */
@media (max-width: 768px) {
  .nav {
    flex-direction: column; /* Stack menu items vertically */
  }
  .nav li {
    position: static; /* Remove positioning for submenus on smaller screens */
  }
  .nav ul {
    position: static; /* Remove positioning for submenus on smaller screens */
    left: 0;
    width: 100%;
  }
}
```

## Full Code (HTML):

```html
<ul class="nav">
  <li><a href="#">Home</a></li>
  <li><a href="#">About</a>
    <ul>
      <li><a href="#">Our Mission</a></li>
      <li><a href="#">Team</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </li>
  <li><a href="#">Services</a>
    <ul>
      <li><a href="#">Design</a></li>
      <li><a href="#">Development</a></li>
    </ul>
  </li>
  <li><a href="#">Blog</a></li>
</ul>
```


## Explanation:

The CSS uses several key techniques:

* **List-style: none;**: Removes default bullet points from the unordered list.
* **Position: relative/absolute**:  Enables precise positioning of the submenus relative to their parent items.
* **Display: block;**: Makes each list item and link take up the full width of its container.
* **:hover**:  Selects the element when the mouse hovers over it.
* **@media (max-width: 768px)**: Applies different styles for smaller screens, making the navigation responsive.


## Links to Resources to Learn More:

* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* **CSS Positioning:** [MDN Web Docs - CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **Learn CSS Grid:** [CSS Grid Layout](https://css-tricks.com/snippets/css/complete-guide-grid/) (For alternative layout approaches)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

