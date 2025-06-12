# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordion


This challenge focuses on creating a multi-level nested list that functions as an accordion.  Each list item will have a header that, when clicked, expands or collapses its sub-list(s). We'll use CSS3 for styling and focus on creating a clean, accessible, and visually appealing design.  No JavaScript will be used for the accordion functionality; it will be achieved purely through CSS.

## Description of the Styling

The styling will incorporate a modern and clean aesthetic.  We'll use a subtle background color for the list, visually separate list levels through indentation and different heading styles, and use a smooth transition for the accordion effect. The open/closed state of each list item will be visually clear.

## Full Code (CSS Only)

```css
body {
  font-family: sans-serif;
  line-height: 1.6;
}

.accordion {
  background-color: #f2f2f2;
  padding: 10px;
  border-radius: 5px;
}

.accordion ul {
  list-style: none;
  padding: 0;
}

.accordion li {
  margin-bottom: 10px;
}

.accordion h3 {
  cursor: pointer;
  background-color: #ddd;
  padding: 10px;
  border-radius: 5px;
  margin-bottom: 0;
  transition: background-color 0.3s ease;
}

.accordion h3:hover {
  background-color: #ccc;
}

.accordion ul li {
  padding-left: 20px; /* Indentation for nested levels */
}

.accordion ul li ul {
    margin-top: 0; /* Remove extra margin from nested lists*/
}

.accordion ul.collapsed {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
}

.accordion ul:not(.collapsed) {
  max-height: 500px; /* Adjust as needed */
  transition: max-height 0.3s ease;
}


.accordion h3::before {
  content: "\25BC"; /* Unicode for downward-pointing triangle */
  margin-right: 5px;
  display: inline-block;
  transition: transform 0.3s ease;
}

.accordion ul:not(.collapsed) h3::before {
  transform: rotate(90deg); /* Rotate triangle for expanded state */
  content: "\25B2"; /* Unicode for upward-pointing triangle */

}
```

This CSS is structured to style a standard HTML unordered list (`<ul>`) to create the accordion effect.  The `max-height` property combined with `overflow: hidden` and transitions controls the collapsing behavior. The `::before` pseudo-element adds a dynamic arrow to indicate expansion/collapse.  You can adapt the styling and max-height value according to your design preferences.


## HTML Structure Example:

```html
<div class="accordion">
  <h3>Item 1</h3>
  <ul>
    <li>Sub-item 1.1</li>
    <li>Sub-item 1.2
        <ul>
            <li>Sub-sub-item 1.2.1</li>
            <li>Sub-sub-item 1.2.2</li>
        </ul>
    </li>
  </ul>
  <h3>Item 2</h3>
  <ul class="collapsed">
    <li>Sub-item 2.1</li>
    <li>Sub-item 2.2</li>
  </ul>
</div>

```

Remember to include the CSS in a `<style>` tag in your HTML's `<head>` or in a separate CSS file linked to your HTML.  The initial `collapsed` class on some lists provides a starting state for the accordion.


## Explanation

The key CSS properties that make the accordion work are:

* **`max-height`:**  This controls the visible height of the list.  Setting it to 0 hides the sub-list.
* **`overflow: hidden`:** This prevents content from overflowing the set `max-height`.
* **`transition`:** This creates a smooth animation when the `max-height` changes.
* **Pseudo-element `::before`:** This adds the dynamic arrow that changes direction when the list is expanded or collapsed, improving user experience.


## Links to Resources to Learn More

* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  (Comprehensive CSS reference)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (Great tutorials and articles on CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

