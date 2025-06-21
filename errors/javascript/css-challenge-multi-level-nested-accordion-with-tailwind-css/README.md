# 🐞 CSS Challenge:  Multi-level Nested Accordion with Tailwind CSS


This challenge focuses on creating a multi-level nested accordion using Tailwind CSS.  The goal is to build an expandable/collapsible structure where parent sections can contain child sections, all with smooth transitions and clean styling.  This requires utilizing Tailwind's utility classes for styling and JavaScript for the interactive functionality.

**Description of the Styling:**

The accordion will use a clean and modern design.  Each accordion item will have a header with a title and a plus/minus icon to indicate expansion.  The content area will slide down smoothly upon expansion.  The overall styling will be consistent with Tailwind's default aesthetic, maintaining a clean and responsive layout.  Nested accordions will be visually indented to clearly show the hierarchical structure.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nested Accordion</title>
<script src="https://cdn.tailwindcss.com"></script>
<script>
  function toggleAccordion(id) {
    const content = document.getElementById(id + "-content");
    const icon = document.getElementById(id + "-icon");
    content.classList.toggle('hidden');
    icon.classList.toggle('rotate-90');
  }
</script>
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-4">

  <div class="accordion">
    <div class="accordion-item bg-white rounded-lg shadow-md p-4 mb-4">
      <div class="flex justify-between items-center cursor-pointer" onclick="toggleAccordion('item1')">
        <h3 id="item1-header" class="text-lg font-medium">Item 1</h3>
        <svg id="item1-icon" class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
        </svg>
      </div>
      <div id="item1-content" class="hidden mt-2">
        <p>Content for Item 1.</p>
        <div class="ml-4">
          <div class="accordion-item bg-gray-200 rounded-lg shadow-md p-4 mb-4">
            <div class="flex justify-between items-center cursor-pointer" onclick="toggleAccordion('item1-1')">
              <h4 id="item1-1-header" class="text-base font-medium">Sub-item 1.1</h4>
              <svg id="item1-1-icon" class="h-5 w-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
              </svg>
            </div>
            <div id="item1-1-content" class="hidden mt-2">
              <p>Content for Sub-item 1.1</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="accordion-item bg-white rounded-lg shadow-md p-4 mb-4">
      <div class="flex justify-between items-center cursor-pointer" onclick="toggleAccordion('item2')">
        <h3 id="item2-header" class="text-lg font-medium">Item 2</h3>
        <svg id="item2-icon" class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
        </svg>
      </div>
      <div id="item2-content" class="hidden mt-2">
        <p>Content for Item 2.</p>
      </div>
    </div>
  </div>

</div>

</body>
</html>
```

**Explanation:**

*   The HTML utilizes Tailwind classes for styling elements like `bg-white`, `rounded-lg`, `shadow-md`, `flex`, `justify-between`, etc.  These classes handle spacing, borders, shadows, and layout.
*   JavaScript functions `toggleAccordion` handle the show/hide logic, toggling the `hidden` class on the content and rotating the arrow icon.
*   The SVG icons provide visual cues for expansion/collapse.
*   The nesting of accordion items demonstrates the hierarchical structure.  Each nested accordion is styled similarly using Tailwind classes, maintaining consistency.

**Links to Resources to Learn More:**

*   **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
*   **Learn more about Accordions:** [Numerous tutorials available on YouTube and other websites.  Search for "CSS accordion tutorial"]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

