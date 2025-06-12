# 🐞 CSS Challenge:  Gradient-Bordered Card with Tailwind CSS


This challenge focuses on creating a visually appealing card using Tailwind CSS.  The card will feature a gradient border and subtle shadow, demonstrating proficiency in using Tailwind's utility classes for styling and responsive design.

**Description of the Styling:**

The card will be rectangular with rounded corners.  The border will be a subtle linear gradient.  A subtle box shadow will add depth.  The card content (placeholder text and image) will be centrally aligned and visually appealing.  The design aims for a clean, modern look.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gradient Border Card</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-4">
  <div class="max-w-sm rounded-lg overflow-hidden shadow-lg bg-white">
    <img class="w-full h-48 object-cover" src="https://via.placeholder.com/350x150" alt="Placeholder Image">
    <div class="p-4">
      <h2 class="text-xl font-bold text-gray-800 mb-2">Card Title</h2>
      <p class="text-gray-600 text-base">This is a sample card with a gradient border. You can customize the content and styling as needed.</p>
    </div>
    <div class="px-4 py-2 bg-gradient-to-r from-blue-500 to-purple-500 border-t border-gray-200">
       <p class="text-white text-center">Learn More</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`container mx-auto p-4`**: Centers the card horizontally and adds padding.
* **`max-w-sm rounded-lg overflow-hidden shadow-lg bg-white`**: Sets the maximum width, rounded corners, prevents content overflow, adds a shadow, and sets a white background.
* **`w-full h-48 object-cover`**: Makes the image responsive, fills the container, and covers the entire area.
* **`text-xl font-bold text-gray-800`**: Styles the title.
* **`text-gray-600 text-base`**: Styles the paragraph text.
* **`bg-gradient-to-r from-blue-500 to-purple-500 border-t border-gray-200`**: Creates a linear gradient background from blue to purple on the bottom section with a top border.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) - The official documentation for Tailwind CSS.  This is an excellent resource for learning about all the utility classes available.
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) - While not directly used in this example, understanding CSS Grid can help you create more complex layouts.
* **Placeholder Images:** [https://via.placeholder.com/](https://via.placeholder.com/) - Useful for quickly generating placeholder images for testing.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

