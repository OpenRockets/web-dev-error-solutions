# 🐞 CSS Challenge:  Multi-level Nested Accordion


This challenge involves creating a multi-level nested accordion using either plain CSS or Tailwind CSS.  The accordion will allow users to expand and collapse sections, with subsections nested within the main sections.  This requires careful use of CSS selectors and potentially JavaScript for dynamic behavior, although we will focus on a CSS-only solution for this example.


## Styling Description

The accordion will have a clean, modern design.  Each section will have a title that acts as a toggle. When a section is expanded, its content will slide down smoothly. Nested sections will be visually indented to clearly show the hierarchy.  We will use a simple color scheme with light backgrounds and dark text for readability.


## Full Code (CSS Only)

This example uses plain CSS for simplicity.  Adapting to Tailwind CSS is straightforward; you would replace the CSS classes with their Tailwind equivalents.

```css
.accordion {
  width: 300px;
}

.accordion-item {
  border: 1px solid #ccc;
  margin-bottom: 5px;
}

.accordion-header {
  background-color: #f0f0f0;
  padding: 10px;
  cursor: pointer;
}

.accordion-header:hover {
  background-color: #ddd;
}

.accordion-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-out;
}

.accordion-item.active .accordion-content {
  max-height: 500px; /* Adjust as needed */
}

.nested-accordion {
  margin-left: 20px;
}
```

```html
<div class="accordion">
  <div class="accordion-item">
    <div class="accordion-header">Section 1</div>
    <div class="accordion-content">
      Content of Section 1
      <div class="nested-accordion">
        <div class="accordion-item">
          <div class="accordion-header">Subsection 1.1</div>
          <div class="accordion-content">Content of Subsection 1.1</div>
        </div>
        <div class="accordion-item">
          <div class="accordion-header">Subsection 1.2</div>
          <div class="accordion-content">Content of Subsection 1.2</div>
        </div>
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <div class="accordion-header">Section 2</div>
    <div class="accordion-content">Content of Section 2</div>
  </div>
</div>

<script>
const accordions = document.querySelectorAll('.accordion-item');
accordions.forEach(accordion => {
  const header = accordion.querySelector('.accordion-header');
  header.addEventListener('click', () => {
    accordion.classList.toggle('active');
  });
});
</script>
```

Remember to include the JavaScript to toggle the `active` class on click to manage the `max-height`  property.  This is a crucial part to making this functional.


## Explanation

This code uses CSS transitions and the `max-height` property to create the expanding and collapsing effect.  The `active` class is toggled using JavaScript.  The nested accordions are simply further instances of the same accordion structure, ensuring consistency.  The `nested-accordion` class adds indentation for visual clarity.  The `max-height` property needs adjustment depending on your content.



## Links to Resources to Learn More

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Selectors:** [MDN Web Docs - CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* **Tailwind CSS Documentation:** [Tailwind CSS Docs](https://tailwindcss.com/docs)  (If you want to use Tailwind)
* **JavaScript Event Listeners:** [MDN Web Docs - Event Listeners](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

