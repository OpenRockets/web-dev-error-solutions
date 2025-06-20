# 🐞 CSS Challenge:  Multi-level Nested Lists with Visual Hierarchy


This challenge focuses on styling a multi-level nested list using CSS to create a clear visual hierarchy. We'll use standard CSS for this example, aiming for a clean and readable outcome.  The goal is to visually distinguish between different levels of the list, making it easy to follow the nested structure.


**Description of the Styling:**

The styling will employ indentation, different markers, and color variations to differentiate list levels.  The top-level list items will have a larger font size and a distinct marker.  Subsequent levels will progressively decrease in font size and use different markers (e.g., circles, squares).  Color will be used subtly to enhance the visual separation between levels.


**Full Code:**

```css
ul {
  list-style-type: none; /* Remove default bullet points */
  padding-left: 0;
}

li {
  margin-bottom: 10px;
}

.level1 {
  font-size: 18px;
  font-weight: bold;
}
.level1::before {
  content: "• "; /* Use a bullet for the top level */
  color: #333;
}

.level2 {
  font-size: 16px;
  margin-left: 20px; /* Indent the second level */
}
.level2::before {
  content: "○ "; /* Use a circle for the second level */
  color: #555;
}


.level3 {
  font-size: 14px;
  margin-left: 40px; /* Indent the third level */
}
.level3::before {
  content: "☐ "; /* Use a square for the third level */
  color: #777;
}
```

**HTML (Example):**

```html
<ul>
  <li class="level1">Item 1</li>
  <li class="level1">Item 2
    <ul>
      <li class="level2">Subitem 2.1</li>
      <li class="level2">Subitem 2.2
        <ul>
          <li class="level3">Sub-subitem 2.2.1</li>
          <li class="level3">Sub-subitem 2.2.2</li>
        </ul>
      </li>
    </ul>
  </li>
  <li class="level1">Item 3</li>
</ul>
```


**Explanation:**

The CSS uses the `::before` pseudo-element to add custom markers to each list item.  The `list-style-type: none;` removes the default list styles.  Classes (`level1`, `level2`, `level3`) are used to target specific levels of nesting and apply different styles (font size, indentation, marker).  Indentation is achieved with `margin-left`.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
* **CSS-Tricks - Working with Lists:** [https://css-tricks.com/almanac/selectors/l/list-item/](https://css-tricks.com/almanac/selectors/l/list-item/) (Find a relevant article on CSS-Tricks about lists)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

