# 🐞 CSS Challenge:  Modern Product Card with Tailwind CSS


This challenge involves creating a visually appealing product card using Tailwind CSS.  The card will feature an image, title, description, price, and a "Buy Now" button.  The styling aims for a clean, modern look, suitable for an e-commerce website.

**Description of the Styling:**

The product card will utilize Tailwind's utility classes to achieve a responsive and visually consistent design.  Key styling elements include:

* **Card Container:** A rounded card with a subtle shadow and padding.
* **Image:** A responsive image that fits within the card, maintaining aspect ratio.
* **Title:** A prominent heading with a dark color.
* **Description:** A concise product description in a smaller font size.
* **Price:**  Clearly displayed price, potentially with a currency symbol.
* **Button:** A call-to-action button with a contrasting color and hover effect.


**Full Code:**

```html
<div class="max-w-sm bg-white rounded-lg shadow-md dark:bg-gray-800 dark:border-gray-700">
    <a href="#">
        <img class="p-8 rounded-t-lg" src="https://flowbite.com/docs/images/blog/image-1.jpg" alt="product image" />
    </a>
    <div class="p-5">
        <a href="#">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Noteworthy Launch</h5>
        </a>
        <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">Here are the biggest enterprise stories of the week and the enterprise trends shaping the future of business.</p>
        <div class="flex items-center justify-between">
            <span class="text-3xl font-bold text-gray-900 dark:text-white">$49</span>
            <a href="#" class="inline-flex items-center py-2 px-3 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                Buy Now
                <svg class="ml-2 -mr-1 w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
            </a>
        </div>
    </div>
</div>
```


**Explanation:**

The code utilizes Tailwind's class-based styling.  `max-w-sm` sets a maximum width, `bg-white` sets the background color, `rounded-lg` adds rounded corners, and `shadow-md` applies a shadow.  The `dark:` prefix enables dark mode support.  Similar classes are used for the image, title, description, price, and button.  The button uses a combination of classes for styling and hover effects.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:** [https://tailwindcss.com/docs/cheat-sheet](https://tailwindcss.com/docs/cheat-sheet) (or search for various community-created cheat sheets)
* **Learn CSS:** (Numerous online resources available, search for "Learn CSS" on your preferred learning platform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

