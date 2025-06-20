# 🐞 CSS Challenge:  Responsive Social Media Card with Tailwind CSS


This challenge focuses on building a responsive social media card using Tailwind CSS.  The card will feature an image, a title, a short description, and a button. The layout should adapt smoothly to different screen sizes.


**Description of the Styling:**

The social media card will use a clean and modern design. The image will be placed at the top, followed by the title, description, and finally a call-to-action button.  We'll leverage Tailwind's utility classes for easy styling and responsiveness. The card will have rounded corners, padding, and a subtle shadow for visual appeal.  The responsiveness will ensure the card looks good on both large desktops and smaller mobile screens.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Social Media Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-4">
  <div class="max-w-sm bg-white rounded-lg shadow-md p-6">
    <img src="https://via.placeholder.com/350x150" alt="Social Media Image" class="rounded-t-lg w-full mb-4">
    <h2 class="text-xl font-bold mb-2">Awesome Post Title</h2>
    <p class="text-gray-700 mb-4">This is a short and captivating description of the post.  It should entice the user to click the button.</p>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      Learn More
    </button>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`container mx-auto p-4`:** This centers the card horizontally and adds padding.
* **`max-w-sm`:**  This limits the card's maximum width for better responsiveness.
* **`bg-white rounded-lg shadow-md p-6`:** This sets the background color, rounded corners, shadow, and padding for the card.
* **`rounded-t-lg`:** Applies rounded top corners to the image.
* **`text-xl font-bold mb-2`:** Styles the title.
* **`text-gray-700 mb-4`:** Styles the description.
* **`bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded`:** Styles the button with hover effect.  The `hover:` modifier changes the style on hover.
* **`w-full`:** Makes the image take up the full width of its container.
* **`mb-4`:** Adds margin to the bottom of elements for spacing.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:** [Search for "Tailwind CSS Cheat Sheet" on Google - many helpful resources are available]
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While this challenge uses flexbox implicitly through Tailwind, understanding CSS Grid is valuable for responsive layouts).

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

