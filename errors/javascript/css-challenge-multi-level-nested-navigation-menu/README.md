# 🐞 CSS Challenge:  Multi-level Nested Navigation Menu


This challenge involves creating a multi-level nested navigation menu using CSS.  The menu should be visually appealing, responsive, and easy to navigate.  We'll use CSS3 for styling, focusing on techniques like hover effects, transitions, and pseudo-elements. No JavaScript will be used.

**Description of the Styling:**

The navigation menu will have a clean, modern look.  The top-level items will be displayed horizontally. Submenus will appear on hover, cascading downwards and slightly offset from the parent item.  The styling will include:

*   A consistent font and color scheme.
*   Smooth hover transitions.
*   Clear visual indicators of active/hovered items.
*   Responsive design to adjust to different screen sizes.


**Full Code (CSS):**

```css
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

nav ul ul {
  display: none;
  position: absolute;
  background-color: #333;
}

nav li:hover > ul {
  display: block;
}

nav ul ul li {
  float: none;
}

nav ul ul a {
  width: 100%;
  left: 0;
}

/* Responsive adjustments */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
  }
  nav ul ul {
    position: relative; /* Remove absolute positioning for smaller screens */
  }
  nav ul ul {
    display: none; /* Hide submenus by default on smaller screens */
  }
  nav li:hover > ul {
    display: block; /* Show submenus on hover */
  }
}
```

**HTML (required for the CSS to work):**

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a>
      <ul>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Our History</a></li>
      </ul>
    </li>
    <li><a href="#">Services</a>
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


**Explanation:**

The CSS uses nested unordered lists (`<ul>`) to create the menu structure.  The `float` property is used to arrange the top-level items horizontally.  The `:hover` pseudo-class is used to trigger the display of submenus.  Absolute positioning is used to position submenus relative to their parent items.  Media queries are used to adjust the layout for smaller screens.


**Links to Resources to Learn More:**

*   **CSS3 Tutorial:** [https://www.w3schools.com/css/](https://www.w3schools.com/css/)
*   **Understanding CSS Selectors:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
*   **Responsive Web Design:** [https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

