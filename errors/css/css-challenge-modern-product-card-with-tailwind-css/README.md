# 🐞 CSS Challenge:  Modern Product Card with Tailwind CSS


This challenge focuses on building a visually appealing product card using Tailwind CSS. The card will showcase a product image, title, description, price, and a "Buy Now" button.  We'll utilize Tailwind's utility classes for efficient and responsive styling.


**Description of the Styling:**

The product card will be a clean and modern design. It will feature:

* A responsive layout that adapts well to different screen sizes.
* A visually prominent product image.
* Clear and concise text for the title, description, and price.
* A well-defined "Buy Now" button with a contrasting color.
* Subtle shadows and spacing to enhance visual appeal.
* A consistent color palette.


**Full Code:**

```html
<div class="max-w-sm bg-white rounded-lg shadow-md dark:bg-gray-800 dark:border-gray-700">
  <a href="#">
    <img class="rounded-t-lg w-full" src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZHVjdHxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=500&q=60" alt="Product image">
  </a>
  <div class="p-5">
    <a href="#">
      <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Product Title</h5>
    </a>
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">Short product description goes here.  This is a sample text.</p>
    <span class="text-lg font-bold text-gray-900 dark:text-white">$29.99</span>
    <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800 mt-4">
      Buy Now
      <svg class="w-3.5 h-3.5 ml-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
      </svg>
    </a>
  </div>
</div>
```


**Explanation:**

The code utilizes Tailwind CSS classes to structure and style the product card.  For example:

* `max-w-sm`: Sets a maximum width for the card.
* `bg-white`: Sets the background color to white.
* `rounded-lg`: Adds rounded corners.
* `shadow-md`: Applies a medium shadow.
* `text-2xl`: Sets the text size to 2xl.
* `dark:bg-gray-800`: Sets the background color to dark gray in dark mode.
* And many more utility classes for styling the different elements within the card.


**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) -  The definitive guide to Tailwind CSS.
* **Tailwind CSS Playgrounds:** Numerous online playgrounds are available for experimenting with Tailwind CSS. Search "Tailwind CSS playground" on Google.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

