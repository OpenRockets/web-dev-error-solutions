# 🐞 CSS Challenge:  Modern Card Design with Tailwind CSS


This challenge focuses on creating a visually appealing and modern card using Tailwind CSS.  The card will feature an image, title, description, and a button.  We'll leverage Tailwind's utility classes for quick and efficient styling.


## Description of the Styling

The card will have a clean, minimalist design. It will use a subtle shadow for depth, rounded corners, and appropriate padding to ensure readability.  The image will be placed at the top, followed by the title, description, and finally a call-to-action button. We'll aim for a responsive design that adapts gracefully to different screen sizes.


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

  <div class="max-w-sm rounded overflow-hidden shadow-lg mx-auto my-10 bg-white">
    <img class="w-full" src="https://via.placeholder.com/500x300" alt="Card Image">
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
* **`overflow-hidden`**: Prevents content from overflowing the card.
* **`shadow-lg`**: Applies a large shadow.
* **`mx-auto`**: Centers the card horizontally.
* **`my-10`**: Adds top and bottom margins.
* **`bg-white`**: Sets the background color to white.
* **`w-full`**: Makes the image take up the full width of its container.
* **`px-6 py-4`**: Adds padding to the content area.
* **`font-bold text-xl mb-2`**: Styles the title.
* **`text-gray-700 text-base`**: Styles the description.
* **`bg-blue-500 hover:bg-blue-700`**: Styles the button with a hover effect.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [various online tutorials available](search on your favorite learning platform like YouTube, freeCodeCamp, etc.) (Search for "Learn CSS Grid" or "CSS Grid Tutorial")


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

