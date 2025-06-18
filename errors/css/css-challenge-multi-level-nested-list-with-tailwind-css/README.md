# 🐞 CSS Challenge:  Multi-level Nested List with Tailwind CSS


This challenge focuses on styling a multi-level nested list using Tailwind CSS. The goal is to create a visually appealing and easily readable nested list with clear hierarchy and consistent spacing.  We'll leverage Tailwind's utility classes to achieve this efficiently.


## Description of the Styling

The styling will achieve the following:

* **Clear Hierarchy:**  Each level of the nested list will be visually distinct, using indentation and different styles for list markers.
* **Consistent Spacing:**  Appropriate spacing will be used between list items and nested lists to improve readability.
* **Modern Appearance:** We'll use Tailwind's styling options to create a clean and modern look.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nested List with Tailwind CSS</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 p-4">

  <ul class="list-disc ml-6">
    <li class="mb-2">Item 1
      <ul class="list-[disc] ml-6">
        <li class="mb-2">Sub-item 1.1</li>
        <li class="mb-2">Sub-item 1.2
          <ul class="list-[circle] ml-6">
            <li class="mb-2">Sub-sub-item 1.2.1</li>
            <li class="mb-2">Sub-sub-item 1.2.2</li>
          </ul>
        </li>
      </ul>
    </li>
    <li class="mb-2">Item 2
      <ul class="list-[disc] ml-6">
        <li class="mb-2">Sub-item 2.1</li>
        <li class="mb-2">Sub-item 2.2</li>
      </ul>
    </li>
    <li class="mb-2">Item 3</li>
  </ul>

</body>
</html>
```


## Explanation

* **`bg-gray-100 p-4`:** This sets a light gray background color and adds padding to the body for better spacing.
* **`list-disc ml-6`:** This applies a disc list marker and a margin-left of 6 units (adjust as needed) to the main list.  The `list-[disc]` inside the nested lists allows for customization of each nested level.  `list-[circle]` is used for the deepest level.
* **`mb-2`:** This adds a bottom margin of 2 units to each list item for better spacing.
* **Nested `<ul>` elements:** These create the nested list structure.  The `ml-6` is repeated to increase indentation at each level.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/) -  The official Tailwind CSS documentation is an excellent resource for learning about all the available utility classes and customizing your Tailwind setup.
* **Learn CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - A comprehensive guide to CSS from Mozilla Developers Network.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

