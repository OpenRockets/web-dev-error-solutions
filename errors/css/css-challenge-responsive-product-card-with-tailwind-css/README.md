# 🐞 CSS Challenge:  Responsive Product Card with Tailwind CSS


This challenge involves creating a responsive product card using Tailwind CSS. The card should display a product image, title, description, price, and a "Add to Cart" button.  The layout should adapt gracefully to different screen sizes.


**Description of the Styling:**

The product card will utilize a clean and modern design.  We'll leverage Tailwind's utility classes for quick and efficient styling. The card will have a shadow, rounded corners, and padding. The image will be responsive and maintain aspect ratio. The text will be clearly legible and well-spaced.  The "Add to Cart" button will have a distinct style to encourage interaction.  Responsiveness is key; the layout should adjust elegantly on smaller screens, potentially stacking elements vertically.


**Full Code:**

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

<div class="container mx-auto p-4">
  <div class="max-w-sm bg-white rounded-lg shadow-md overflow-hidden md:max-w-xl">
    <img class="w-full h-48 object-cover" src="https://via.placeholder.com/600x400" alt="Product Image">
    <div class="p-4">
      <h2 class="text-xl font-bold mb-2">Awesome Product Name</h2>
      <p class="text-gray-700 text-base mb-4">This is a short description of the awesome product.  It highlights key features and benefits.</p>
      <p class="text-gray-900 text-lg font-bold mb-2">$49.99</p>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Add to Cart
      </button>
    </div>
  </div>
</div>

</body>
</html>

```


**Explanation:**

* **`container mx-auto p-4`**: Centers the card horizontally and adds padding.
* **`max-w-sm md:max-w-xl`**: Sets a maximum width for smaller screens and increases it on medium screens and above.
* **`bg-white rounded-lg shadow-md overflow-hidden`**: Styles the card with a white background, rounded corners, shadow, and prevents content overflow.
* **`w-full h-48 object-cover`**: Makes the image responsive and covers the entire container.  You should replace the placeholder image URL with your actual product image.
* **Tailwind Typography Classes**:  `text-xl`, `font-bold`, `text-gray-700`, etc., are used for text styling.
* **`bg-blue-500 hover:bg-blue-700`**: Styles the button with a blue background and changes it on hover.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:**  (Search for "Tailwind CSS Cheat Sheet" on Google for various options)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

