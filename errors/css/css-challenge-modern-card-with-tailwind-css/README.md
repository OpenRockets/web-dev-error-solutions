# 🐞 CSS Challenge:  Modern Card with Tailwind CSS


This challenge involves creating a modern-looking card using Tailwind CSS.  The card will feature an image, a title, a short description, and a button.  We'll focus on clean styling and responsive design.

**Description of the Styling:**

The card will have a clean, minimalist aesthetic.  It will utilize Tailwind's pre-defined utility classes for rapid development. We'll aim for a card that's visually appealing and adapts gracefully to different screen sizes. The card will have rounded corners, shadows, and a subtle hover effect.

**Full Code:**

```html
<div class="max-w-sm rounded overflow-hidden shadow-lg">
  <img class="w-full" src="https://via.placeholder.com/500x300" alt="Sunset in the mountains">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">Mountain Sunset</div>
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
```

**Explanation:**

* **`max-w-sm`**: Limits the card's maximum width to small size.
* **`rounded`**: Adds rounded corners.
* **`overflow-hidden`**: Prevents content from overflowing the card.
* **`shadow-lg`**: Applies a large shadow.
* **`w-full` (in the `img` tag)**: Makes the image occupy the full width of its container.
* **`px-6 py-4`**: Adds padding to the content area.
* **`font-bold text-xl mb-2`**: Styles the title.
* **`text-gray-700 text-base`**: Styles the description text.
* **`bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded`**: Styles the button with a blue background, hover effect, and white text.

**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)  This is the primary resource for learning Tailwind CSS.
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS cheat sheet" on Google; many helpful cheat sheets are available.  These can be very useful for quickly finding the right utility classes.
* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) A great resource for learning general CSS concepts.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

