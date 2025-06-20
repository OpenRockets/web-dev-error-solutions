# 🐞 CSS Challenge:  Multi-Level Nested Navigation


This challenge involves creating a multi-level nested navigation menu using pure CSS.  The goal is to achieve a visually appealing and user-friendly design that smoothly expands and collapses sub-menus on hover. We'll be using only CSS (no JavaScript) to accomplish this.

**Description of the Styling:**

The navigation will be a vertical menu with clear visual hierarchy.  Parent menu items will have a distinct style, with sub-menus appearing on hover, indented and visually separated from the parent items.  We'll aim for a clean, modern aesthetic.  We'll utilize CSS3 features like `transform` and `transition` for smooth animations.

**Full Code (CSS):**

```css
.nav {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav li {
  position: relative;
}

.nav a {
  display: block;
  padding: 10px 20px;
  text-decoration: none;
  color: #333;
  background-color: #f0f0f0;
  transition: background-color 0.3s ease;
}

.nav a:hover {
  background-color: #ddd;
}

.nav ul {
  display: none;
  position: absolute;
  left: 100%;
  top: 0;
  padding: 0;
  margin: 0;
}

.nav li:hover > ul {
  display: block;
}

.nav ul li {
  margin-left: 10px; /* Indent sub-menus */
}

.nav ul a {
  padding-left: 30px; /* Further indent sub-menu items */
}

/* Optional: Add some styling for visual distinction */
.nav > li > a {
  font-weight: bold; /* Make top-level items bold */
}
```

**HTML (Example):**

```html
<nav>
  <ul class="nav">
    <li><a href="#">Home</a></li>
    <li>
      <a href="#">About</a>
      <ul>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">Our History</a></li>
      </ul>
    </li>
    <li>
      <a href="#">Services</a>
      <ul>
        <li><a href="#">Service 1</a></li>
        <li><a href="#">Service 2</a></li>
        <li>
          <a href="#">Service 3</a>
          <ul>
            <li><a href="#">Sub-Service A</a></li>
            <li><a href="#">Sub-Service B</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```


**Explanation:**

* The CSS utilizes the `:hover` pseudo-class to show/hide sub-menus.
* `position: absolute` and `left: 100%` position sub-menus to the right of their parent items.
* `transition` provides smooth background color changes on hover.
* Indentation is achieved with margins and padding.

**Links to Resources to Learn More:**

* **CSS Specificity:** Understanding CSS specificity is crucial for making sure your styles are applied correctly: [MDN Web Docs - CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
* **CSS Pseudo-classes:** Learn more about the power of pseudo-classes like `:hover`, `:focus`, etc.: [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS Positioning:** Mastering CSS positioning (relative, absolute, etc.) is essential for layout control: [MDN Web Docs - CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

