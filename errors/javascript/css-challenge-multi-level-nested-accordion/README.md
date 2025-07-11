# 🐞 CSS Challenge:  Multi-Level Nested Accordion


This challenge involves creating a multi-level nested accordion using CSS.  The accordion should allow users to expand and collapse sections, with nested sections also expanding and collapsing independently. We'll use pure CSS for styling, avoiding JavaScript.  This example leverages the power of the `:target` pseudo-class and sibling selectors for a clean and efficient solution.


**Description of the Styling:**

The accordion will have a clean, modern look. Each section will have a heading that acts as the toggle.  When a section is expanded, its content will smoothly slide down.  Nested accordions will indent visually to clearly show the hierarchy.  We'll use a simple color palette for readability.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Accordion</title>
<style>
body {
  font-family: sans-serif;
}

.accordion {
  width: 500px;
  border: 1px solid #ccc;
}

.accordion-item {
  border-bottom: 1px solid #ccc;
}

.accordion-title {
  background-color: #f0f0f0;
  padding: 10px;
  cursor: pointer;
}

.accordion-title:hover {
  background-color: #ddd;
}

.accordion-content {
  padding: 10px;
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
</style>
</head>
<body>

<div class="accordion" id="accordion1">
  <div class="accordion-item">
    <h2 class="accordion-title">Section 1</h2>
    <div class="accordion-content">
      <p>Content for Section 1.</p>
      <div class="accordion nested-accordion" id="accordion2">
        <div class="accordion-item">
          <h3 class="accordion-title">Nested Section 1.1</h3>
          <div class="accordion-content">
            <p>Content for Nested Section 1.1.</p>
          </div>
        </div>
        <div class="accordion-item">
          <h3 class="accordion-title">Nested Section 1.2</h3>
          <div class="accordion-content">
            <p>Content for Nested Section 1.2.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-title">Section 2</h2>
    <div class="accordion-content">
      <p>Content for Section 2.</p>
    </div>
  </div>
</div>

<script>
const titles = document.querySelectorAll('.accordion-title');

titles.forEach(title => {
  title.addEventListener('click', function() {
    this.parentNode.classList.toggle('active');
  });
});

</script>


</body>
</html>
```

**Explanation:**

* The HTML structures the accordion using nested `div` elements.  Each section is an `accordion-item` containing a title (`accordion-title`) and content (`accordion-content`).
* The CSS uses `max-height` and `transition` to create the smooth expanding and collapsing effect. The `:target` pseudo-class is not directly used here; a simpler JavaScript solution is implemented for the toggling functionality.
* The JavaScript adds event listeners to the titles, toggling the `active` class on the parent `accordion-item` when clicked. The `active` class then controls the `max-height` of the `accordion-content`.
* The `nested-accordion` class provides visual indentation for nested sections.


**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Pseudo-classes:** [MDN Web Docs - CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **JavaScript Event Listeners:** [MDN Web Docs - AddEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

