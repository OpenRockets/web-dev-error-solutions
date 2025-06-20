# 🐞 CSS Challenge:  Modern Card Design with Tailwind CSS


This challenge focuses on creating a visually appealing and modern card using Tailwind CSS.  The card will feature an image, title, description, and a button.  We'll leverage Tailwind's utility classes for rapid and efficient styling.


**Description of the Styling:**

The card will be responsive, adapting to different screen sizes. It will have rounded corners, a subtle shadow, and a clean layout. The image will be placed at the top, followed by the title, description, and finally, a call-to-action button. We'll use Tailwind's color palette for a consistent and visually pleasing aesthetic.


**Full Code:**

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

  <div class="container mx-auto p-6">
    <div class="max-w-sm bg-white rounded-lg shadow-md overflow-hidden">
      <img class="w-full h-48 object-cover" src="https://via.placeholder.com/350x150" alt="Card Image">
      <div class="p-4">
        <h2 class="text-xl font-bold text-gray-800 mb-2">Card Title</h2>
        <p class="text-gray-600 text-base">
          This is a sample card description.  You can customize this text to your liking.  Add more details about the product or service you're promoting.
        </p>
        <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Learn More
        </button>
      </div>
    </div>
  </div>

</body>
</html>
```


**Explanation:**

* **`container mx-auto p-6`:** Centers the card horizontally and adds padding.
* **`max-w-sm`:** Limits the card's maximum width.
* **`bg-white rounded-lg shadow-md`:** Sets the background color, rounded corners, and shadow.
* **`overflow-hidden`:** Prevents content from overflowing the card boundaries.
* **`object-cover`:** Ensures the image covers the entire container.
* **Tailwind Typography Classes:**  `text-xl`, `font-bold`, `text-gray-800`, etc., are used for text styling.
* **`bg-blue-500 hover:bg-blue-700`:** Styles the button with a blue background and a hover effect.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  This is the official documentation for Tailwind CSS, containing a wealth of information and examples.
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS Cheat Sheet" on Google – many helpful cheat sheets are available to quickly reference utility classes.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

