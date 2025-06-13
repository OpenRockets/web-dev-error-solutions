# 🐞 CSS Challenge:  Modern Card with Tailwind CSS


This challenge involves creating a modern-looking product card using Tailwind CSS. The card will feature an image, title, description, and a call-to-action button. We'll leverage Tailwind's utility classes for efficient and responsive styling.


## Description of the Styling

The card will have a clean and minimalist design.  It will be responsive, adapting well to different screen sizes. The image will be displayed prominently at the top, followed by the title, a short description, and a button to encourage user interaction.  We'll use a subtle shadow and rounded corners to give it a modern feel.  The color palette will be neutral and easy on the eyes.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="max-w-sm rounded overflow-hidden shadow-lg mx-auto my-10 bg-white">
    <img class="w-full" src="https://via.placeholder.com/350x150" alt="Product Image">
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">Product Title</div>
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
* **`overflow-hidden`**: Prevents content from overflowing the card.
* **`shadow-lg`**: Applies a large shadow.
* **`mx-auto`**: Centers the card horizontally.
* **`my-10`**: Adds margin top and bottom.
* **`bg-white`**: Sets the background color to white.
* **`w-full`**: Makes the image take up the full width of its container.
* **`px-6 py-4`**: Adds padding to the content area.
* **`font-bold text-xl mb-2`**: Styles the title.
* **`text-gray-700 text-base`**: Styles the description.
* **`bg-blue-500 hover:bg-blue-700`**: Styles the button with hover effect.


## Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  - The official documentation for Tailwind CSS, a comprehensive resource for learning all its features and utilities.
* **Tailwind CSS Playgrounds:**  Several online playgrounds exist allowing you to experiment with Tailwind CSS without setting up a local development environment. Search for "Tailwind CSS playground" on your preferred search engine.
* **CSS Tricks:** [https://css-tricks.com/](https://css-tricks.com/) - A website with numerous articles and tutorials covering various CSS topics, including best practices and advanced techniques.  Useful for improving your understanding of CSS in general.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

