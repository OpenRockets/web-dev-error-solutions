# 🐞 CSS Challenge:  Multi-Level Nested List with Stylish Accordions


This challenge focuses on creating a multi-level nested list styled as a series of accordions using CSS. Each list item will act as an accordion header, revealing or hiding its sub-items upon clicking.  We'll use only CSS (no JavaScript) for this effect.  While Tailwind CSS could be used, we'll opt for standard CSS for broader applicability and understanding.

**Description of the Styling:**

The styling aims for a clean, modern look.  The accordion headers will have a subtle background color change on hover and a clear visual indicator of the expansion/collapse state.  Sub-levels will be indented and visually distinct from the parent items.  The overall design prioritizes readability and user-friendliness.


**Full Code:**

```css
body {
  font-family: sans-serif;
}

.accordion {
  background-color: #f2f2f2;
  cursor: pointer;
  padding: 18px;
  width: 100%;
  border: none;
  text-align: left;
  outline: none;
  transition: 0.4s;
}

.active, .accordion:hover {
  background-color: #ddd;
}

.accordion:after {
  content: '\002B';
  color: #777;
  font-weight: bold;
  float: right;
  margin-left: 5px;
}

.active:after {
  content: "\2212";
}

.panel {
  padding: 0 18px;
  background-color: white;
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.2s ease-out;
}

.panel.show {
  max-height: 500px; /* Adjust as needed */
}

.nested-list {
  list-style-type: none;
  padding-left: 20px;
}

.nested-list li {
  margin-bottom: 10px;
}

```

**HTML Structure (Example):**

```html
<ul>
  <li>
    <button class="accordion">Item 1</button>
    <div class="panel">
      <p>Content for Item 1</p>
      <ul class="nested-list">
        <li>
          <button class="accordion">Sub-item 1.1</button>
          <div class="panel">
            <p>Content for Sub-item 1.1</p>
          </div>
        </li>
        <li>
          <button class="accordion">Sub-item 1.2</button>
          <div class="panel">
            <p>Content for Sub-item 1.2</p>
          </div>
        </li>
      </ul>
    </div>
  </li>
  <li>
    <button class="accordion">Item 2</button>
    <div class="panel">
      <p>Content for Item 2</p>
    </div>
  </li>
</ul>
```


**Explanation:**

The CSS utilizes the `max-height` property and transitions to control the accordion's opening and closing.  The `:after` pseudo-element creates the plus/minus indicator.  JavaScript is avoided by leveraging the `:hover` and `active` class which can be toggled via the `onclick` event of the `button` elements (this is typically added in JavaScript, but the CSS styles the elements appropriately). The nested lists are styled for clarity and indentation.  You'll need to add JavaScript to handle the toggling of the `active` and `show` classes for full functionality.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **Understanding `max-height`:** [Understanding max-height](https://css-tricks.com/almanac/properties/m/max-height/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

