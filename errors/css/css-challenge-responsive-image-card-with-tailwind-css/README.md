# 🐞 CSS Challenge:  Responsive Image Card with Tailwind CSS


This challenge focuses on creating a responsive image card using Tailwind CSS.  The card will feature an image, a title, and a short description, all neatly arranged and adapting seamlessly to different screen sizes.  We'll leverage Tailwind's utility classes for efficient and concise styling.

**Description of the Styling:**

The card will have a clean, modern look. The image will take up the majority of the card's space, maintaining its aspect ratio. The title will be prominently displayed below the image, and a concise description will follow.  The card will have rounded corners, padding, and a subtle shadow for visual appeal.  Responsiveness is key—the card should adapt gracefully to different screen sizes, preventing content overflow or awkward layouts.


**Full Code:**

```html
<div class="max-w-sm rounded overflow-hidden shadow-lg bg-white">
  <img class="w-full" src="https://via.placeholder.com/500x300" alt="Sunset in the Mountains">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">Sunset over the Lake</div>
    <p class="text-gray-700 text-base">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#photography</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#nature</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700">#landscape</span>
  </div>
</div>
```

**Explanation:**

* **`max-w-sm`:** Limits the card's maximum width to small size.
* **`rounded overflow-hidden`:** Adds rounded corners and prevents content overflow.
* **`shadow-lg`:** Applies a large shadow.
* **`bg-white`:** Sets the background color to white.
* **`w-full` (in the `<img>` tag):** Makes the image take up the full width of its container.
* **`px-6 py-4`:** Adds padding to the content area.
* **`font-bold text-xl mb-2`:** Styles the title.
* **`text-gray-700 text-base`:** Styles the description.
* **`inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2`:** Styles the hashtags.  Each hashtag is styled individually for consistency.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) - The official Tailwind CSS documentation is an excellent resource for learning about its utility classes and functionalities.
* **Tailwind CSS Cheat Sheet:** Search for "Tailwind CSS cheatsheet" on Google – many helpful cheat sheets are available online to quickly find the classes you need.
* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) – A comprehensive resource for learning CSS.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

