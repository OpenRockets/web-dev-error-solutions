# 🐞 CSS Challenge:  Dynamically Sized Card Grid with Tailwind CSS


This challenge focuses on creating a responsive card grid using Tailwind CSS. The grid should dynamically adjust the number of columns based on the screen size, ensuring optimal viewing experience on various devices.  We'll aim for a clean, modern aesthetic.


**Description of the Styling:**

The card grid will contain several cards, each displaying an image and a short title. The styling will leverage Tailwind's pre-built classes for efficient development. We'll use Tailwind's grid system to achieve the responsive layout, and ensure the cards are visually appealing and well-spaced.  The goal is to have a 3-column layout on large screens, a 2-column layout on medium screens, and a 1-column layout on small screens.


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

  <div class="container mx-auto px-4 py-8">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div class="bg-white rounded-lg shadow-md p-6">
        <img src="https://via.placeholder.com/350x150" alt="Card Image 1" class="rounded-t-lg mb-4">
        <h2 class="text-xl font-semibold mb-2">Card Title 1</h2>
        <p class="text-gray-600">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      </div>
      <div class="bg-white rounded-lg shadow-md p-6">
        <img src="https://via.placeholder.com/350x150" alt="Card Image 2" class="rounded-t-lg mb-4">
        <h2 class="text-xl font-semibold mb-2">Card Title 2</h2>
        <p class="text-gray-600">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      </div>
      <div class="bg-white rounded-lg shadow-md p-6">
        <img src="https://via.placeholder.com/350x150" alt="Card Image 3" class="rounded-t-lg mb-4">
        <h2 class="text-xl font-semibold mb-2">Card Title 3</h2>
        <p class="text-gray-600">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      </div>
      <!-- Add more cards as needed -->
    </div>
  </div>

</body>
</html>
```


**Explanation:**

* **`container mx-auto px-4 py-8`**: This centers the content and adds padding.
* **`grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6`**: This sets up the responsive grid.  `grid-cols-1` is the default, `md:grid-cols-2` applies to medium screens and larger, and `lg:grid-cols-3` applies to large screens and larger. `gap-6` adds spacing between the cards.
* **`bg-white rounded-lg shadow-md p-6`**:  These classes style the individual cards with a white background, rounded corners, shadow, and padding.
*  The rest of the classes style the image and text within each card using Tailwind's utility classes.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **Tailwind CSS Grid System:** [https://tailwindcss.com/docs/grid](https://tailwindcss.com/docs/grid)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

