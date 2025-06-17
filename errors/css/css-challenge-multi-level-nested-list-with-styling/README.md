# 🐞 CSS Challenge:  Multi-level Nested List with Styling


This challenge focuses on styling a multi-level nested list using CSS, achieving a visually appealing and easily navigable hierarchy. We'll use standard CSS (no frameworks like Tailwind are needed for this specific example, although they could be used).  The goal is to create a nested list that clearly differentiates levels through indentation, different bullet styles, and color variations.

**Description of the Styling:**

The styling will incorporate the following elements:

* **Indentation:** Each nested level will be indented further to the right.
* **Bullet Styles:** The top-level list items will use circles, the second level will use squares, and the third level will use triangles.
* **Color Variation:**  Each level will have a slightly different text color to improve readability and hierarchy.
* **Background Colors:** Alternate background colors will be applied to list items for better visual separation.


**Full Code:**

```css
ul {
  list-style: none; /* Remove default bullet points */
  padding: 0;
  margin-bottom: 1em;
}

li {
  margin-left: 20px; /* Indentation */
}

ul > li { /* Top-level list items */
  list-style-type: disc;
  color: #333;
}

ul > li::before {
  content: "";
  display: inline-block;
  width: 10px;
  height: 10px;
  margin-left: -20px;
  margin-right: 5px;
  border-radius: 50%; /* Circle */
  background-color: #007bff;
}

ul > li:nth-child(even) { /* Alternate background color */
  background-color: #f2f2f2;
}

ul ul > li { /* Second-level list items */
  list-style-type: square;
  color: #555;
}

ul ul > li::before {
  content: "";
  display: inline-block;
  width: 10px;
  height: 10px;
  margin-left: -20px;
  margin-right: 5px;
  background-color: #28a745;
}

ul ul ul > li { /* Third-level list items */
  list-style-type: triangle;
  color: #777;
}

ul ul ul > li::before {
  content: "";
  display: inline-block;
  width: 10px;
  height: 10px;
  margin-left: -20px;
  margin-right: 5px;
  border-left: 5px solid #dc3545;
  border-top: 5px solid transparent;
  border-bottom: 5px solid transparent;
  
}
```


**HTML (Example to use with the CSS):**

```html
<ul>
  <li>Item 1
    <ul>
      <li>Sub-item 1.1
        <ul>
          <li>Sub-sub-item 1.1.1</li>
          <li>Sub-sub-item 1.1.2</li>
        </ul>
      </li>
      <li>Sub-item 1.2</li>
    </ul>
  </li>
  <li>Item 2
    <ul>
      <li>Sub-item 2.1</li>
      <li>Sub-item 2.2</li>
    </ul>
  </li>
  <li>Item 3</li>
</ul>
```


**Explanation:**

The CSS utilizes `list-style-type` to change the bullet style for each level.  The `::before` pseudo-element is used to create custom bullet points with specific shapes and colors.  `nth-child` is used for alternating background colors, improving visual organization. Indentation is managed using `margin-left`.  The code is well-commented to explain each section.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
* **MDN Web Docs - CSS Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks - Lists:** [https://css-tricks.com/almanac/selectors/n/nth-child/](https://css-tricks.com/almanac/selectors/n/nth-child/) (For `nth-child` selector)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

