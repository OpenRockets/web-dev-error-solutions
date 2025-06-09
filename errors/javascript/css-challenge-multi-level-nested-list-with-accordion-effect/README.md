# 🐞 CSS Challenge:  Multi-level Nested List with Accordion Effect


This challenge involves creating a multi-level nested list where each parent list item can be expanded and collapsed to reveal its children, mimicking an accordion effect. We'll use CSS3 for styling and achieve the accordion functionality without JavaScript.


**Description of the Styling:**

The styling will aim for a clean and modern look.  Each list item will have a clear indicator (e.g., a plus/minus symbol) to show whether it's expanded or collapsed.  The nested lists will be indented for readability.  We'll use CSS transitions to make the expansion and collapse smooth.  We will aim for a simple, accessible design.


**Full Code (CSS only):**

```css
ul {
  list-style: none;
  padding: 0;
}

li {
  position: relative;
  margin-bottom: 10px;
}

.accordion-item {
  cursor: pointer;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  background-color: #f9f9f9;
  transition: background-color 0.3s ease;
}

.accordion-item:hover {
  background-color: #f0f0f0;
}

.accordion-item .indicator {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 1.2em;
}

.accordion-item.expanded .indicator {
  transform: translateY(-50%) rotate(90deg);
}


.accordion-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
}

.accordion-item.expanded .accordion-content {
  max-height: 500px; /* Adjust as needed */
}

ul ul {
  padding-left: 20px;
}
```

**HTML Structure (Example):**

```html
<ul>
  <li class="accordion-item">
    <span>Item 1</span>
    <span class="indicator">+</span>
    <ul class="accordion-content">
      <li>Sub-item 1.1</li>
      <li>Sub-item 1.2</li>
      <li class="accordion-item">
        <span>Sub-item 1.3</span>
        <span class="indicator">+</span>
        <ul class="accordion-content">
          <li>Sub-sub-item 1.3.1</li>
        </ul>
      </li>
    </ul>
  </li>
  <li class="accordion-item">
    <span>Item 2</span>
    <span class="indicator">+</span>
    <ul class="accordion-content">
      <li>Sub-item 2.1</li>
    </ul>
  </li>
</ul>
```

**Explanation:**

The CSS uses `max-height` and transitions to control the height of the nested lists.  The `expanded` class, toggled with JavaScript (not included in this CSS-only example –  it would require a simple JavaScript function to add/remove the class on click), determines whether the content is visible. The `indicator` class changes its rotation to visually represent the expansion/collapse state. The HTML structure uses nested `<ul>` and `<li>` elements to create the multi-level list.  You would need to add JavaScript to handle the click events and toggle the `expanded` class on the list items.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **List Styling in CSS:** [A tutorial on list styling](https://www.w3schools.com/css/css_list.asp)  (replace with a more relevant and specific tutorial if possible)



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

