# 🐞 CSS Challenge: Responsive Navigation Bar with Submenus


This challenge involves creating a responsive navigation bar that gracefully handles different screen sizes and includes nested submenus for enhanced user experience.  We'll be using CSS3 for the styling.  No JavaScript is required for this specific implementation.


## Description of the Styling

The navigation bar will consist of a main menu with several top-level items. When a user hovers over a top-level item (or clicks it on smaller screens), a submenu will smoothly appear containing secondary navigation links.  The styling will be clean, modern, and adapt seamlessly to various screen sizes, using media queries to adjust layout and appearance based on viewport width.  We will aim for a smooth, user-friendly experience, avoiding jarring transitions.


## Full Code

```css
/* Basic Styling */
nav {
  background-color: #333;
  overflow: hidden;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  float: left;
}

nav a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav a:hover {
  background-color: #ddd;
  color: black;
}

/* Submenu Styling */
nav ul ul {
  display: none;
  position: absolute;
  background-color: #333;
  width: 150px; /* Adjust as needed */
}

nav li:hover > ul {
  display: block;
}

/* Responsiveness */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
    width: 100%;
  }
  nav ul ul {
    position: static;
  }
}
```

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li>
      <a href="#">Services</a>
      <ul>
        <li><a href="#">Service 1</a></li>
        <li><a href="#">Service 2</a></li>
        <li><a href="#">Service 3</a></li>
      </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```


## Explanation

The CSS code utilizes several key techniques:

* **Floats:** The `float: left;` property on the `li` elements arranges the main menu items horizontally.
* **Nested Lists:** Nested unordered lists (`<ul>`) create the submenus.
* **`display: none;` and `:hover`:**  The submenus are initially hidden using `display: none;` and revealed on hover using the `:hover` pseudo-class.
* **`position: absolute;`:** This positions the submenus relative to their parent list items.
* **Media Queries:** The `@media` rule adjusts the layout for smaller screens, making the menu items stack vertically instead of horizontally.  This improves usability on mobile devices.


## Resources to Learn More

* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - A comprehensive resource for all things CSS.
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) - A popular blog with many CSS tutorials and articles.
* **FreeCodeCamp:** [https://www.freecodecamp.org/](https://www.freecodecamp.org/) - Offers interactive CSS courses and challenges.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

