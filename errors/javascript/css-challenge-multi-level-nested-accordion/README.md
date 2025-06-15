# 🐞 CSS Challenge:  Multi-level Nested Accordion


This challenge involves creating a multi-level nested accordion menu using CSS.  We'll focus on a clean, modern design using only CSS (no JavaScript).  This example utilizes CSS variables for easier customization.


**Description of the Styling:**

The accordion will feature a hierarchical structure.  Each accordion item will have a title that, when clicked, reveals its content.  Nested accordions will be indented to clearly show the hierarchy. We aim for a visually appealing and user-friendly experience with smooth transitions.  The styling will be clean and minimal, emphasizing functionality.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Accordion</title>
<style>
:root {
  --accordion-bg: #f0f0f0;
  --accordion-title-bg: #ddd;
  --accordion-title-color: #333;
  --accordion-content-bg: #fff;
  --accordion-content-padding: 15px;
  --accordion-arrow-color: #555;
}

.accordion {
  background-color: var(--accordion-bg);
  border-radius: 5px;
  overflow: hidden;
}

.accordion-item {
  border-bottom: 1px solid #ccc;
}

.accordion-title {
  background-color: var(--accordion-title-bg);
  color: var(--accordion-title-color);
  padding: 10px 15px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.accordion-title::before {
  content: '>';
  font-size: 14px;
  transition: transform 0.2s ease-in-out;
  color: var(--accordion-arrow-color);
}

.accordion-title.active::before {
  transform: rotate(90deg);
}

.accordion-content {
  background-color: var(--accordion-content-bg);
  padding: var(--accordion-content-padding);
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-in-out;
}

.accordion-item.active .accordion-content {
  max-height: 200px; /* Adjust as needed */
}

.accordion-item.active .accordion-title{
  background-color: #d6d6d6;
}

.nested-accordion {
  margin-left: 20px;
}
</style>
</head>
<body>

<div class="accordion">
  <div class="accordion-item">
    <div class="accordion-title">Item 1</div>
    <div class="accordion-content">
      Content 1
      <div class="accordion nested-accordion">
        <div class="accordion-item">
          <div class="accordion-title">Nested Item 1.1</div>
          <div class="accordion-content">Nested Content 1.1</div>
        </div>
        <div class="accordion-item">
          <div class="accordion-title">Nested Item 1.2</div>
          <div class="accordion-content">Nested Content 1.2</div>
        </div>
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <div class="accordion-title">Item 2</div>
    <div class="accordion-content">Content 2</div>
  </div>
</div>

<script>
const accordions = document.querySelectorAll('.accordion-title');
accordions.forEach(accordion => {
  accordion.addEventListener('click', () => {
    const item = accordion.parentElement;
    item.classList.toggle('active');
  });
});
</script>

</body>
</html>
```

**Explanation:**

1.  **CSS Variables:**  The `:root` selector defines CSS variables for easier customization of colors, padding, etc.
2.  **Accordion Structure:**  The HTML uses nested `<div>` elements to represent the accordion items and their content.  The `nested-accordion` class provides visual indentation for nested accordions.
3.  **CSS Transitions:**  `transition` property is used for smooth opening and closing of accordion content.
4.  **JavaScript (minimal):** A small JavaScript snippet adds the click functionality to toggle the `active` class, controlling the visibility of the content.  The `max-height` CSS property is used to show/hide the content.
5. **Styling:** The CSS handles the visual appearance of titles, backgrounds, and content using the defined variables and classes.


**Links to Resources to Learn More:**

*   **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
*   **CSS Variables:** [MDN Web Docs - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
*   **Advanced CSS Techniques:**  Search for "Advanced CSS Layout Techniques" or "CSS Animations" on your favorite learning platform.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

