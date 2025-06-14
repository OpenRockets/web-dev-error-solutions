# 🐞 CSS Challenge: Responsive Multi-level Navigation Menu


This challenge involves creating a responsive, multi-level navigation menu using CSS.  The menu will expand sub-menus on hover, and gracefully adapt to different screen sizes. We will utilize CSS Grid and Flexbox for layout and responsiveness.


## Description of the Styling

The navigation menu will have a clean and modern look.  The top-level items will be displayed horizontally. On hover, a sub-menu will slide down from the corresponding top-level item.  The sub-menu items will be vertically stacked.  The menu will adapt smoothly to smaller screens, potentially collapsing into a hamburger menu for optimal mobile usability (though this challenge focuses on the initial structure).  We'll use a light color scheme for readability.

## Full Code (CSS only)

```css
nav {
  background-color: #f0f0f0;
  overflow: hidden; /* To prevent submenus from overflowing */
}

.nav-item {
  display: inline-block;
  position: relative; /* Required for positioning submenus */
  padding: 10px 20px;
}

.nav-item a {
  text-decoration: none;
  color: #333;
}

.nav-item:hover {
  background-color: #ddd;
}

.submenu {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1; /* Ensures submenu appears above other elements */
  left: 0;
}

.nav-item:hover .submenu {
  display: block;
}

.submenu-item {
  padding: 10px 20px;
  border-bottom: 1px solid #ddd;
}

.submenu-item:last-child {
  border-bottom: none;
}

/* Media query for smaller screens (adjust breakpoint as needed) */
@media (max-width: 768px) {
  .nav-item {
    display: block; /* Stack items vertically */
    width: 100%; /* Occupy full width */
  }
  .submenu {
    position: static; /* Submenus appear below parent items */
    left: 0;
  }
}
```

To use this code, you'll need an accompanying HTML structure like this:

```html
<nav>
  <div class="nav-item">
    <a href="#">Item 1</a>
    <div class="submenu">
      <div class="submenu-item"><a href="#">Subitem 1.1</a></div>
      <div class="submenu-item"><a href="#">Subitem 1.2</a></div>
    </div>
  </div>
  <div class="nav-item">
    <a href="#">Item 2</a>
    <div class="submenu">
      <div class="submenu-item"><a href="#">Subitem 2.1</a></div>
    </div>
  </div>
  <div class="nav-item">
    <a href="#">Item 3</a>
  </div>
</nav>
```


## Explanation

* **`nav`:**  The main navigation container.  `overflow: hidden` prevents submenus from extending beyond the boundaries of the navigation.
* **`.nav-item`:**  Each top-level menu item. `position: relative` allows us to position the submenu absolutely within the item.
* **`.submenu`:** The container for sub-menu items. `display: none` hides it initially, and `display: block` on hover shows it.
* **`.submenu-item`:**  Each sub-menu item.
* **Media Query:** The `@media` query adjusts the layout for smaller screens, stacking the menu items vertically.


## Links to Resources to Learn More

* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Flexbox:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
* **CSS Positioning:** [https://developer.mozilla.org/en-US/docs/Web/CSS/position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

