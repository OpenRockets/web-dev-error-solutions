# 🐞 CSS Challenge:  Modern Card Design with Tailwind CSS


This challenge focuses on creating a visually appealing and modern card using Tailwind CSS.  The card will feature an image, title, description, and button, all styled consistently with a clean and contemporary aesthetic. We'll leverage Tailwind's utility-first approach for efficient and maintainable styling.


## Description of the Styling

The card will be responsive, adapting to different screen sizes. It will use a subtle shadow for depth, rounded corners for a modern feel, and a consistent color palette for visual harmony.  The image will be prominent, filling the top portion of the card. The text will be clearly legible and appropriately sized.  The button will have a contrasting color to stand out.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="max-w-sm rounded overflow-hidden shadow-lg mx-auto my-10 bg-white">
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

* **`max-w-sm`:** Limits the card's maximum width for responsiveness.
* **`rounded`:** Adds rounded corners.
* **`overflow-hidden`:** Prevents content from overflowing the card boundaries.
* **`shadow-lg`:** Applies a large shadow.
* **`mx-auto`:** Centers the card horizontally.
* **`my-10`:** Adds margin top and bottom.
* **`bg-white`:** Sets the background color to white.
* **`w-full` (image):** Makes the image take up the full width of its container.
* **`px-6 py-4`:** Adds padding to the text content.
* **`font-bold text-xl mb-2`:** Styles the title.
* **`text-gray-700 text-base`:** Styles the description text.
* **`bg-blue-500 hover:bg-blue-700`:** Styles the button with a blue background and hover effect.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)  - The official Tailwind CSS documentation is an invaluable resource.
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS Cheat Sheet" on Google – numerous helpful cheat sheets are available online to quickly look up classes.
* **Learn CSS:**  Numerous online resources are available for learning CSS fundamentals, including freeCodeCamp, Codecademy, and MDN Web Docs.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

