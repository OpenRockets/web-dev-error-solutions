# 🐞 CSS Challenge:  Responsive Image Gallery with Tailwind CSS


This challenge involves creating a responsive image gallery using Tailwind CSS. The gallery will display a set of images in a grid layout that adapts gracefully to different screen sizes.  We'll aim for a clean, modern aesthetic.

## Styling Description:

The gallery will feature:

* A grid layout using Tailwind's grid system.  The number of columns will adjust based on screen size (e.g., 3 columns on large screens, 2 on medium, 1 on small).
* Each image will be contained within a card-like element with rounded corners and a subtle shadow.
* Images will maintain their aspect ratio.
* Optional:  hover effects (e.g., image scaling or opacity change).

## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Image Gallery</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="container mx-auto p-8">
    <h1 class="text-3xl font-bold mb-6">Image Gallery</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <img src="image1.jpg" alt="Image 1" class="w-full object-cover">
      </div>
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <img src="image2.jpg" alt="Image 2" class="w-full object-cover">
      </div>
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <img src="image3.jpg" alt="Image 3" class="w-full object-cover">
      </div>
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <img src="image4.jpg" alt="Image 4" class="w-full object-cover">
      </div>
      <!-- Add more image divs as needed -->
    </div>
  </div>

</body>
</html>
```

Remember to replace `"image1.jpg"`, `"image2.jpg"`, etc. with the actual paths to your images.


## Explanation:

* **`container mx-auto p-8`**: This centers the gallery and adds padding.
* **`grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4`**: This creates a responsive grid.  It starts with 1 column, then becomes 2 on medium screens (`md`), and 3 on large screens (`lg`).  `gap-4` adds spacing between the grid items.
* **`bg-white rounded-lg shadow-md overflow-hidden`**: Styles each image card with a white background, rounded corners, a shadow, and prevents image overflow.
* **`w-full object-cover`**: Makes the image fill the entire width of its container while maintaining its aspect ratio and covering the entire area.

## Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/) -  The official documentation is an excellent resource for learning all about Tailwind CSS.
* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) -  Learn more about the CSS Grid layout module.
* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - A comprehensive resource for all things CSS.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

