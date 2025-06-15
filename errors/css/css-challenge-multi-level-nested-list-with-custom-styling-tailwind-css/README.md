# 🐞 CSS Challenge:  Multi-level Nested List with Custom Styling (Tailwind CSS)


This challenge involves styling a nested, unordered list using Tailwind CSS to create a visually appealing and organized hierarchical structure.  The goal is to visually distinguish between the different levels of nesting and create a clean, readable list.


**Description of the Styling:**

We will create a multi-level nested list where each level has distinct styling.  The top-level list items will have a larger font size and a different background color than subsequent levels.  Indentation will be used to clearly show the hierarchy, and we'll use Tailwind's utility classes to achieve this efficiently. We will also add some subtle hover effects for improved user experience.

**Full Code:**

```html
<ul class="list-disc pl-6">
  <li class="mb-2 bg-gray-100 p-2 rounded text-lg font-medium">
    Level 1 Item 1
    <ul class="list-disc pl-6">
      <li class="mb-2 bg-gray-200 p-2 rounded hover:bg-gray-300">Level 2 Item 1</li>
      <li class="mb-2 bg-gray-200 p-2 rounded hover:bg-gray-300">
        Level 2 Item 2
        <ul class="list-disc pl-6">
          <li class="mb-2 bg-gray-300 p-2 rounded hover:bg-gray-400">Level 3 Item 1</li>
          <li class="mb-2 bg-gray-300 p-2 rounded hover:bg-gray-400">Level 3 Item 2</li>
        </ul>
      </li>
    </ul>
  </li>
  <li class="mb-2 bg-gray-100 p-2 rounded text-lg font-medium">Level 1 Item 2</li>
</ul>
```

**Explanation:**

* **`list-disc`:** This Tailwind class adds a disc bullet point to the list items.
* **`pl-6`:** This adds padding to the left, creating the indentation for each nesting level.  The amount of padding increases with each level.
* **`mb-2`:** Adds a margin to the bottom of each list item for spacing.
* **`bg-gray-100`, `bg-gray-200`, `bg-gray-300`:** These provide different shades of gray backgrounds to visually distinguish the levels.  The shade deepens with each level.
* **`p-2`:** Adds padding to each list item for better readability.
* **`rounded`:**  Adds rounded corners to the list items.
* **`text-lg font-medium`:** Styles the text of the top-level list items.
* **`hover:bg-gray-300`, `hover:bg-gray-400`:**  Adds a hover effect, changing the background color on hover to provide visual feedback.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  (Comprehensive documentation on all Tailwind CSS classes and utilities)
* **CSS Nested Lists Tutorial:** (Search for "CSS nested lists" on your preferred learning platform like freeCodeCamp, MDN Web Docs, etc.  Many tutorials are available.)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

