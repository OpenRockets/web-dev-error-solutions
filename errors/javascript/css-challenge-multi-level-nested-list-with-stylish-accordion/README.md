# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordion


This challenge focuses on styling a nested, multi-level unordered list to mimic an accordion effect using CSS. Each list item will expand to reveal its sub-items when clicked. We'll leverage CSS only for this, avoiding JavaScript.  This example uses standard CSS, but the principles could be easily adapted to Tailwind CSS.


## Description of the Styling:

The styling aims for a clean, modern look.  We'll use a subtle background color change to indicate the open/closed state of the list items.  Sub-levels will be indented with appropriate padding and potentially different bullet styles.  The overall design will be responsive, adapting gracefully to different screen sizes.


## Full Code:

```css
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

li {
  cursor: pointer;
  padding: 10px;
  border-bottom: 1px solid #ddd;
}

li > ul {
  display: none; /* Initially hide sub-lists */
  padding-left: 20px; /* Indent sub-lists */
}

li.active > ul {
  display: block; /* Show sub-list when parent is active */
}

li:before {
  content: "\25BC"; /* Unicode for a down triangle */
  margin-right: 5px;
  display: inline-block;
}

li.active:before {
  content: "\25B2"; /* Unicode for an up triangle */
}

li:hover {
  background-color: #f0f0f0;
}

li.active {
  background-color: #e0e0e0;
}

/*Optional Styling for Different Levels*/
li ul li:before {
  content: "\2022"; /* Bullet Point */
  margin-right:5px;
}
```

```html
<ul>
  <li>Item 1
    <ul>
      <li>Sub-item 1.1</li>
      <li>Sub-item 1.2
        <ul>
          <li>Sub-sub-item 1.2.1</li>
          <li>Sub-sub-item 1.2.2</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>Item 2</li>
  <li>Item 3
    <ul>
      <li>Sub-item 3.1</li>
    </ul>
  </li>
</ul>

<script>
  const listItems = document.querySelectorAll('li');

  listItems.forEach(item => {
    item.addEventListener('click', () => {
      item.classList.toggle('active');
    });
  });
</script>
```

## Explanation:

The CSS uses the `display: none;` property to initially hide the sub-lists.  The `li.active > ul { display: block; }` rule shows the sub-list when the parent `li` has the `active` class.  The JavaScript code toggles this `active` class on click, creating the accordion effect.  The `:before` pseudo-element is used to add the triangle icons, changing based on the active state.


## Links to Resources to Learn More:

* **CSS Selectors:**  [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) - Learn about different types of CSS selectors to better target elements.
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) -  Understand how to use `:before` and `:after` to add content to elements.
* **CSS Display Property:** [MDN Web Docs - display property](https://developer.mozilla.org/en-US/docs/Web/CSS/display) - Learn how to control the visibility and layout of elements.
* **JavaScript Event Listeners:** [MDN Web Docs - AddEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) -  Understand how to add event listeners to elements.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

