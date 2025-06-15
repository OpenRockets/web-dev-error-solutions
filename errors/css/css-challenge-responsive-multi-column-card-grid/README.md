# 🐞 CSS Challenge: Responsive Multi-Column Card Grid


This challenge focuses on creating a responsive grid of cards that adjusts seamlessly across different screen sizes. We'll use CSS Grid for layout and leverage Tailwind CSS for rapid styling.  The goal is to create a visually appealing and user-friendly card layout that adapts to various devices, from large desktops to small mobile phones.

**Description of the Styling:**

The design involves a grid of cards displaying placeholder images and titles.  The number of columns will dynamically adjust based on screen size:

* **Large screens:**  Three columns
* **Medium screens:** Two columns
* **Small screens:** One column

Each card will have a consistent style with rounded corners, padding, and a subtle shadow.  Tailwind CSS classes will handle the styling efficiently.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Responsive Card Grid</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

<div class="container mx-auto px-4 py-8 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
  <div class="bg-white rounded-lg shadow-md p-6">
    <img src="https://via.placeholder.com/300x200" alt="Card Image 1" class="rounded-t-lg mb-2">
    <h2 class="text-xl font-bold mb-2">Card Title 1</h2>
    <p class="text-gray-700">This is some placeholder text for card 1.</p>
  </div>
  <div class="bg-white rounded-lg shadow-md p-6">
    <img src="https://via.placeholder.com/300x200" alt="Card Image 2" class="rounded-t-lg mb-2">
    <h2 class="text-xl font-bold mb-2">Card Title 2</h2>
    <p class="text-gray-700">This is some placeholder text for card 2.</p>
  </div>
  <div class="bg-white rounded-lg shadow-md p-6">
    <img src="https://via.placeholder.com/300x200" alt="Card Image 3" class="rounded-t-lg mb-2">
    <h2 class="text-xl font-bold mb-2">Card Title 3</h2>
    <p class="text-gray-700">This is some placeholder text for card 3.</p>
  </div>
  <div class="bg-white rounded-lg shadow-md p-6">
    <img src="https://via.placeholder.com/300x200" alt="Card Image 4" class="rounded-t-lg mb-2">
    <h2 class="text-xl font-bold mb-2">Card Title 4</h2>
    <p class="text-gray-700">This is some placeholder text for card 4.</p>
  </div>
  <!-- Add more cards as needed -->
</div>

</body>
</html>
```

**Explanation:**

* We use Tailwind's `grid` system with `grid-cols` to define the number of columns.  The `sm:` and `lg:` prefixes apply the styles at different screen sizes (defined in Tailwind's responsive design system).
* `gap-4` adds spacing between the grid items.
* Tailwind classes like `bg-white`, `rounded-lg`, `shadow-md`, `p-6`, `text-xl`, `font-bold`, and `text-gray-700` style the cards consistently.
* Placeholder images are used for demonstration.  Replace these with your actual images.


**Links to Resources to Learn More:**

* **Tailwind CSS:** [https://tailwindcss.com/](https://tailwindcss.com/)
* **CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* **Responsive Web Design:** [https://developer.mozilla.org/en-US/docs/Web/Responsive_Web_Design](https://developer.mozilla.org/en-US/docs/Web/Responsive_Web_Design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

