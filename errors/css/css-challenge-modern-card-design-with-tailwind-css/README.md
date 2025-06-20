# 🐞 CSS Challenge:  Modern Card Design with Tailwind CSS


This challenge focuses on creating a modern, clean card design using Tailwind CSS. The card will feature an image, title, description, and a button.  We'll leverage Tailwind's utility classes for quick and efficient styling.


## Description of the Styling

The card will have a clean, minimalist aesthetic. It will use a subtle shadow for depth, rounded corners, and appropriate padding for readability. The image will be responsive and maintain its aspect ratio.  The title will be prominent, and the description will be concise. The button will have a contrasting color to stand out.  We'll use Tailwind's responsive modifiers to ensure the card adapts well to different screen sizes.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Card</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

  <div class="max-w-sm rounded overflow-hidden shadow-lg m-4 bg-white">
    <img class="w-full" src="https://via.placeholder.com/350x150" alt="Sunset in the mountains">
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">Card Title</div>
      <p class="text-gray-700 text-base">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
      </p>
    </div>
    <div class="px-6 pt-4 pb-2">
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Learn More
      </button>
    </div>
  </div>

</body>
</html>
```


## Explanation

* **`max-w-sm`**: Limits the card's maximum width to small size.
* **`rounded`**: Adds rounded corners.
* **`overflow-hidden`**: Prevents content from overflowing the card's boundaries.
* **`shadow-lg`**: Applies a large shadow.
* **`m-4`**: Adds margin on all sides.
* **`bg-white`**: Sets the background color to white.
* **`w-full` (in the image)**: Makes the image take up the full width of its container.
* **`px-6 py-4`**: Adds padding to the content area.
* **`font-bold text-xl mb-2`**: Styles the title.
* **`text-gray-700 text-base`**: Styles the description.
* **`bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded`**: Styles the button with hover effect.

## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  This is the official documentation for Tailwind CSS, a comprehensive resource for learning all its features and utilities.
* **Tailwind CSS Cheat Sheet:** Search for "Tailwind CSS Cheat Sheet" on Google – many helpful cheat sheets are available to quickly reference common classes.
* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  For a deeper understanding of CSS concepts.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

