# 🐞 CSS Challenge:  Multi-level Nested Navigation Menu


This challenge involves creating a multi-level nested navigation menu using CSS.  We'll achieve a clean, expandable design suitable for a website with many sections and sub-sections.  This example will use plain CSS3;  a Tailwind CSS implementation would follow similar principles but leverage its utility classes.


**Description of the Styling:**

The navigation menu will be a vertical list.  Top-level items will have a distinct style, and sub-level items will be indented and only visible when their parent item is hovered over.  We'll use a subtle visual cue to indicate expandable items.

**Full Code (CSS3):**

```css
.nav {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav li {
  position: relative;
}

.nav > li > a { /* Top-level links */
  display: block;
  padding: 10px 20px;
  text-decoration: none;
  color: #333;
  background-color: #f0f0f0;
  border-bottom: 1px solid #ddd;
}

.nav > li > a::after { /* Expand/Collapse indicator */
  content: "\25BC"; /* Unicode for down arrow */
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
}

.nav > li.active > a::after {
  content: "\25B2"; /* Unicode for up arrow */
}


.nav ul {
  display: none;
  position: absolute;
  left: 20px; /* Indentation */
  top: 100%;
  background-color: #f8f8f8;
  border: 1px solid #ddd;
}

.nav li:hover > ul {
  display: block;
}

.nav li:hover > a::after{
    content: "\25B2";
}

.nav > li.active > ul {
    display: block;
}
```

**HTML Structure (Example):**

```html
<ul class="nav">
  <li>
    <a href="#">Item 1</a>
    <ul>
      <li><a href="#">Subitem 1.1</a></li>
      <li><a href="#">Subitem 1.2</a></li>
    </ul>
  </li>
  <li class="active">
    <a href="#">Item 2</a>
    <ul>
      <li><a href="#">Subitem 2.1</a></li>
      <li><a href="#">Subitem 2.2</a></li>
      <li><a href="#">Subitem 2.3</a></li>
    </ul>
  </li>
  <li>
    <a href="#">Item 3</a>
  </li>
</ul>
```

**Explanation:**

The CSS uses a combination of `position: relative` and `position: absolute` to achieve the nested menu effect.  The sub-menus are initially hidden (`display: none`) and are shown using the `:hover` pseudo-class. The `::after` pseudo-element adds the expandable/collapse arrow.  The Javascript would be needed to maintain the active state on page load and potential to collapse if clicked again.


**Links to Resources to Learn More:**

* **CSS Pseudo-classes and Pseudo-elements:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Positioning:** [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **Understanding CSS Selectors:** [freeCodeCamp](https://www.freecodecamp.org/news/css-selectors-a-complete-guide/)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

