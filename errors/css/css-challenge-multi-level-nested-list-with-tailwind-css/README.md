# 🐞 CSS Challenge:  Multi-level Nested List with Tailwind CSS


This challenge focuses on styling a multi-level nested list using Tailwind CSS.  The goal is to create a visually appealing and easily navigable nested list with clear visual hierarchy, demonstrating understanding of Tailwind's utility classes for styling lists.


## Description of the Styling

The styling aims for a clean, modern look.  We'll use Tailwind's list styles to remove default bullet points and apply custom spacing and indentation to create distinct levels in the nested list.  Different list levels will have varied background colors for better readability and visual distinction.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nested List with Tailwind</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 p-8">

  <div class="max-w-3xl mx-auto">
    <ul class="list-none p-0">
      <li class="bg-blue-100 p-4 rounded mb-2">
        Item 1
        <ul class="list-none p-4 ml-8">
          <li class="bg-green-100 p-2 rounded mb-1">Sub-item 1.1</li>
          <li class="bg-green-100 p-2 rounded mb-1">
            Sub-item 1.2
            <ul class="list-none p-4 ml-8">
              <li class="bg-yellow-100 p-2 rounded">Sub-sub-item 1.2.1</li>
              <li class="bg-yellow-100 p-2 rounded">Sub-sub-item 1.2.2</li>
            </ul>
          </li>
          <li class="bg-green-100 p-2 rounded mb-1">Sub-item 1.3</li>
        </ul>
      </li>
      <li class="bg-blue-100 p-4 rounded mb-2">Item 2
        <ul class="list-none p-4 ml-8">
          <li class="bg-green-100 p-2 rounded mb-1">Sub-item 2.1</li>
          <li class="bg-green-100 p-2 rounded mb-1">Sub-item 2.2</li>
        </ul>
      </li>
      <li class="bg-blue-100 p-4 rounded mb-2">Item 3</li>
    </ul>
  </div>

</body>
</html>
```


## Explanation

* **`list-none`**: Removes default list styles (bullets).
* **`p-0`**:  Removes default padding.
* **`bg-blue-100`, `bg-green-100`, `bg-yellow-100`**: Apply light background colors for visual distinction at each level.  These are Tailwind's pre-defined color classes.
* **`p-4`**:  Adds padding to list items.
* **`rounded`**: Adds rounded corners to list items.
* **`mb-2`**: Adds margin to the bottom of list items for spacing.
* **`ml-8`**:  Adds margin to the left for indentation, creating the nested effect.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  (Official documentation – essential for understanding Tailwind's utility classes)
* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) (For a deeper understanding of CSS list styling in general)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

