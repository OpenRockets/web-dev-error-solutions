# 🐞 CSS Challenge:  Stylish Accordion with Tailwind CSS


This challenge involves creating a stylish accordion using Tailwind CSS.  The accordion will have multiple sections, each with a clickable header that reveals or hides its corresponding content.  We'll focus on creating a clean, modern look using Tailwind's utility classes for efficient and responsive styling.

**Description of the Styling:**

The accordion will feature:

*   A clean and modern design using Tailwind CSS.
*   Collapsible sections with smooth transitions.
*   Headers with a subtle hover effect.
*   Content areas that expand and collapse seamlessly.
*   Responsive design adapting to different screen sizes.

**Full Code:**

```html
<div class="w-full max-w-lg mx-auto p-4">
  <div class="accordion">
    <div class="accordion-item bg-gray-100 rounded-lg mb-2">
      <h2 class="accordion-header p-4 cursor-pointer bg-gray-200 rounded-t-lg font-bold text-lg hover:bg-gray-300">
        Section 1
      </h2>
      <div class="accordion-content p-4 hidden">
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
      </div>
    </div>
    <div class="accordion-item bg-gray-100 rounded-lg mb-2">
      <h2 class="accordion-header p-4 cursor-pointer bg-gray-200 rounded-t-lg font-bold text-lg hover:bg-gray-300">
        Section 2
      </h2>
      <div class="accordion-content p-4 hidden">
        <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
    </div>
    <div class="accordion-item bg-gray-100 rounded-lg">
      <h2 class="accordion-header p-4 cursor-pointer bg-gray-200 rounded-t-lg font-bold text-lg hover:bg-gray-300">
        Section 3
      </h2>
      <div class="accordion-content p-4 hidden">
        <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
      </div>
    </div>
  </div>
</div>

<script>
  const accordionItems = document.querySelectorAll('.accordion-item');

  accordionItems.forEach(item => {
    const header = item.querySelector('.accordion-header');
    const content = item.querySelector('.accordion-content');

    header.addEventListener('click', () => {
      content.classList.toggle('hidden');
    });
  });
</script>
```


**Explanation:**

*   The HTML uses Tailwind classes to style the accordion structure.  `bg-gray-100`, `rounded-lg`, `p-4`, etc., control the background color, border radius, padding, and other visual aspects.
*   JavaScript is used to handle the accordion functionality.  It adds and removes the `hidden` class to show and hide the content when the header is clicked.
*   The `accordion-item` and `accordion-content` classes are custom to structure the accordion sections.
*  Tailwind's `hover:bg-gray-300` adds a subtle hover effect on the header.


**Links to Resources to Learn More:**

*   **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
*   **JavaScript Basics:**  [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
*   **Understanding DOM Manipulation:** [https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

