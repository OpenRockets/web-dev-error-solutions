# 🐞 CSS Challenge:  Responsive Multi-level Nested Navigation Menu


This challenge involves creating a responsive, multi-level nested navigation menu using CSS.  The menu should collapse and expand gracefully on smaller screens and maintain a clean, visually appealing layout across different screen sizes.  We'll use CSS Grid and Flexbox for layout, focusing on semantic HTML for better accessibility.


**Description of the Styling:**

The navigation menu will have a clean, modern design.  The top-level items will be displayed horizontally. On hover, sub-menus will slide down smoothly.  For smaller screens, the menu will become a hamburger menu that expands vertically, revealing all levels.


**Full Code (CSS Only):**

```css
/* Basic Styling */
nav {
  background-color: #333;
  color: #fff;
}

nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex; /* Horizontal on larger screens */
  flex-wrap: wrap; /* Wrap on smaller screens */
}

nav li {
  position: relative; /* For positioning sub-menus */
}

nav a {
  display: block;
  padding: 15px 20px;
  text-decoration: none;
  color: #fff;
}

nav a:hover {
  background-color: #555;
}

/* Responsive Styling */
@media (max-width: 768px) {
  nav ul {
    flex-direction: column; /* Vertical on smaller screens */
  }
  nav li {
    width: 100%; /* Full width for smaller screens */
  }
  nav ul ul { /* Sub-menus */
    display: none; /* Hide sub-menus by default */
  }
  nav li:hover > ul { /* Show sub-menus on hover */
    display: block;
  }
}

/* Sub-menu Styling */
nav ul ul {
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #444;
  width: 200px;
  display: block;
  z-index: 1; /* Ensure sub-menu is on top */
  transition: opacity 0.3s ease; /* Smooth transition */
}
@media (max-width: 768px){
    nav ul ul {
        position: relative;
        width: 100%;
        left: 0;
    }
}

/*Improve transition*/
nav ul li:hover > ul {
    opacity: 1;
}
nav ul ul{
    opacity: 0;
}



```

**HTML Structure (Example):**

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
      </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

**Explanation:**

The CSS uses a combination of `flex-direction`, `position: absolute`, and media queries to achieve the responsive behavior. The base styles create a horizontal menu.  The media query targets screens smaller than 768px, changing the `flex-direction` to `column` and hiding sub-menus by default.  `position: absolute` is used to position the sub-menus below their parent items.  Hover effects reveal the sub-menus smoothly.  Adjust the media query breakpoint and styling to suit your specific needs.


**Links to Resources to Learn More:**

* **CSS Grid:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Flexbox:** [MDN Web Docs - CSS Flexible Box Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
* **Responsive Web Design:** [Responsive Design Basics](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

