# 🐞 CSS Challenge:  Modern Card Design with Tailwind CSS


This challenge focuses on creating a modern, clean product card using Tailwind CSS.  The card will feature an image, title, description, and a call-to-action button.  We'll leverage Tailwind's utility classes for efficient and responsive styling.

**Description of the Styling:**

The card will have a clean, minimalist aesthetic. It will utilize a subtle shadow for depth and will be fully responsive, adapting gracefully to different screen sizes. The image will be positioned at the top, followed by the title, description, and finally a button encouraging user interaction. We'll use Tailwind's color palette to maintain a consistent and visually appealing design.

**Full Code:**

```html
<div class="max-w-sm rounded overflow-hidden shadow-lg bg-white dark:bg-gray-800">
  <img class="w-full" src="https://via.placeholder.com/350x150" alt="Product Image">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2 text-gray-900 dark:text-white">Product Title</div>
    <p class="text-gray-700 dark:text-gray-400 text-base">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Nulla nec purus feugiat, molestie ipsum et, consequat nibh.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <button class="inline-block bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      Learn More
    </button>
  </div>
</div>
```

**Explanation:**

* **`max-w-sm`:**  Sets a maximum width for the card, ensuring it doesn't overflow on larger screens.
* **`rounded`:** Adds rounded corners to the card.
* **`overflow-hidden`:** Prevents content from overflowing the card's boundaries.
* **`shadow-lg`:** Applies a large shadow for depth.
* **`bg-white dark:bg-gray-800`:** Sets a white background for light mode and a dark gray background for dark mode.
* **`w-full` (image):** Makes the image take up the full width of its container.
* **`px-6 py-4`:** Adds padding to the content area.
* **`font-bold text-xl mb-2 text-gray-900 dark:text-white`:** Styles the title with bold font, extra-large size, bottom margin, and dark/light mode colors.
* **`text-gray-700 dark:text-gray-400 text-base`:** Styles the description text with appropriate colors and size.
* **`inline-block bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded`:** Styles the button with background color, hover effect, text color, padding, and rounded corners.


**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **Tailwind CSS Cheat Sheet:** (Search for "Tailwind CSS Cheat Sheet" on Google – many helpful resources are available)
* **Learn CSS (General):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

