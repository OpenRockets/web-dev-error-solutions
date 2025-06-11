# 🐞 CSS Challenge:  Multi-level Nested Navigation Menu


This challenge involves creating a multi-level nested navigation menu using CSS.  We'll aim for a clean, modern look with smooth transitions and clear visual hierarchy.  We will utilize pure CSS for styling, avoiding JavaScript.


**Description of the Styling:**

The navigation menu will be a vertical list.  Each top-level item will have a clear visual indicator, and sub-menus will slide out horizontally on hover.  We'll use a subtle animation for a smooth user experience.  The styling will be responsive, adapting to different screen sizes.


**Full Code (CSS only):**

```css
nav {
  background-color: #333;
  color: white;
  width: 200px;
}

nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

nav li {
  position: relative;
}

nav a {
  display: block;
  padding: 10px;
  text-decoration: none;
  color: white;
}

nav a:hover {
  background-color: #555;
}

nav ul ul {
  position: absolute;
  left: 200px; /* Adjust based on nav width */
  top: 0;
  display: none;
  background-color: #333;
}

nav li:hover > ul {
  display: block;
}

nav ul ul a {
  padding-left: 20px; /* Indent sub-menu items */
}

/* Responsiveness (adjust as needed): */
@media (max-width: 768px) {
  nav {
    width: 100%;
  }
  nav ul ul {
    left: 100%; /* Full width sub-menu */
    top: 0;
  }

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
        <li><a href="#">Service 3</a>
          <ul>
            <li><a href="#">Sub-service A</a></li>
            <li><a href="#">Sub-service B</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```


**Explanation:**

* The main navigation uses nested unordered lists (`<ul>`) to create the hierarchy.
* `position: relative` on parent list items and `position: absolute` on sub-menus allows for precise positioning.
* `display: none` initially hides sub-menus, and `:hover` shows them.
* Media queries provide basic responsiveness for smaller screens.  You can refine this further based on your design needs.


**Resources to Learn More:**

* **MDN Web Docs - CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  (Comprehensive CSS reference)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Articles and tutorials on CSS techniques)
* **FreeCodeCamp - Responsive Web Design:** [https://www.freecodecamp.org/learn/responsive-web-design/](https://www.freecodecamp.org/learn/responsive-web-design/) (Interactive learning path)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

