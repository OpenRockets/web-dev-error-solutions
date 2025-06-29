# 🐞 CSS Challenge:  Multi-level Nested List with Accordion Effect


This challenge involves creating a nested, multi-level list where each parent list item acts as an accordion, revealing or hiding its child list items upon clicking. We'll use CSS3 for the styling and achieve the accordion effect without JavaScript.

**Description of the Styling:**

The styling will focus on creating a clean and visually appealing nested list. We'll use a subtle background color to distinguish list items, padding for readability, and a plus/minus icon to indicate whether a section is expanded or collapsed. The accordion effect will be achieved by using CSS to toggle the height of the child list elements.  We'll strive for a modern and responsive design.

**Full Code (CSS only):**

```css
/* Styles for the overall list */
.accordion-list {
  list-style: none;
  padding: 0;
  margin: 20px;
}

.accordion-list li {
  background-color: #f4f4f4;
  border: 1px solid #ddd;
  margin-bottom: 10px;
  padding: 10px;
  cursor: pointer;
}

.accordion-list li > ul {
  list-style: disc;
  padding-left: 20px;
  max-height: 0; /* Initially collapsed */
  overflow: hidden;
  transition: max-height 0.3s ease-out; /* Smooth transition */
}

/* Style for the plus/minus icon */
.accordion-list li::before {
  content: "+";
  display: inline-block;
  width: 20px;
  text-align: center;
  margin-right: 10px;
}

/* Style when list item is expanded */
.accordion-list li.active > ul {
  max-height: 200px; /* Adjust as needed */
}

.accordion-list li.active::before {
  content: "-";
}


/* Responsive adjustments (optional) */
@media (max-width: 768px) {
  .accordion-list li {
    font-size: 14px;
  }
}
```

**HTML Structure (Example):**

```html
<ul class="accordion-list">
  <li>Item 1
    <ul>
      <li>Subitem 1.1</li>
      <li>Subitem 1.2</li>
    </ul>
  </li>
  <li>Item 2
    <ul>
      <li>Subitem 2.1</li>
      <li>Subitem 2.2
        <ul>
          <li>Sub-subitem 2.2.1</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>Item 3</li>
</ul>

<script>
  const accordions = document.querySelectorAll('.accordion-list li');
  accordions.forEach(item => {
    item.addEventListener('click', () => {
      item.classList.toggle('active');
    });
  });
</script>
```

**Explanation:**

The CSS uses `max-height` and `transition` to create the accordion effect.  Initially, the child `<ul>` elements have `max-height: 0;` making them collapsed.  When a list item is clicked, JavaScript toggles the `active` class, which changes the `max-height` to a defined value, smoothly revealing the child list items. The `::before` pseudo-element adds the plus/minus icon.  The provided JavaScript is simple and adds the 'active' class on click.  This can be expanded upon for more complex behavior if needed.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **JavaScript Event Listeners:** [MDN Web Docs - Event Listeners](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

