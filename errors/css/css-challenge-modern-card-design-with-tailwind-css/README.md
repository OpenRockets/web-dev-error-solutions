# 🐞 CSS Challenge:  Modern Card Design with Tailwind CSS


This challenge involves creating a modern-looking product card using Tailwind CSS.  The card will feature an image, title, description, and a call-to-action button.  We'll focus on achieving a clean, visually appealing design using Tailwind's utility-first approach.

## Description of the Styling:

The card will be responsive and adapt to different screen sizes.  It will use a subtle shadow and rounded corners for a modern feel.  The image will be positioned at the top, followed by the title, description, and button.  We'll utilize Tailwind's color palette and spacing utilities for efficient styling.

## Full Code:

```html
<div class="max-w-sm rounded-lg shadow-md bg-white dark:bg-gray-800">
  <img class="rounded-t-lg w-full h-48 object-cover object-center" src="https://images.unsplash.com/photo-1602647396550-b819986a2067?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80" alt="Product Image">
  <div class="p-5">
    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Product Title</h5>
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">This is a longer description of the product. It should be concise and informative, highlighting key features and benefits. </p>
    <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
      Learn More
    </a>
  </div>
</div>
```

## Explanation:

* **`max-w-sm`**: Sets a maximum width for the card.
* **`rounded-lg`**: Applies rounded corners.
* **`shadow-md`**: Adds a medium shadow.
* **`bg-white dark:bg-gray-800`**: Sets the background color to white, and gray for dark mode.
* **`rounded-t-lg`**: Applies rounded corners to the top of the image.
* **`w-full h-48 object-cover object-center`**: Makes the image full width, 48 units high, covers the entire area, and centers the image.
* **`p-5`**: Adds padding.
* **`text-2xl font-bold tracking-tight text-gray-900 dark:text-white`**: Styles the title.
* **`mb-3 font-normal text-gray-700 dark:text-gray-400`**: Styles the description.
* Tailwind's utility classes are used for styling the button (`inline-flex`, `items-center`, `px-3`, `py-2`, etc.).  Dark mode support is included via `dark:` modifiers.

## Links to Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn Tailwind CSS (various tutorials available on YouTube and other platforms):** Search "Learn Tailwind CSS" on YouTube or your preferred learning platform.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

