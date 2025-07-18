# 🐞 CSS Challenge:  Multi-level Nested List with Tailwind CSS


This challenge involves styling a multi-level nested list using Tailwind CSS to create a visually appealing and easily navigable hierarchy.  The goal is to achieve a clean, modern look with clear visual distinctions between the different list levels.  We'll use Tailwind's utility classes for efficient and responsive styling.


## Description of the Styling:

The nested list will have three levels:

* **Level 1:**  Each top-level list item will have a bold title, a slightly larger font size, and a distinct background color.
* **Level 2:**  Sub-items will be indented, use a smaller font size, and have a subtle background color.
* **Level 3:**  Sub-sub-items will be further indented, use an even smaller font size, and have no background color.

We'll also aim for good spacing and readability using Tailwind's spacing utilities.


## Full Code:

```html
<ul class="list-disc pl-8">
  <li class="bg-gray-100 p-4 rounded mb-4">
    <h3 class="text-lg font-bold">Level 1 Item 1</h3>
    <ul class="list-disc pl-6">
      <li class="bg-gray-200 p-2 rounded mb-2">
        <p class="text-sm">Level 2 Item 1</p>
        <ul class="list-disc pl-6">
          <li class="text-xs">Level 3 Item 1</li>
          <li class="text-xs">Level 3 Item 2</li>
        </ul>
      </li>
      <li class="bg-gray-200 p-2 rounded mb-2">
        <p class="text-sm">Level 2 Item 2</p>
      </li>
    </ul>
  </li>
  <li class="bg-gray-100 p-4 rounded mb-4">
    <h3 class="text-lg font-bold">Level 1 Item 2</h3>
    <ul class="list-disc pl-6">
      <li class="bg-gray-200 p-2 rounded mb-2">
        <p class="text-sm">Level 2 Item 3</p>
      </li>
    </ul>
  </li>
</ul>

```

## Explanation:

* **`list-disc`**:  This Tailwind class adds a disc bullet point to each list item.
* **`pl-8`, `pl-6`**: These classes add padding to the left, creating the indentation for each level. The values (8 and 6) represent units in Tailwind's spacing system.
* **`bg-gray-100`, `bg-gray-200`**: These classes set the background color for different levels using Tailwind's color palette.
* **`p-4`, `p-2`**:  These classes add padding to the list items.
* **`rounded`**: This class adds rounded corners to the list items.
* **`mb-4`, `mb-2`**: These classes add margin to the bottom, creating spacing between list items.
* **`text-lg`, `text-sm`, `text-xs`**: These classes set the font sizes for each level.
* **`font-bold`**: This class makes the Level 1 titles bold.


## Links to Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  This is the official documentation for Tailwind CSS, providing comprehensive information on all its utility classes and features.
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While not directly used here, understanding CSS Grid is beneficial for advanced layout techniques).


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

